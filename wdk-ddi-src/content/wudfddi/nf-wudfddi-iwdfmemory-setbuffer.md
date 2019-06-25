---
UID: NF:wudfddi.IWDFMemory.SetBuffer
title: IWDFMemory::SetBuffer (wudfddi.h)
description: The SetBuffer method assigns a specified buffer to a memory object that a driver created by calling IWDFDriver::CreatePreallocatedWdfMemory.
old-location: wdf\iwdfmemory_setbuffer.htm
tech.root: wdf
ms.assetid: 1399922d-684c-44a4-8bc7-b9e45ba05086
ms.date: 02/26/2018
ms.keywords: IWDFMemory interface,SetBuffer method, IWDFMemory.SetBuffer, IWDFMemory::SetBuffer, SetBuffer, SetBuffer method, SetBuffer method,IWDFMemory interface, UMDFMemoryObjectRef_34339a6a-7426-46fc-8df9-7f5281b03308.xml, umdf.iwdfmemory_setbuffer, wdf.iwdfmemory_setbuffer, wudfddi/IWDFMemory::SetBuffer
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFMemory.SetBuffer
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFMemory::SetBuffer


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>SetBuffer</b> method assigns a specified buffer to a memory object that a driver created by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfdriver-createpreallocatedwdfmemory">IWDFDriver::CreatePreallocatedWdfMemory</a>. 


## -parameters




### -param Buffer [in]

A pointer to a driver-supplied buffer.


### -param BufferSize [in]

The nonzero size, in bytes, of the buffer that <i>Buffer</i> points to. 


## -returns



None




## -remarks



The <b>SetBuffer</b> method can assign a buffer to a memory object that <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfdriver-createpreallocatedwdfmemory">IWDFDriver::CreatePreallocatedWdfMemory</a> created, but not to a memory object that <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfdriver-createwdfmemory">IWDFDriver::CreateWdfMemory</a> created.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfioqueue-retrievenextrequest">IWDFIoQueue::RetrieveNextRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfmemory">IWDFMemory</a>
 

 

