---
UID: NF:ntifs.ZwQueryEaFile
title: ZwQueryEaFile function (ntifs.h)
description: Learn more about the ZwQueryEaFile function.
tech.root: kernel
ms.date: 04/25/2024
keywords: ["ZwQueryEaFile function"]
ms.keywords: ZwQueryEaFile, ZwQueryEaFile routine [Kernel-Mode Driver Architecture], kernel.zwqueryeafile, ntifs/ZwQueryEaFile
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
 - ZwQueryEaFile
 - ntifs/ZwQueryEaFile
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwQueryEaFile
---

# ZwQueryEaFile function (ntifs.h)



## -description

**ZwQueryEaFile** routine returns the extended attributes (EAs) associated with the specified file.

## -parameters

### -param FileHandle [in]

The handle for the file on which the operation is to be performed.

### -param IoStatusBlock [out]

A pointer to an [**IO_STATUS_BLOCK**](../wdm/ns-wdm-_io_status_block.md) structure that receives the final completion status and other information about the requested operation.

### -param Buffer [out]

A pointer to a caller-supplied [**FILE_FULL_EA_INFORMATION**](../wdm/ns-wdm-_file_full_ea_information.md)-structured output buffer in which to return the file's EAs.

### -param Length [in]

The length, in bytes, of the buffer that **Buffer** points to.

### -param ReturnSingleEntry [in]

Set to TRUE if **ZwQueryEaFile** should return only the first entry that it finds.

### -param EaList [in, optional]

A pointer to a caller-supplied [**FILE_GET_EA_INFORMATION**](ns-ntifs-_file_get_ea_information.md)-structured input buffer that specifies the EAs to be queried. This parameter is optional and can be NULL.

### -param EaListLength [in]

The length, in bytes, of the buffer that the **EaList** parameter points to.

### -param EaIndex [in, optional]

The index of the entry at which scanning the file's EA list should begin. This parameter is ignored if **EaList** points to a nonempty list. This parameter is optional and can be NULL.

### -param RestartScan [in]

Set to TRUE if **ZwQueryEaFile** should begin the scan at the first entry in the file's EA list. If this parameter is set to FALSE, the routine resumes the scan from a previous call to **ZwQueryEaFile**.

## -returns

**ZwQueryEaFile** returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following:

| Return value | Description |
| ------------ | ----------- |
| STATUS_EAS_NOT_SUPPORTED | The file system doesn't support EAs. This is an error code. |
| STATUS_INSUFFICIENT_RESOURCES | There isn't enough memory available to complete the operation. This is an error code. |
| STATUS_EA_LIST_INCONSISTENT | The **EaList** parameter isn't formatted correctly. This is an error code. |

## -remarks

The amount of information that **ZwQueryEaFile** returns is based on the size of the EAs and the size of the buffer that **Buffer** points to. That is, either all of the requested EAs are written to the buffer, or the buffer is filled with as many complete EAs if it's not large enough to contain all the EAs. Only complete EAs are written to the buffer; no partial EAs will ever be returned.

## -see-also

[**FILE_FULL_EA_INFORMATION**](../wdm/ns-wdm-_file_full_ea_information.md)

[**FILE_GET_EA_INFORMATION**](ns-ntifs-_file_get_ea_information.md)

[**ZwSetEaFile**](nf-ntifs-zwseteafile.md)
