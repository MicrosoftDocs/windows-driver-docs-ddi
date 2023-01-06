---
UID: NI:gnssdriver.IOCTL_GNSS_CREATE_GEOFENCE
title: IOCTL_GNSS_CREATE_GEOFENCE (gnssdriver.h)
description: The IOCTL_GNSS_CREATE_GEOFENCE control code is used by the GNSS adapter to create a geofence.
tech.root: gnss
ms.date: 01/03/2023
keywords: ["IOCTL_GNSS_CREATE_GEOFENCE IOCTL"]
ms.keywords: IOCTL_GNSS_CREATE_GEOFENCE, IOCTL_GNSS_CREATE_GEOFENCE control, IOCTL_GNSS_CREATE_GEOFENCE control code [Sensor Devices], gnss.ioctl_gnss_create_geofence, gnssdriver/IOCTL_GNSS_CREATE_GEOFENCE
req.header: gnssdriver.h
req.include-header: Gnssdriver.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_GNSS_CREATE_GEOFENCE
 - gnssdriver/IOCTL_GNSS_CREATE_GEOFENCE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - IOCTL_GNSS_CREATE_GEOFENCE
---

## -description

The **IOCTL_GNSS_CREATE_GEOFENCE** control code is used by the GNSS adapter to create a geofence.

Applies to GNSS DDI version 2 and later.

## -ioctlparameters

### -input-buffer

A pointer to a [GNSS_GEOFENCE_CREATE_PARAM](./ns-gnssdriver-gnss_geofence_create_param.md) structure that defines the geofence to be created.

### -input-buffer-length

Set to sizeof(**GNSS_GEOFENCE_CREATE_PARAM**).

### -output-buffer

A pointer to a [GNSS_GEOFENCE_CREATE_RESPONSE](./ns-gnssdriver-gnss_geofence_create_response.md) structure.

### -output-buffer-length

Set to sizeof(**GNSS_GEOFENCE_CREATE_RESPONSE**).

### -in-out-buffer

### -inout-buffer-length

### -status-block

**Irp->IoStatus.Status** is set to STATUS_SUCCESS if the request is successful. Otherwise, **Status** to the appropriate error condition as a [NTSTATUS](/windows-hardware/drivers/kernel/using-ntstatus-values) code.

## -remarks

### GNSS adapter notes

If the call is successful, the GNSS engine registers the geofence and assigns a unique ID. The GNSS adapter uses the unique ID for all interaction with the driver regarding this specific geofence.

If the call fails, the GNSS driver must ensure that the GNSS engine does not end up creating the geofence and start tracking it. A failure should roll the state of the GNSS engine back to the previous state before adding this geofence.

The GNSS adapter does not expect the driver to persist the geofences across driver restarts. The GNSS adapter explicitly clears all geofences from the GNSS driver through the **GNSS_ResetGeofencesTracking** command at appropriate times (initialization, tracking status change after a failure, etc.).

### GNSS driver notes

If this is the first geofence, the GNSS driver should start geofence tracking, continue monitoring the geofence against the current location of the device in a power efficient manner, and raise alerts if a geofence is breached. If the GNSS engine is unable to track the geofence (due to bad signal conditions or other transient errors), an error status must be raised through the **LISTEN_GEOFENCES_TRACKINGSTATUS** event.

The GNSS engine must adhere to the following guidelines for geofence tracking:

- The device tracking operation and breach detection must be optimized to take into account the size and area of the geofence. If all conditions are  the same, larger geofences should be tracked less aggressively compared to smaller geofences.

- The device tracking operation must be dynamically optimized to take into account the relative distance of the geofence with respect to the current position. All conditions being equal, farther geofences should be tracked less aggressively compared to the closer ones and the aggression should increase as the device gets closer to the geofence.

- The breach detection mechanism must be asymmetric for entry and exit. As a general rule, the rules for determining exit from a geofence should be relaxed compared to the rules for determining entry into the geofence.

- The breach detection mechanism must take into account potential false positives arising due to the inherent inaccuracy of device location. For example, if the device is hovering near the edge of a geofence, a sub-optimal breach detection mechanism may generate too many entry and exit events back to back even if the device is not physically moving in and out. Asymmetric exit detection and hysteresis are typical measures to avoid such errors.

- The device tracking operation of the GNSS engine must use all forms of available location changed signals that are either available on the SoC or can be used at low-power. Such signals may include, but not limited to, data from accelerometer and other sensors, cellular signal change, WiFi connect/disconnect, and so on.

- The geofence tracking and breach detection operations must be entirely implemented in the GNSS engine on SoC. Neither the GNSS driver nor any other extension component on the application processor should wake up for device tracking or breach detection.

- The GNSS driver and the GNSS engine must expose documented IHV-specific tuning parameters to facilitate performance and power tuning of the geofence tracking functionality. Microsoft and OEMs will make use of  tuning parameters and determine the right balance between the quality of service, reliability, and power cost of the geofence experience end-to-end. Tuning parameters can be made available either through registry settings or through IHV SoC configuration data.

## -see-also

[Creating IOCTL Requests in Drivers](/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers)

[WdfIoTargetSendInternalIoctlOthersSynchronously](../wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md)

[WdfIoTargetSendInternalIoctlSynchronously](../wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md)

[WdfIoTargetSendIoctlSynchronously](../wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md)
