---
UID: NF:ntifs.SeLocateProcessImageName
tech.root: ifsk
title: SeLocateProcessImageName
ms.date: 01/06/2025
targetos: Windows
description: Learn more about the SeLocateProcessImageName function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: NtosKrnl.exe
req.header: ntifs.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: NtosKrnl.lib
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
 -HeaderDef
api_location:
 - ntifs.h
api_name:
 - SeLocateProcessImageName
f1_keywords:
 - SeLocateProcessImageName
 - ntifs/SeLocateProcessImageName
dev_langs:
 - c++
helpviewer_keywords:
 - SeLocateProcessImageName
---

## -description

The **SeLocateProcessImageName** routine returns the full process image name for the specified process.

## -parameters

### -param Process

[in/out] Pointer to the process value for which to acquire the name.

### -param pImageFileName

[out] Pointer to an allocated buffer that receives the full image name of the process. The buffer contains a Unicode string followed by the image name string.

## -returns

**SeLocateProcessImageName** returns an NTSTATUS value such as the following.

| Return code | Description |
| ----------- | ----------- |
| STATUS_SUCCESS | The routine successfully returned the process image name. |
| STATUS_NOT_FOUND | The routine could not find the process image name. |

## -remarks

The caller is responsible for freeing the buffer that **pImageFileName** points to, using the **ExFree*Xxx*** routine that corresponds to the routine used to allocate the buffer.

## -see-also

[**ExAllocatePool2**](../wdm/nf-wdm-exallocatepool2.md)

[**ExAllocatePoolWithTag**](../wdm/nf-wdm-exallocatepoolwithtag.md)

[**ExFreePool2**](../wdm/nf-wdm-exfreepool2.md)

[**ExFreePoolWithTag**](../wdm/nf-wdm-exfreepoolwithtag.md)
