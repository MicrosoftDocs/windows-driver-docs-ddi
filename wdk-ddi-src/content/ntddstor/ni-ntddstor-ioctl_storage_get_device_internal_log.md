---
UID: NI:ntddstor.IOCTL_STORAGE_GET_DEVICE_INTERNAL_LOG
title: IOCTL_STORAGE_GET_DEVICE_INTERNAL_LOG
description: A driver can use IOCTL_STORAGE_GET_DEVICE_INTERNAL_LOG to get the internal status data from the device.
tech.root: storage
ms.date: 08/04/2020
ms.topic: ioctl
req.header: ntddstor.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.max-support: 
targetos: Windows
f1_keywords:
 - IOCTL_STORAGE_GET_DEVICE_INTERNAL_LOG
 - ntddstor/IOCTL_STORAGE_GET_DEVICE_INTERNAL_LOG
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - IOCTL_STORAGE_GET_DEVICE_INTERNAL_LOG
product:
 - Windows
---

# IOCTL_STORAGE_GET_DEVICE_INTERNAL_LOG IOCTL

### Major Code

[IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-device-control)


## -description

A driver can use **IOCTL_STORAGE_GET_DEVICE_INTERNAL_LOG** to get the internal status data from the device.

## -ioctlparameters

### -input-buffer

A [**GET_DEVICE_INTERNAL_STATUS_DATA_REQUEST**](ns-ntddstor-get_device_internal_status_data_request.md) structure that identifies the type of data to be queried.

### -input-buffer-length

**Parameters.DeviceIoControl.InputBufferLength** indicates the size, in bytes, of the parameter buffer at **Irp->AssociatedIrp.SystemBuffer**, which must be >= **sizeof(GET_DEVICE_INTERNAL_STATUS_DATA_REQUEST)**.

### -output-buffer

The driver returns output to the buffer at **Irp->AssociatedIrp.SystemBuffer**. This buffer contains a [**DEVICE_INTERNAL_STATUS_DATA**](ns-ntddstor-device_internal_status_data.md) structure with the device's internal status.

### -output-buffer-length

**Parameters.DeviceIoControl.OutputBufferLength** in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be >= **sizeof(DEVICE_INTERNAL_STATUS_DATA)**.

### -status-block

**Irp->IoStatus.Status** is set to STATUS_SUCCESS if the request is successful.
Otherwise, Status is set to the appropriate error condition as a NTSTATUS code. For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

IOCTL_STORAGE_GET_DEVICE_INTERNAL_LOG returns the host-initiated device telemetry log from any storage device. The following pseudocode shows how to request the telemetry data header:

```cpp
// Allocate a GET_DEVICE_INTERNAL_STATUS_DATA_REQUEST structure, then
// initialize it with a data header request:
//   request.Version = sizeof(GET_DEVICE_INTERNAL_STATUS_DATA_REQUEST);
//   request.Size = sizeof(GET_DEVICE_INTERNAL_STATUS_DATA_REQUEST);
//   request.RequestDataType = DeviceCurrentInternalStatusDataHeader;

// Allocate a DEVICE_INTERNAL_STATUS_DATA structure in which
// to return the header data, with outputBufferLength set to
// (sizeof(DEVICE_INTERNAL_STATUS_DATA) + 512).

// Get the device internal status data.
BOOL result = TRUE;
ULONG returnedLength = 0;
result = DeviceIoControl(deviceHandle,
            IOCTL_STORAGE_GET_DEVICE_INTERNAL_LOG,
            &request,
            sizeof(GET_DEVICE_INTERNAL_STATUS_DATA_REQUEST),
            &outputBuffer,
            outputBufferLength,
            &returnedLength,
            NULL);

```

## -see-also

[DEVICE_INTERNAL_STATUS_DATA](ns-ntddstor-device_internal_status_data.md)

[GET_DEVICE_INTERNAL_STATUS_DATA_REQUEST](ns-ntddstor-get_device_internal_status_data_request.md)
