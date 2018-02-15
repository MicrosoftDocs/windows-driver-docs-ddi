---
UID: NF:wudfddi.IWDFMemory.SetBuffer
title: IWDFMemory::SetBuffer method
author: windows-driver-content
description: The SetBuffer method assigns a specified buffer to a memory object that a driver created by calling IWDFDriver::CreatePreallocatedWdfMemory.
old-location: wdf\iwdfmemory_setbuffer.htm
old-project: wdf
ms.assetid: 1399922d-684c-44a4-8bc7-b9e45ba05086
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.iwdfmemory_setbuffer, SetBuffer method, IWDFMemory interface, IWDFMemory, IWDFMemory interface, SetBuffer method, SetBuffer method, IWDFMemory::SetBuffer, wudfddi/IWDFMemory::SetBuffer, UMDFMemoryObjectRef_34339a6a-7426-46fc-8df9-7f5281b03308.xml, SetBuffer, umdf.iwdfmemory_setbuffer
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
-	IWDFMemory.SetBuffer
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IWDFMemory::SetBuffer method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>SetBuffer</b> method assigns a specified buffer to a memory object that a driver created by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff558902">IWDFDriver::CreatePreallocatedWdfMemory</a>. 


## -syntax


````
void SetBuffer(
  [in] void   *Buffer,
  [in] SIZE_T BufferSize
);
````


## -parameters




### -param Buffer [in]

A pointer to a driver-supplied buffer.


### -param BufferSize [in]

The nonzero size, in bytes, of the buffer that <i>Buffer</i> points to. 


## -returns



None




## -remarks



The <b>SetBuffer</b> method can assign a buffer to a memory object that <a href="https://msdn.microsoft.com/library/windows/hardware/ff558902">IWDFDriver::CreatePreallocatedWdfMemory</a> created, but not to a memory object that <a href="https://msdn.microsoft.com/library/windows/hardware/ff558905">IWDFDriver::CreateWdfMemory</a> created.




## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558967">IWDFIoQueue::RetrieveNextRequest</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFMemory::SetBuffer method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

