---
UID: NF:ntifs.ZwSetEaFile
title: ZwSetEaFile function (ntifs.h)
description: Learn more about the ZwSetEaFile function.
tech.root: kernel
ms.date: 04/25/2024
keywords: ["ZwSetEaFile function"]
ms.keywords: ZwSetEaFile, ZwSetEaFile routine [Kernel-Mode Driver Architecture], kernel.zwseteafile, ntifs/ZwSetEaFile
req.header: ntifs.h
req.construct-type: function
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 2000
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - ZwSetEaFile
 - ntifs/ZwSetEaFile
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwSetEaFile
---

# ZwSetEaFile function (ntifs.h)



## -description

**ZwSetEaFile** replaces the extended attributes (EAs) associated with a file with the specified EAs.

## -parameters

### -param FileHandle [in]

The handle for the file on which the operation is to be performed.

### -param IoStatusBlock [out]

A pointer to an [**IO_STATUS_BLOCK**](../wdm/ns-wdm-_io_status_block.md) structure that receives the final completion status and other information about the requested operation.

### -param Buffer [in]

A pointer to a caller-supplied [**FILE_FULL_EA_INFORMATION**](../wdm/ns-wdm-_file_full_ea_information.md)-structured input buffer that contains the new EAs that will replace the EAs currently associated with the file.

### -param Length [in]

Length, in bytes, of the buffer that the **Buffer** parameter points to.

## -returns

**ZwSetEaFile** returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following:

| Return value | Description |
| ------------ | ----------- |
| STATUS_EA_LIST_INCONSISTENT | The EA list that **Buffer** points to isn't formatted correctly. This is an error code. |
| STATUS_INSUFFICIENT_RESOURCES | There isn't enough memory available to complete the operation. This is an error code. |

## -remarks

**ZwSetEaFile** replaces the EAs associated with **FileHandle** with the EAs in the buffer that **Buffer** points to. The EAs in the buffer must be formatted as a sequence of [**FILE_FULL_EA_INFORMATION**](../wdm/ns-wdm-_file_full_ea_information.md) structures. **ZwSetEaFile** first [checks that the buffer of EA values is valid](nf-ntifs-iocheckeabuffervalidity.md) before replacing the existing EAs.

## -see-also

[**FILE_FULL_EA_INFORMATION**](../wdm/ns-wdm-_file_full_ea_information.md)

[**IoCheckEaBufferValidity**](nf-ntifs-iocheckeabuffervalidity.md)

[**ZwQueryEaFile**](nf-ntifs-zwqueryeafile.md)
