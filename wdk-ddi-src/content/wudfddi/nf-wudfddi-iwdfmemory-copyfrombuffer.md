---
UID: NF:wudfddi.IWDFMemory.CopyFromBuffer
title: IWDFMemory::CopyFromBuffer (wudfddi.h)
description: The CopyFromBuffer method safely copies data from the specified source buffer to a memory object.
old-location: wdf\iwdfmemory_copyfrombuffer.htm
tech.root: wdf
ms.date: 08/12/2022
keywords: ["IWDFMemory::CopyFromBuffer"]
ms.keywords: CopyFromBuffer, CopyFromBuffer method, CopyFromBuffer method,IWDFMemory interface, IWDFMemory interface,CopyFromBuffer method, IWDFMemory.CopyFromBuffer, IWDFMemory::CopyFromBuffer, UMDFMemoryObjectRef_ca676a5f-0dba-423a-9013-3bb95974371a.xml, umdf.iwdfmemory_copyfrombuffer, wdf.iwdfmemory_copyfrombuffer, wudfddi/IWDFMemory::CopyFromBuffer
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
 - IWDFMemory::CopyFromBuffer
 - wudfddi/IWDFMemory::CopyFromBuffer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFMemory::CopyFromBuffer
---

# IWDFMemory::CopyFromBuffer

## -description

> [!WARNING]
> UMDF 2 is the latest version of UMDF and supersedes UMDF 1. All new UMDF drivers should be written using UMDF 2. No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10. Universal Windows drivers must use UMDF 2. For more info, see [Getting Started with UMDF](/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2).

The **CopyFromBuffer** method safely copies data from the specified source buffer to a memory object.

## -parameters

### -param DestOffset [in]

The offset, in bytes, into the memory object to start to copy data to.

### -param SourceBuffer [in]

A pointer to the source buffer that data is copied from.

### -param NumOfBytesToCopyFrom [in]

The number of bytes to copy from the *SourceBuffer*.

## -returns

**CopyFromBuffer** returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.

## -see-also

- [IWDFIoQueue::RetrieveNextRequest](./nf-wudfddi-iwdfioqueue-retrievenextrequest.md)
- [IWDFMemory](./nn-wudfddi-iwdfmemory.md)
