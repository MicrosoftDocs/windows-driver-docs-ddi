---
UID: NS:ntifs._FSCTL_OFFLOAD_WRITE_INPUT
title: FSCTL_OFFLOAD_WRITE_INPUT (ntifs.h)
description: Learn more about the FSCTL_OFFLOAD_WRITE_INPUT structure.
tech.root: ifsk
ms.date: 07/06/2023
keywords: ["FSCTL_OFFLOAD_WRITE_INPUT structure"]
ms.keywords: "*PFSCTL_OFFLOAD_WRITE_INPUT, FSCTL_OFFLOAD_WRITE_INPUT, FSCTL_OFFLOAD_WRITE_INPUT structure [Installable File System Drivers], PFSCTL_OFFLOAD_WRITE_INPUT, PFSCTL_OFFLOAD_WRITE_INPUT structure pointer [Installable File System Drivers], _FSCTL_OFFLOAD_WRITE_INPUT, ifsk.fsctl_offload_write_input, ntifs/FSCTL_OFFLOAD_WRITE_INPUT, ntifs/PFSCTL_OFFLOAD_WRITE_INPUT"
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
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
req.typenames: FSCTL_OFFLOAD_WRITE_INPUT, *PFSCTL_OFFLOAD_WRITE_INPUT
f1_keywords:
 - _FSCTL_OFFLOAD_WRITE_INPUT
 - ntifs/_FSCTL_OFFLOAD_WRITE_INPUT
 - PFSCTL_OFFLOAD_WRITE_INPUT
 - ntifs/PFSCTL_OFFLOAD_WRITE_INPUT
 - FSCTL_OFFLOAD_WRITE_INPUT
 - ntifs/FSCTL_OFFLOAD_WRITE_INPUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FSCTL_OFFLOAD_WRITE_INPUT
 - PFSCTL_OFFLOAD_WRITE_INPUT
 - FSCTL_OFFLOAD_WRITE_INPUT
---

# FSCTL_OFFLOAD_WRITE_INPUT structure

## -description

The **FSCTL_OFFLOAD_WRITE_INPUT** structure contains the input for the [**FSCTL_OFFLOAD_WRITE**](/windows-hardware/drivers/ifs/fsctl-offload-write) control code request.

## -struct-fields

### -field Size

The size of this structure. Set this member to ```sizeof(FSCTL_OFFLOAD_WRITE_INPUT)```.

### -field Flags

 This member is not used. Set to 0.

### -field FileOffset

 The position in the file to begin writing to. The offset value must be aligned to a logical sector boundary on the volume.

### -field CopyLength

 The length, in bytes, of data to write, starting at **FileOffset**. The length  value must align to a logical sector boundary on the volume, except when the length matches end-of-file.

### -field TransferOffset

 The position in the data associated with **Token** to begin writing from.

### -field Token

A byte array that contains a [**STORAGE_OFFLOAD_TOKEN**](../ntddstor/ns-ntddstor-_storage_offload_token.md) token structure that represents a file data range to be logically written. The contents of **Token**  must remain unmodified between offload operations.

## -remarks

**CopyLength** can be zero. The value of **FileOffset** + **CopyLength** is bounded by both **MAXULONGLONG** and **MAXFILESIZE**. [**FSCTL_OFFLOAD_WRITE**](/windows-hardware/drivers/ifs/fsctl-offload-write) returns with **STATUS_INVALID_PARAMETER** if these conditions are not met.

## -see-also

[**FSCTL_OFFLOAD_READ**](/windows-hardware/drivers/ifs/fsctl-offload-read)

[**FSCTL_OFFLOAD_WRITE**](/windows-hardware/drivers/ifs/fsctl-offload-write)

[**FSCTL_OFFLOAD_WRITE_OUTPUT**](ns-ntifs-_fsctl_offload_write_output.md)

[**STORAGE_OFFLOAD_TOKEN**](../ntddstor/ns-ntddstor-_storage_offload_token.md)
