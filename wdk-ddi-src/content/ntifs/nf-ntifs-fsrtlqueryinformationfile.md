---
UID: NF:ntifs.FsRtlQueryInformationFile
tech.root: ifs
title: FsRtlQueryInformationFile
ms.date: 08/11/2022
targetos: Windows
description: Learn more about the FsRtlQueryInformationFile function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
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
 - ntifs.h
api_name:
 - FsRtlQueryInformationFile
f1_keywords:
 - FsRtlQueryInformationFile
 - ntifs/FsRtlQueryInformationFile
dev_langs:
 - c++
helpviewer_keywords:
 - FsRtlQueryInformationFile
---

## -description

**FsRtlQueryInformationFile** builds an explicit file query information IRP (IRP_MJ_QUERY_INFORMATION), sends it down the stack, synchronously waits for it to complete, and returns the result. This function allows the caller to complete this action by **FileObject** instead of handle.

## -parameters

### -param FileObject [in]

Pointer to the [**FILE_OBJECT**](../wdm/ns-wdm-_file_object.md) to send the operation on.

### -param FileInformation [out]

Pointer to a caller-allocated buffer to receive the queried file information.

### -param Length [in]

Size in bytes of the buffer that **FileInformation** points to.

### -param FileInformationClass [in]

A [**FILE_INFORMATION_CLASS**](../wdm/ne-wdm-_file_information_class.md) value that specifies the type of file information being queried.

### -param RetFileInformationSize [out]

Receives the number of bytes written (returned) into the buffer that **FileInformation** points to.

## -returns

**FsRtlKernelFsControlFile** returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following.

| Value | Meaning |
| ----- | ------- |
| STATUS_INSUFFICIENT_RESOURCES | A pool allocation failure occurred. |
| STATUS_INVALID_PARAMETER      | An invalid parameter was provided (for example, an invalid **FileObject**). |

## -remarks

This routine assumes all passed in buffers are kernel mode buffers.

## -see-also

[**ZwQueryInformationFile**](../wdm/nf-wdm-zwqueryinformationfile.md)
