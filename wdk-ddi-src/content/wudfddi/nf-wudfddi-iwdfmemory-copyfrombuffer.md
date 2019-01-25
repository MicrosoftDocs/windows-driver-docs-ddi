---
UID: NF:wudfddi.IWDFMemory.CopyFromBuffer
title: IWDFMemory::CopyFromBuffer (wudfddi.h)
description: The CopyFromBuffer method safely copies data from the specified source buffer to a memory object.
old-location: wdf\iwdfmemory_copyfrombuffer.htm
tech.root: wdf
ms.assetid: d8e56186-f801-4684-8919-236d2429310f
ms.date: 02/26/2018
ms.keywords: CopyFromBuffer, CopyFromBuffer method, CopyFromBuffer method,IWDFMemory interface, IWDFMemory interface,CopyFromBuffer method, IWDFMemory.CopyFromBuffer, IWDFMemory::CopyFromBuffer, UMDFMemoryObjectRef_ca676a5f-0dba-423a-9013-3bb95974371a.xml, umdf.iwdfmemory_copyfrombuffer, wdf.iwdfmemory_copyfrombuffer, wudfddi/IWDFMemory::CopyFromBuffer
ms.topic: method
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFMemory.CopyFromBuffer
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFMemory::CopyFromBuffer


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CopyFromBuffer</b> method safely copies data from the specified source buffer to a memory object.


## -parameters




### -param DestOffset [in]

The offset, in bytes, into the memory object to start to copy data to.


### -param SourceBuffer




### -param NumOfBytesToCopyFrom [in]

The number of bytes to copy from the buffer that <i>pSourceBuffer</i> points to.


#### - pSourceBuffer [in]

A pointer to the source buffer that data is copied from.


## -returns



<b>CopyFromBuffer</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558967">IWDFIoQueue::RetrieveNextRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559249">IWDFMemory</a>
 

 

