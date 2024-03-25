---
UID: NS:ntifs._FSCTL_OFFLOAD_WRITE_OUTPUT
title: FSCTL_OFFLOAD_WRITE_OUTPUT (ntifs.h)
description: Learn more about the FSCTL_OFFLOAD_WRITE_OUTPUT structure.
tech.root: ifsk
ms.date: 07/06/2023
keywords: ["FSCTL_OFFLOAD_WRITE_OUTPUT structure"]
ms.keywords: "*PFSCTL_OFFLOAD_WRITE_OUTPUT, FSCTL_OFFLOAD_WRITE_OUTPUT, FSCTL_OFFLOAD_WRITE_OUTPUT structure [Installable File System Drivers], OFFLOAD_READ_FLAG_FILE_TOO_SMALL, PFSCTL_OFFLOAD_WRITE_OUTPUT, PFSCTL_OFFLOAD_WRITE_OUTPUT structure pointer [Installable File System Drivers], _FSCTL_OFFLOAD_WRITE_OUTPUT, ifsk.fsctl_offload_write_output, ntifs/FSCTL_OFFLOAD_WRITE_OUTPUT, ntifs/PFSCTL_OFFLOAD_WRITE_OUTPUT"
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
req.typenames: FSCTL_OFFLOAD_WRITE_OUTPUT, *PFSCTL_OFFLOAD_WRITE_OUTPUT
f1_keywords:
 - _FSCTL_OFFLOAD_WRITE_OUTPUT
 - ntifs/_FSCTL_OFFLOAD_WRITE_OUTPUT
 - PFSCTL_OFFLOAD_WRITE_OUTPUT
 - ntifs/PFSCTL_OFFLOAD_WRITE_OUTPUT
 - FSCTL_OFFLOAD_WRITE_OUTPUT
 - ntifs/FSCTL_OFFLOAD_WRITE_OUTPUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FSCTL_OFFLOAD_WRITE_OUTPUT
 - PFSCTL_OFFLOAD_WRITE_OUTPUT
 - FSCTL_OFFLOAD_WRITE_OUTPUT
---

# FSCTL_OFFLOAD_WRITE_OUTPUT structure

## -description

The **FSCTL_OFFLOAD_WRITE_OUTPUT** structure contains the output for the [**FSCTL_OFFLOAD_WRITE**](/windows-hardware/drivers/ifs/fsctl-offload-write) control code request.

## -struct-fields

### -field Size

The size in bytes of this structure. Set this member to ```sizeof(FSCTL_OFFLOAD_WRITE_OUTPUT)```.

### -field Flags

Result flags for the offload write operation. This value is either 0 or the following:

| Value | Meaning |
| ----- | ------- |
| OFFLOAD_READ_FLAG_FILE_TOO_SMALL | The file to write to is too small for an offload operation. |

### -field LengthWritten

The length of data written for the transfer specified in [**FSCTL_OFFLOAD_WRITE_INPUT**](ns-ntifs-_fsctl_offload_write_input.md).

## -remarks

 The resulting length written, **LengthWritten**, may be smaller than what was originally specified in the **CopyLength** member of [**FSCTL_OFFLOAD_WRITE_INPUT**](ns-ntifs-_fsctl_offload_write_input.md). A smaller value indicates that less data was able to be logically written with the specified **Token** than was requested.

 If less data than requested was written, the write operation may be completed by performing another [**FSCTL_OFFLOAD_WRITE**](/windows-hardware/drivers/ifs/fsctl-offload-write) request. The next request uses an updated **FileOffset** member in the [**FSCTL_OFFLOAD_WRITE_INPUT**](ns-ntifs-_fsctl_offload_write_input.md) structure with the value in **LengthWritten** and an adjusted write length of the previous length minus the value in **LengthWritten**. An incomplete write operation can also be completed through a non-offloaded write method, such as using the [**ZwWriteFile**](nf-ntifs-ntwritefile.md) routine, for example.

## -see-also

[**FSCTL_OFFLOAD_WRITE**](/windows-hardware/drivers/ifs/fsctl-offload-write)

[**FSCTL_OFFLOAD_WRITE_INPUT**](ns-ntifs-_fsctl_offload_write_input.md)
