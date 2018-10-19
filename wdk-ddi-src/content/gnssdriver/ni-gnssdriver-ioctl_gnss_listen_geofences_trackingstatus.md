---
UID: NI:gnssdriver.IOCTL_GNSS_LISTEN_GEOFENCES_TRACKINGSTATUS
title: IOCTL_GNSS_LISTEN_GEOFENCES_TRACKINGSTATUS
author: windows-driver-content
description: The IOCTL_GNSS_LISTEN_GEOFENCES_TRACKINGSTATUS control code is used to receive geofence tracking status from the driver.
old-location: gnss\ioctl_gnss_listen_geofences_trackingstatus.htm
tech.root: gnss
ms.assetid: 3AB8CECA-C5FD-4B0A-A85B-B6E90FA22B04
ms.date: 02/15/2018
ms.keywords: IOCTL_GNSS_LISTEN_GEOFENCES_TRACKINGSTATUS, IOCTL_GNSS_LISTEN_GEOFENCES_TRACKINGSTATUS control, IOCTL_GNSS_LISTEN_GEOFENCES_TRACKINGSTATUS control code [Sensor Devices], gnss.ioctl_gnss_listen_geofences_trackingstatus, gnssdriver/IOCTL_GNSS_LISTEN_GEOFENCES_TRACKINGSTATUS
ms.topic: ioctl
req.header: gnssdriver.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	gnssdriver.h
api_name:
-	IOCTL_GNSS_LISTEN_GEOFENCES_TRACKINGSTATUS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_GNSS_LISTEN_GEOFENCES_TRACKINGSTATUS IOCTL


## -description


The <b>IOCTL_GNSS_LISTEN_GEOFENCES_TRACKINGSTATUS</b> control code is used to receive geofence tracking status from the driver.
<div class="alert"><b>Note</b>  Applies to GNSS DDI version 2 and later.</div><div> </div>

## -ioctlparameters




### -input-buffer

Set to NULL.




### -input-buffer-length

Set to 0.




### -output-buffer

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn925134">GNSS_EVENT</a> structure.



The EventType must be set to <b>GNSS_Event_GeofencesTrackingStatus</b> and the <b>GeofencesTrackingStatus</b> member filled in.




### -output-buffer-length

Set to sizeof(GNSS_EVENT).




### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks



<h3><a id="GNSS_adapter_notes"></a><a id="gnss_adapter_notes"></a><a id="GNSS_ADAPTER_NOTES"></a>GNSS adapter notes</h3>
The GNSS adapter keeps a pending request all the time.

When the driver completes the I/O call, the adapter issues another IOCTL to receive the next status change notification.

The GNSS adapter may keep this IOCTL pending even if there are no geofences, or if geofence tracking operation has been reinitialized through the <b>GNSS_ResetGeofencesTracking</b> driver command. The GNSS driver must not treat this as an error condition.

The HLOS reacts to the tracking failure alert by starting off its own standby application processor-based geofence tracking engine. The HLOS geofence tracking engine runs in parallel with the GNSS engine and tracks the exact same geofences that the GNSS engine has. 

During this time, any changes in the geofence set (for example, addition of new geofences or deletion of existing geofences) are also communicated to the GNSS engine (although the GNSS engine is unable to track those due to the prevailing low-signal conditions). 

The application processor-based geofence engine stays active for as long as the GNSS engine remains in the low-signal condition. Subsequently, when the GNSS engine is able to track geofences again  by communicating a success tracking status alert through this IOCTL, the HLOS gracefully transfer full control back to the GNSS engine through the following steps.

On receipt of this success tracking status alert, the HLOS brings down it’s application processor-based geofence tracking engine, issues a <b>GNSS_ResetGeofencesTracking</b> command to the GNSS engine, and re-adds the currently active geofences together with the current entry/exit status of each geofence. This reset operation is necessary so that the GNSS engine can re-synchronize the states of all the geofences  and raise any needed geofence alert for any of them

<h3><a id="GNSS_driver_notes"></a><a id="gnss_driver_notes"></a><a id="GNSS_DRIVER_NOTES"></a>GNSS driver notes</h3>
There will be a pending IOCTL all the time. Whenever there is a tracking status change the I/O operation should be completed. When geofences are initially added to the GNSS engine, the HLOS optimistically assumes that the GNSS engine is able to track the geofences. Thus initially the IOCTL should be filled only when the GNSS engine is unable to track geofences, and the tracking status is a failure code. Subsequently, the adapter expects the IOCTL to be filled when the tracking status changes to success.

A failure tracking status implies that the GNSS engine is unable to reliably track geofences due to bad signal conditions or other transient reasons. This status applies to the overall ability to reliably track geofences, as opposed to specific to one or more geofence. Thus a failure status must be reported even when the GNSS engine can track most of the fences, but cannot do so for a smaller number.

When signal conditions degrade while geofences are being tracked, the GNSS engine must make allowances for several retries before declaring a failure status. This will prevent unneeded failovers when the signal degradation is due to transient conditions, for example, when a  user enters a tunnel.

A success status is raised when the GNSS engine had previously raised a failure status, and is now able to track all the geofences again (due to improved signal conditions or other reasons).


If the GNSS engine had previously raised a failure status while geofences were being tracked, no further geofence alerts are expected till the GNSS engine can track all geofences again and has raised a subsequent success status.


When the GNSS engine is unable to track geofences, it may continue to monitor the tracking condition so that it can resume geofence tracking when signal conditions improve. Since the monitoring of tracking condition can be power-intensive, especially under low GNSS signal conditions, the GNSS engine must optimize this activity in an implementation-specific way. The GNSS engine must not keep on consuming power for a prolonged time if the tracking conditions do not improve.

Additionally, if geofence tracking is explicitly reset by the HLOS or the HLOS deletes all geofences, the tracking condition monitoring should immediately stop. When new geofences are subsequently added and the GNSS engine is still unable to track geofences, a subsequent failure status should be raised.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548651">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548656">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548660">WdfIoTargetSendIoctlSynchronously</a>
 

 

