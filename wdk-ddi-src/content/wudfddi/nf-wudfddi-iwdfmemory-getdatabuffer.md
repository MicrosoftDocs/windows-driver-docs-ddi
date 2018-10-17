---
UID: NF:wudfddi.IWDFMemory.GetDataBuffer
title: IWDFMemory::GetDataBuffer
author: windows-driver-content
description: The GetDataBuffer method retrieves the data buffer that is associated with a memory object.
old-location: wdf\iwdfmemory_getdatabuffer.htm
tech.root: wdf
ms.assetid: 136aa2af-e3bf-48b6-9511-348510eedfb5
ms.date: 2/26/2018
ms.keywords: GetDataBuffer, GetDataBuffer method, GetDataBuffer method,IWDFMemory interface, IWDFMemory interface,GetDataBuffer method, IWDFMemory.GetDataBuffer, IWDFMemory::GetDataBuffer, UMDFMemoryObjectRef_910791a8-4fd9-47ff-93f9-f8f496e95272.xml, umdf.iwdfmemory_getdatabuffer, wdf.iwdfmemory_getdatabuffer, wudfddi/IWDFMemory::GetDataBuffer
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
-	IWDFMemory.GetDataBuffer
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFMemory::GetDataBuffer


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetDataBuffer</b> method retrieves the data buffer that is associated with a memory object.


## -parameters




### -param BufferSize






#### - pBufferSize [out, optional]

A pointer to a variable that receives information that describes the size of the data buffer.

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


## -returns



<b>GetDataBuffer</b> returns a pointer to the data buffer.




## -remarks



For a code example of how to use the <b>GetDataBuffer</b> method, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558892">IWDFDevice::SetPnpState</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559249">IWDFMemory</a>
 

 

