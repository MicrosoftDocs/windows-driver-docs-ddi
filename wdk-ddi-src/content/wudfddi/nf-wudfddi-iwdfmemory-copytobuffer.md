---
UID: NF:wudfddi.IWDFMemory.CopyToBuffer
title: IWDFMemory::CopyToBuffer (wudfddi.h)
description: The CopyToBuffer method safely copies data from a memory object to the specified target buffer.
old-location: wdf\iwdfmemory_copytobuffer.htm
tech.root: wdf
ms.date: 08/12/2022
keywords: ["IWDFMemory::CopyToBuffer"]
ms.keywords: CopyToBuffer, CopyToBuffer method, CopyToBuffer method,IWDFMemory interface, IWDFMemory interface,CopyToBuffer method, IWDFMemory.CopyToBuffer, IWDFMemory::CopyToBuffer, UMDFMemoryObjectRef_40ff2a7e-f93c-4f95-ba14-b7ade765ab2d.xml, umdf.iwdfmemory_copytobuffer, wdf.iwdfmemory_copytobuffer, wudfddi/IWDFMemory::CopyToBuffer
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFMemory::CopyToBuffer
 - wudfddi/IWDFMemory::CopyToBuffer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFMemory::CopyToBuffer
---

# IWDFMemory::CopyToBuffer

## -description

> [!WARNING]
> UMDF 2 is the latest version of UMDF and supersedes UMDF 1. All new UMDF drivers should be written using UMDF 2. No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10. Universal Windows drivers must use UMDF 2. For more info, see [Getting Started with UMDF](/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2).

The **CopyToBuffer** method safely copies data from a memory object to the specified target buffer.

## -parameters

### -param SourceOffset [in]

The offset, in bytes, into the memory object from which to start copying data.

### -param TargetBuffer [out]

A pointer to the target buffer to which data is copied.

### -param NumOfBytesToCopyTo [in]

The number of bytes to copy to the *TargetBuffer*.

## -returns

**CopyToBuffer** returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.

## -see-also

- [IWDFMemory](./nn-wudfddi-iwdfmemory.md)
