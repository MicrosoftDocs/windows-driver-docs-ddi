---
UID: NI:ntddstor.IOCTL_STORAGE_SET_PROPERTY
title: IOCTL_STORAGE_SET_PROPERTY (ntddstor.h)
description: A driver can use IOCTL_STORAGE_SET_PROPERTY to set the properties of a storage device or adapter.
tech.root: storage
ms.date: 07/12/2019
keywords: ["IOCTL_STORAGE_SET_PROPERTY IOCTL"]
req.header: ntddstor.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.max-support: 
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - IOCTL_STORAGE_SET_PROPERTY
 - ntddstor/IOCTL_STORAGE_SET_PROPERTY
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - IOCTL_STORAGE_SET_PROPERTY
---

# IOCTL_STORAGE_SET_PROPERTY IOCTL

### Major Code:  [IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description

A driver can use IOCTL_STORAGE_SET_PROPERTY to set the properties of a storage device or adapter.

> [!NOTE]
> Due to colliding IOCTL definitions, existing software that uses IOCTL_STORAGE_SET_PROPERTY will need to be recompiled on the next version of Windows 10 after version 2004.

## -ioctlparameters

### -input-buffer

Contains a [STORAGE_PROPERTY_SET](ns-ntddstor-storage_property_set.md) structure that describes the type of set being done, the property being set, and any additional parameters that a particular property set requires. A structure with additional properties can be found immediately after the STORAGE_PROPERTY_SET structure, depending on STORAGE_PROPERTY_SET's **PropertyId**. For example, if **PropertyId** is **StorageAdapterProtocolSpecificProperty**, then a [STORAGE_PROTOCOL_SPECIFIC_DATA_EXT](ns-ntddstor-storage_protocol_specific_data_ext.md) structure immediately follows STORAGE_PROPERTY_SET.

### -input-buffer-length

**Parameters.DeviceIoControl.InputBufferLength** indicates the size, in bytes, of the parameter buffer at **Irp->AssociatedIrp.SystemBuffer**, which must be >= sizeof(STORAGE_PROPERTY_SET).

### -output-buffer

Depends on the specified **PropertyId**. For example, if **PropertyId** is **StorageAdapterProtocolSpecificProperty**, then the output buffer contains a STORAGE_PROTOCOL_SPECIFIC_DATA_EXT structure with updated data from the miniport.

### -output-buffer-length

Size, in bytes, of the output buffer.

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.
Otherwise, Status to the appropriate error condition as a NTSTATUS code.
For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

## -see-also

[STORAGE_PROPERTY_SET](ns-ntddstor-storage_property_set.md)

[STORAGE_PROTOCOL_SPECIFIC_DATA_EXT](ns-ntddstor-storage_protocol_specific_data_ext.md)

[STORAGE_SET_TYPE](ne-ntddstor-storage_set_type.md)
