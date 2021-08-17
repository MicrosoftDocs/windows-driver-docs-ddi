---
UID: NF:fltkernel.FltVetoBypassIo
tech.root: ifsk
title: FltVetoBypassIo
ms.date: 08/12/2021
targetos: Windows
description: FltVetoBypassIo retrieves information needed to veto a BypassIO request.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: fltkernel.h
req.idl: 
req.include-header: 
req.irql: <= APC_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - fltkernel.h
api_name:
 - FltVetoBypassIo
f1_keywords:
 - FltVetoBypassIo
 - fltkernel/FltVetoBypassIo
dev_langs:
 - c++
---

## -description

**FltVetoBypassIo** retrieves information needed to veto a BypassIO request.

## -parameters

### -param CallbackData

[in] Pointer to the [**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md) for [**FSCTL_MANAGE_BYPASS_IO**](../ntifs/ni-ntifs-fsctl_manage_bypass_io.md).

### -param FltObjects

[in] Pointer to the [**FLT_RELATED_OBJECTS**](ns-fltkernel-_flt_related_objects.md) structure for the BypassIO operation.

### -param OperationStatus

[in] The NTSTATUS error code provided by the filter for the veto.

### -param FailureReason

[in] A unique, descriptive string that provides details about why the filter is vetoing the BypassIO enable request.

## -returns

**FltVetoBypassIo** returns STATUS_SUCCESS upon successful completion; otherwise, it returns one of the following values.

| Value | Meaning |
| ----- | ------- |
| STATUS_BUFFER_TOO_SMALL    | The FSCTL's [output buffer](../ntifs/ns-ntifs-fs_bpio_output.md) is too small. |
| STATUS_INVALID_BUFFER_SIZE | The FSCTL's [input buffer](../ntifs/ns-ntifs-fs_bpio_input.md) is too small. |
| STATUS_INVALID_PARAMETER_3 | An appropriate error code was not provided. |
| STATUS_INVALID_PARAMETER_4 | An appropriate failure reason was not provided. |

## -remarks

A minifilter calls **FltVetoBypassIo** when it intends to veto a BypassIo [enable or query request](../ntifs/ne-ntifs-fs_bpio_operations.md) on a file.

See [BypassIO for filter drivers](/windows-hardware/drivers/ifs/bypassio) for more information.

## -see-also

[**FS_BPIO_OPERATIONS**](../ntifs/ne-ntifs-fs_bpio_operations.md)

[**FSCTL_MANAGE_BYPASS_IO**](../ntifs/ni-ntifs-fsctl_manage_bypass_io.md)
