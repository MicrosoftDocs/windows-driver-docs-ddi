---
UID: NI:gnssdriver.IOCTL_GNSS_DELETE_GEOFENCE
title: IOCTL_GNSS_DELETE_GEOFENCE (gnssdriver.h)
description: The IOCTL_GNSS_DELETE_GEOFENCE control code is used by the GNSS adapter to delete a previously created geofence.
tech.root: gnss
ms.date: 01/03/2023
keywords: ["IOCTL_GNSS_DELETE_GEOFENCE IOCTL"]
ms.keywords: IOCTL_GNSS_DELETE_GEOFENCE, IOCTL_GNSS_DELETE_GEOFENCE control, IOCTL_GNSS_DELETE_GEOFENCE control code [Sensor Devices], gnss.ioctl_gnss_delete_geofence, gnssdriver/IOCTL_GNSS_DELETE_GEOFENCE
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
 - IOCTL_GNSS_DELETE_GEOFENCE
 - gnssdriver/IOCTL_GNSS_DELETE_GEOFENCE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - IOCTL_GNSS_DELETE_GEOFENCE
---

## -description

The **IOCTL_GNSS_DELETE_GEOFENCE** control code is used by the GNSS adapter to delete a previously created geofence.

Applies to GNSS DDI version 2 and later.

## -ioctlparameters

### -input-buffer

A pointer to a [GNSS_GEOFENCE_DELETE_PARAM](./ns-gnssdriver-gnss_geofence_delete_param.md) structure that defines the geofence to be deleted.

### -input-buffer-length

Set to sizeof(GNSS_GEOFENCE_DELETE_PARAM).

### -output-buffer

Set to **NULL**.

### -output-buffer-length

Set to 0.

### -in-out-buffer

### -inout-buffer-length

### -status-block

**Irp->IoStatus.Status** is set to STATUS_SUCCESS if the request is successful. Otherwise, **Status** to the appropriate error condition as a [NTSTATUS](/windows-hardware/drivers/kernel/using-ntstatus-values) code.

## -remarks

NTSTATUS  with the following indications:

- STATUS_SUCCESS: The driver successfully removed the geofence.

- STATUS_UNSUCCESSFUL: Failed, the geofence cannot be deleted.

### GNSS adapter notes

The GNSS adapter does not expect this call to fail because there is no elegant way to handle the consequence of this failure. On failure, the GNSS adapter will issue the **GNSS_ResetGeofencesTracking** command and re-add the geofences.

### GNSS driver  notes

If this is the last geofence, the GNSS driver should stop geofence tracking. If the GNSS engine was unable to track geofences (due to bad signal conditions or other transient errors) prior to the deletion of the last geofence, the monitoring activity should stop.

If the geofence is successfully removed, the driver returns STATUS_SUCCESS. If the geofence cannot be deleted, a failure code,  STATUS_UNSUCCESSFUL, is returned. If a failure occurs, the GNSS adapter issues the GNSS_ResetGeofencesTracking command and recreates the desired geofences. If this command deletes the last defined geofence, the driver stops geofence tracking.

## -see-also

[Creating IOCTL Requests in Drivers](/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers)

[WdfIoTargetSendInternalIoctlOthersSynchronously](../wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md)

[WdfIoTargetSendInternalIoctlSynchronously](../wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md)

[WdfIoTargetSendIoctlSynchronously](../wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md)
