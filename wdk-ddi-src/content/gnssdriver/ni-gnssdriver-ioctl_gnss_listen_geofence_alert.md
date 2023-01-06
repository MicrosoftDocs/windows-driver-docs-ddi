---
UID: NI:gnssdriver.IOCTL_GNSS_LISTEN_GEOFENCE_ALERT
title: IOCTL_GNSS_LISTEN_GEOFENCE_ALERT (gnssdriver.h)
description: The IOCTL_GNSS_LISTEN_GEOFENCE_ALERT control code is used to start listening for geofence alerts from the driver.
tech.root: gnss
ms.date: 01/03/2023
keywords: ["IOCTL_GNSS_LISTEN_GEOFENCE_ALERT IOCTL"]
ms.keywords: IOCTL_GNSS_LISTEN_GEOFENCE_ALERT, IOCTL_GNSS_LISTEN_GEOFENCE_ALERT control, IOCTL_GNSS_LISTEN_GEOFENCE_ALERT control code [Sensor Devices], gnss.ioctl_gnss_listen_geofence_alert, gnssdriver/IOCTL_GNSS_LISTEN_GEOFENCE_ALERT
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
 - IOCTL_GNSS_LISTEN_GEOFENCE_ALERT
 - gnssdriver/IOCTL_GNSS_LISTEN_GEOFENCE_ALERT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - IOCTL_GNSS_LISTEN_GEOFENCE_ALERT
---

## -description

The IOCTL_GNSS_LISTEN_GEOFENCE_ALERT control code is used to start listening for geofence alerts from the driver.

Applies to GNSS DDI version 2 and later.

## -ioctlparameters

### -input-buffer

Set to NULL.

### -input-buffer-length

Set to 0.

### -output-buffer

A pointer to a [GNSS_EVENT](./ns-gnssdriver-gnss_event.md) structure.

The EventType must be set to **GNSS_Event_GeofenceAlertData** and the **GeofenceAlertData** member filled in.

### -output-buffer-length

Set to sizeof(GNSS_EVENT).

### -in-out-buffer

### -inout-buffer-length

### -status-block

**Irp->IoStatus.Status** is set to STATUS_SUCCESS if the request is successful. Otherwise, **Status** to the appropriate error condition as a [NTSTATUS](/windows-hardware/drivers/kernel/using-ntstatus-values) code.

## -remarks

### GNSS adapter notes

The GNSS adapter keeps a pending request all the time.

When the driver completes the I/O call, the adapter issues another IOCTL to receive the next geofence alert.

The GNSS adapter may keep this IOCTL pending even if there are no geofences, or if geofence tracking operation has been reinitialized through the **GNSS_ResetGeofencesTracking** driver command. The GNSS driver must not treat this as an error condition.

### GNSS driver notes

Whenever the GNSS driver gets a geofence alert notification from the GNSS engine, it completes the I/O operation.

If the GNSS adapter is in the process of handling a previous alert and has not issued a pending IOCTL yet, the GNSS driver queues the alert locally and dequeues it whenever the adapter sends this IOCTL.

When a geofence is added for the first time, the initial state (as seen by HLOS) is passed in as a parameter. The GNSS engine should raise the first alert only when there is a change in state from the initial state. This must be handled natively by the GNSS engine itself, as opposed to the GNSS driver filtering out redundant alerts at the driver level, therefore defeating the purpose of unneeded application processor wake-up at initialization.

This IO request is kept pending until an alert is received from the GNSS engine. When the driver completes the IO call, the GNSS adapter issues another IOCTL to receive the next geofence alert. This IOCTL is kept pending even if there are no geofences or tracking operation has been reinitialized through the **GNSS_ResetGeofencesTracking** command. If a new pending IOCTL has not been issued and another geofence alert is received, it is queued locally until the next pending IO request is received.

## -see-also

[Creating IOCTL Requests in Drivers](/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers)

[WdfIoTargetSendInternalIoctlOthersSynchronously](../wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md)

[WdfIoTargetSendInternalIoctlSynchronously](../wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md)

[WdfIoTargetSendIoctlSynchronously](../wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md)
