---
UID: NF:wudfddi.IWDFMemory.CopyFromMemory
title: IWDFMemory::CopyFromMemory (wudfddi.h)
description: The CopyFromMemory method safely copies data from the specified source buffer and prevents overruns that the copy operation might otherwise cause.
old-location: wdf\iwdfmemory_copyfrommemory.htm
tech.root: wdf
ms.assetid: 29b77215-9c7e-47f2-8c94-0bcd733f54a2
ms.date: 02/26/2018
ms.keywords: CopyFromMemory, CopyFromMemory method, CopyFromMemory method,IWDFMemory interface, IWDFMemory interface,CopyFromMemory method, IWDFMemory.CopyFromMemory, IWDFMemory::CopyFromMemory, UMDFMemoryObjectRef_c5bc961a-62e9-4692-bbd7-6551b268b08b.xml, umdf.iwdfmemory_copyfrommemory, wdf.iwdfmemory_copyfrommemory, wudfddi/IWDFMemory::CopyFromMemory
ms.topic: method
f1_keywords:
 - "wudfddi/IWDFMemory.CopyFromMemory"
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
- IWDFMemory.CopyFromMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFMemory::CopyFromMemory


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CopyFromMemory</b> method safely copies data from the specified source buffer and prevents overruns that the copy operation might otherwise cause.


## -parameters




### -param Source




### -param SourceOffset






#### - pSource [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfmemory">IWDFMemory</a> interface for the memory object that is the source of the copy operation.


#### - pSourceOffset [in, optional]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi_types/ns-wudfddi_types-_wdfmemory_offset">WDFMEMORY_OFFSET</a> structure that describes the information that is copied from a memory block. This parameter is optional. The driver can pass <b>NULL</b> if the entire source buffer is copied. 

The <b>BufferOffset</b> member of the WDFMEMORY_OFFSET structure, if not <b>NULL</b>, indicates the offset into the source buffer to start the copy operation from. 

The <b>BufferLength</b> member should be set to 0; the framework ignores this member because the amount of data that is copied depends on the length and offset combination of the current destination buffer. 


## -returns



<b>CopyFromMemory</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfmemory">IWDFMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi_types/ns-wudfddi_types-_wdfmemory_offset">WDFMEMORY_OFFSET</a>
 

 

