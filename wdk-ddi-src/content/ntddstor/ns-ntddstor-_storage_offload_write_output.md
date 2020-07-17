---
UID: NS:ntddstor._STORAGE_OFFLOAD_WRITE_OUTPUT
title: _STORAGE_OFFLOAD_WRITE_OUTPUT (ntddstor.h)
description: The STORAGE_OFFLOAD_WRITE_OUTPUT structure is the output of an IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES control code request when the Action member of DEVICE_MANAGE_DATA_SET_ATTRIBUTES is set to DeviceDsmAction_OffloadWrite.
old-location: storage\storage_offload_write_output.htm
tech.root: storage
ms.assetid: 95EF1722-5171-4A09-8676-7910E53E3868
ms.date: 08/23/2019
keywords: ["_STORAGE_OFFLOAD_WRITE_OUTPUT structure"]
ms.keywords: "*PSTORAGE_OFFLOAD_WRITE_OUTPUT, PSTORAGE_OFFLOAD_WRITE_OUTPUT, PSTORAGE_OFFLOAD_WRITE_OUTPUT structure pointer [Storage Devices], STORAGE_OFFLOAD_TOKEN_INVALID, STORAGE_OFFLOAD_WRITE_OUTPUT, STORAGE_OFFLOAD_WRITE_OUTPUT structure [Storage Devices], STORAGE_OFFLOAD_WRITE_RANGE_TRUNCATED, _STORAGE_OFFLOAD_WRITE_OUTPUT, ntddstor/PSTORAGE_OFFLOAD_WRITE_OUTPUT, ntddstor/STORAGE_OFFLOAD_WRITE_OUTPUT, storage.storage_offload_write_output"
f1_keywords:
 - "ntddstor/STORAGE_OFFLOAD_WRITE_OUTPUT"
 - "STORAGE_OFFLOAD_WRITE_OUTPUT"
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
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
- ntddstor.h
api_name:
- STORAGE_OFFLOAD_WRITE_OUTPUT
product:
- Windows
targetos: Windows
req.typenames: STORAGE_OFFLOAD_WRITE_OUTPUT, *PSTORAGE_OFFLOAD_WRITE_OUTPUT
---

# _STORAGE_OFFLOAD_WRITE_OUTPUT structure

## -description

The STORAGE_OFFLOAD_WRITE_OUTPUT structure is the output of an [IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_manage_data_set_attributes) control code request when the **Action** member of [DEVICE_DSM_INPUT](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_device_manage_data_set_attributes) is set to **DeviceDsmAction_OffloadWrite**.

## -struct-fields

### -field OffloadWriteFlags

Flags indicating the result of the offload write operation. This is set to one of the following.

| Value | Meaning |
| ----- | ------- |
| STORAGE_OFFLOAD_WRITE_RANGE_TRUNCATED | The offload write was performed but the range written was truncated. |
| STORAGE_OFFLOAD_TOKEN_INVALID | The token provided for the offload write operation was invalid. |

### -field Reserved

Reserved.

### -field LengthCopied

Bytes copied for the write request in DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS.

## -remarks

On input, a token value in [DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_device_dsm_offload_write_parameters) uniquely identifies the data set ranges requested for writing in the DEVICE_DSM_INPUT structure. The STORAGE_OFFLOAD_WRITE_OUTPUT structure contains the results of the write operation.

The STORAGE_OFFLOAD_WRITE_OUTPUT structure is returned at the beginning of the system buffer.

## -see-also

[DEVICE_DSM_INPUT](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_device_manage_data_set_attributes)

[DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_device_dsm_offload_write_parameters)

[IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_manage_data_set_attributes)
