---
UID: NI:gnssdriver.IOCTL_GNSS_DELETE_GEOFENCE
title: IOCTL_GNSS_DELETE_GEOFENCE
author: windows-driver-content
description: The IOCTL_GNSS_DELETE_GEOFENCE control code is used by the GNSS adapter to delete a previously created geofence.
old-location: sensors\ioctl_gnss_delete_geofence.htm
old-project: sensors
ms.assetid: BF50E28A-56CF-4718-93BB-CCC3DFE84072
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: sensors.ioctl_gnss_delete_geofence, IOCTL_GNSS_DELETE_GEOFENCE control code [Sensor Devices], IOCTL_GNSS_DELETE_GEOFENCE, gnssdriver/IOCTL_GNSS_DELETE_GEOFENCE
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	gnssdriver.h
apiname:
-	IOCTL_GNSS_DELETE_GEOFENCE
product: Windows
targetos: Windows
req.typenames: GNSS_SUPL_CERT_ACTION
---

# IOCTL_GNSS_DELETE_GEOFENCE IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


The <b>IOCTL_GNSS_DELETE_GEOFENCE</b> control code is used by the GNSS adapter to delete a previously created geofence.


<div class="alert"><b>Note</b>  Applies to GNSS DDI version 2 and later.

</div><div> </div>

## -ioctlparameters




### -input-buffer

A pointer to a <a href="..\gnssdriver\ns-gnssdriver-gnss_geofence_delete_param.md">GNSS_GEOFENCE_DELETE_PARAM</a> structure that defines the geofence to be deleted.




### -input-buffer-length

Set to sizeof(GNSS_GEOFENCE_DELETE_PARAM).




### -output-buffer

Set to <b>NULL</b>.


### -output-buffer-length

Set to 0.


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks


NTSTATUS  with the following indications:
<ul>
<li>
STATUS_SUCCESS: The driver successfully removed the geofence.

</li>
<li>
STATUS_UNSUCCESSFUL: Failed, the geofence cannot be deleted.

</li>
</ul><h3><a id="GNSS_adapter_notes"></a><a id="gnss_adapter_notes"></a><a id="GNSS_ADAPTER_NOTES"></a>GNSS adapter notes</h3>The GNSS adapter does not expect this call to fail because there is no elegant way to handle the consequence of this failure. On failure, the GNSS adapter will issue the <b>GNSS_ResetGeofencesTracking</b> command and re-add the geofences.
<h3><a id="GNSS_driver__notes"></a><a id="gnss_driver__notes"></a><a id="GNSS_DRIVER__NOTES"></a>GNSS driver  notes</h3>If this is the last geofence, the GNSS driver should stop geofence tracking. If the GNSS engine was unable to track geofences (due to bad signal conditions or other transient errors) prior to the deletion of the last geofence, the monitoring activity should stop.

If the geofence is successfully removed, the driver returns STATUS_SUCCESS. If the geofence cannot be deleted, a failure code,  STATUS_UNSUCCESSFUL, is returned. If a failure occurs, the GNSS adapter issues the GNSS_ResetGeofencesTracking command and recreates the desired geofences. If this command deletes the last defined geofence, the driver stops geofence tracking.



## -see-also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20IOCTL_GNSS_DELETE_GEOFENCE control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

