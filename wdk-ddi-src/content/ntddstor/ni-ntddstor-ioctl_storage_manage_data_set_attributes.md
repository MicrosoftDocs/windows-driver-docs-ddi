---
UID: NI:ntddstor.IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES
title: IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES (ntddstor.h)
description: This IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES request is used to send a manage data set attributes request to a storage device.
old-location: storage\ioctl_storage_manage_data_set_attributes.htm
tech.root: storage
ms.assetid: 678bbca6-f21f-480a-897d-a30e922d01e3
ms.date: 08/15/2019
ms.keywords: IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES, IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES control, IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES control code [Storage Devices], k307_99edaea9-af25-4aba-ba16-0758c63252b6.xml, ntddstor/IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES, storage.ioctl_storage_manage_data_set_attributes
ms.topic: ioctl
f1_keywords:
 - "ntddstor/IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES"
req.header: ntddstor.h
req.include-header: Ntddstor.h
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
req.irql: IRQL < DISPATCH_LEVEL (See Remarks section.)
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddstor.h
api_name:
- IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES IOCTL

## -description

This IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES request is used to send a data set attributes management request to a storage device.

## -ioctlparameters

### -input-buffer

The buffer at *Irp->AssociatedIrp.SystemBuffer* contains a [DEVICE_DSM_INPUT](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_device_manage_data_set_attributes) structure. Note that the buffer may include parameter and data set range blocks. Also, the **Action** member of this structure defines the action to be performed as a DEVICE_DSM_ACTION value.

### -input-buffer-length

*Parameters.DeviceIoControl.InputBufferLength* in the I/O stack location of the IRP indicates the size, in bytes, of the buffer, which must be at least **sizeof**(DEVICE_DSM_INPUT).

### -output-buffer

Depending on the value set in the **Action** member of DEVICE_DSM_INPUT, the request may return data in a [DEVICE_DSM_OUTPUT](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_device_manage_data_set_attributes_output) structure in the buffer at *Irp->AssociatedIrp.UserBuffer*. This buffer will contain valid data if the manage data set action operation returns output and *Parameters.DeviceIoControl.OutputBufferLength* > 0.

### -output-buffer-length

The length of DEVICE_DSM_OUTPUT, in bytes.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The **Status** field can be set to STATUS_SUCCESS, or possibly to STATUS_INVALID_DEVICE_REQUEST, STATUS_BUFFER_TOO_SMALL, STATUS_BUFFER_OVERFLOW, or some other error status.

## -remarks

See [DEVICE_DSM_ACTION Descriptions](https://docs.microsoft.com/windows-hardware/drivers/storage/device-dsm-action-descriptions) for descriptions of the DEVICE_DSM_ACTION constants.

Due to memory pool requirements by the storage driver stack, completion of the IRP containing this IOCTL must be at IRQL < DISPATCH_LEVEL.

## -see-also

[DEVICE_DSM_ACTION Descriptions](https://docs.microsoft.com/windows-hardware/drivers/storage/device-dsm-action-descriptions)

[DEVICE_DSM_INPUT](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_device_manage_data_set_attributes)

[DEVICE_DSM_OUTPUT](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_device_manage_data_set_attributes_output)
