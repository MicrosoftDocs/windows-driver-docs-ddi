---
UID: NI:gnssdriver.IOCTL_GNSS_CREATE_GEOFENCE
title: IOCTL_GNSS_CREATE_GEOFENCE (gnssdriver.h)
description: The IOCTL_GNSS_CREATE_GEOFENCE control code is used by the GNSS adapter to create a geofence.
old-location: gnss\ioctl_gnss_create_geofence.htm
tech.root: gnss
ms.assetid: 114B7E39-1FC6-4AC4-A238-3FC3D4A122B0
ms.date: 02/15/2018
keywords: ["IOCTL_GNSS_CREATE_GEOFENCE IOCTL"]
ms.keywords: IOCTL_GNSS_CREATE_GEOFENCE, IOCTL_GNSS_CREATE_GEOFENCE control, IOCTL_GNSS_CREATE_GEOFENCE control code [Sensor Devices], gnss.ioctl_gnss_create_geofence, gnssdriver/IOCTL_GNSS_CREATE_GEOFENCE
f1_keywords:
 - "gnssdriver/IOCTL_GNSS_CREATE_GEOFENCE"
 - "IOCTL_GNSS_CREATE_GEOFENCE"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- gnssdriver.h
api_name:
- IOCTL_GNSS_CREATE_GEOFENCE
targetos: Windows
req.typenames: 
---

# IOCTL_GNSS_CREATE_GEOFENCE IOCTL


## -description


The <b>IOCTL_GNSS_CREATE_GEOFENCE</b> 
   control code is used by the GNSS adapter to create a geofence.

<div class="alert"><b>Note</b>  Applies to GNSS DDI version 2 and later.

</div><div> </div>

## -ioctlparameters




### -input-buffer

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gnssdriver/ns-gnssdriver-gnss_geofence_create_param">GNSS_GEOFENCE_CREATE_PARAM</a> structure that defines the geofence to be created.




### -input-buffer-length

Set to sizeof(<b>GNSS_GEOFENCE_CREATE_PARAM</b>).




### -output-buffer

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gnssdriver/ns-gnssdriver-gnss_geofence_create_response">GNSS_GEOFENCE_CREATE_RESPONSE</a> structure.


### -output-buffer-length

Set to sizeof(<b>GNSS_GEOFENCE_CREATE_RESPONSE</b>).


### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NTSTATUS</a> code. 


## -remarks



<h3><a id="GNSS_adapter_notes"></a><a id="gnss_adapter_notes"></a><a id="GNSS_ADAPTER_NOTES"></a>GNSS adapter notes</h3>
If the call is successful, the GNSS engine registers the geofence and assigns a unique ID. The GNSS adapter uses the unique ID for all interaction with the driver regarding this specific geofence.


If the call fails, the GNSS driver must ensure that the GNSS engine does not end up creating the geofence and start tracking it. A failure should roll the state of the GNSS engine back to the previous state before adding this geofence.


The GNSS adapter does not expect the driver to persist the geofences across driver restarts. The GNSS adapter explicitly clears all geofences from the GNSS driver through the <b>GNSS_ResetGeofencesTracking</b> command at appropriate times (initialization, tracking status change after a failure, etc.).

<h3><a id="GNSS_driver_notes"></a><a id="gnss_driver_notes"></a><a id="GNSS_DRIVER_NOTES"></a>GNSS driver notes</h3>
If this is the first geofence, the GNSS driver should start geofence tracking, continue monitoring the geofence against the current location of the device in a power efficient manner, and raise alerts if a geofence is breached. If the GNSS engine is unable to track the geofence (due to bad signal conditions or other transient errors), an error status must be raised through the <b>LISTEN_GEOFENCES_TRACKINGSTATUS</b> event.

The GNSS engine must adhere to the following guidelines for geofence tracking:

<ul>
<li>
The device tracking operation and breach detection must be optimized to take into account the size and area of the geofence. If all conditions are  the same, larger geofences should be tracked less aggressively compared to smaller geofences.

</li>
<li>
The device tracking operation must be dynamically optimized to take into account the relative distance of the geofence with respect to the current position. All conditions being equal, farther geofences should be tracked less aggressively compared to the closer ones and the aggression should increase as the device gets closer to the geofence.

</li>
<li>
The breach detection mechanism must be asymmetric for entry and exit. As a general rule, the rules for determining exit from a geofence should be relaxed compared to the rules for determining entry into the geofence.

</li>
<li>
The breach detection mechanism must take into account potential false positives arising due to the inherent inaccuracy of device location. For example, if the device is hovering near the edge of a geofence, a sub-optimal breach detection mechanism may generate too many entry and exit events back to back even if the device is not physically moving in and out. Asymmetric exit detection and hysteresis are typical measures to avoid such errors.

</li>
<li>
The device tracking operation of the GNSS engine must use all forms of available location changed signals that are either available on the SoC or can be used at low-power. Such signals may include, but not limited to, data from accelerometer and other sensors, cellular signal change, WiFi connect/disconnect, and so on.

</li>
<li>
The geofence tracking and breach detection operations must be entirely implemented in the GNSS engine on SoC. Neither the GNSS driver nor any other extension component on the application processor should wake up for device tracking or breach detection.

</li>
<li>
The GNSS driver and the GNSS engine must expose documented IHV-specific tuning parameters to facilitate performance and power tuning of the geofence tracking functionality. Microsoft and OEMs will make use of  tuning parameters and determine the right balance between the quality of service, reliability, and power cost of the geofence experience end-to-end. Tuning parameters can be made available either through registry settings or through IHV SoC configuration data.

</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
 

 

