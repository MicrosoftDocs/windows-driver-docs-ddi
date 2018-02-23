---
UID: NF:wudfddi.IWDFMemory.CopyFromBuffer
title: IWDFMemory::CopyFromBuffer method
author: windows-driver-content
description: The CopyFromBuffer method safely copies data from the specified source buffer to a memory object.
old-location: wdf\iwdfmemory_copyfrombuffer.htm
old-project: wdf
ms.assetid: d8e56186-f801-4684-8919-236d2429310f
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: IWDFMemory::CopyFromBuffer, wudfddi/IWDFMemory::CopyFromBuffer, UMDFMemoryObjectRef_ca676a5f-0dba-423a-9013-3bb95974371a.xml, IWDFMemory interface, CopyFromBuffer method, CopyFromBuffer method, CopyFromBuffer method, IWDFMemory interface, CopyFromBuffer, wdf.iwdfmemory_copyfrombuffer, umdf.iwdfmemory_copyfrombuffer, IWDFMemory
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: wudfddi.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFMemory.CopyFromBuffer
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFMemory::CopyFromBuffer method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CopyFromBuffer</b> method safely copies data from the specified source buffer to a memory object.


## -syntax


````
HRESULT CopyFromBuffer(
  [in] ULONG_PTR DestOffset,
  [in] void      *pSourceBuffer,
  [in] SIZE_T    NumOfBytesToCopyFrom
);
````


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

<a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558967">IWDFIoQueue::RetrieveNextRequest</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFMemory::CopyFromBuffer method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

