---
UID: NI:ntddstor.IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES
title: IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES (ntddstor.h)
description: This IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES request is used to send a data set management request to a storage device.
old-location: storage\ioctl_storage_manage_data_set_attributes.htm
tech.root: storage
ms.assetid: 678bbca6-f21f-480a-897d-a30e922d01e3
ms.date: 08/23/2019
keywords: ["IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES IOCTL"]
ms.keywords: IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES, IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES control, IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES control code [Storage Devices], k307_99edaea9-af25-4aba-ba16-0758c63252b6.xml, ntddstor/IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES, storage.ioctl_storage_manage_data_set_attributes
f1_keywords:
 - "ntddstor/IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES"
 - "IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES"
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

This **IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES** request is used to send a data set management request to a storage device.

## -ioctlparameters

### -input-buffer

The buffer at *Irp->AssociatedIrp.SystemBuffer* contains a [DEVICE_DSM_INPUT](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_device_manage_data_set_attributes) structure. Depending on the **Action** member of this structure, the input buffer might additionally include a parameter block and block of data set ranges. See [DEVICE_DSM_ACTION Descriptions](https://docs.microsoft.com/windows-hardware/drivers/storage/device-dsm-action-descriptions) for descriptions of all possible actions.

### -input-buffer-length

*Parameters.DeviceIoControl.InputBufferLength* in the I/O stack location of the IRP indicates the size, in bytes, of the buffer, which must be at least **sizeof**([DEVICE_DSM_INPUT](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_device_manage_data_set_attributes)).

### -output-buffer

Depending on the value set in the **Action** member of DEVICE_DSM_INPUT, the request may return data in the buffer at *Irp->AssociatedIrp.SystemBuffer*. The system buffer will contain valid [DEVICE_DSM_OUTPUT](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_device_manage_data_set_attributes_output) data if the DSM operation returns output and *Parameters.DeviceIoControl.OutputBufferLength* > 0. Depending on **Action**, the output buffer might additionally include an output block.

### -output-buffer-length

The length in bytes of the output buffer, if any. If output is returned, the output buffer must be at least **sizeof**([DEVICE_DSM_OUTPUT](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_device_manage_data_set_attributes_output)).

### -in-out-buffer

### -inout-buffer-length

### -status-block

The **Status** field can be set to STATUS_SUCCESS, or possibly to STATUS_INVALID_DEVICE_REQUEST, STATUS_BUFFER_TOO_SMALL, STATUS_BUFFER_OVERFLOW, or some other error status.

## -remarks

Due to memory pool requirements by the storage driver stack, completion of the IRP containing this IOCTL must be at IRQL < DISPATCH_LEVEL.

See [Data Set Management Overview](https://docs.microsoft.com/windows-hardware/drivers/storage/data-set-management-overview) for more information.

## -see-also

[Data Set Management Overview](https://docs.microsoft.com/windows-hardware/drivers/storage/data-set-management-overview)

[DEVICE_DSM_ACTION Descriptions](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdd)

[DEVICE_DSM_INPUT](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_device_manage_data_set_attributes)

[DEVICE_DSM_OUTPUT](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_device_manage_data_set_attributes_output)
