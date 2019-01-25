---
UID: NF:wudfddi.IWDFIoQueue.GetDevice
title: IWDFIoQueue::GetDevice (wudfddi.h)
description: The GetDevice method retrieves the interface to the device that owns the I/O queue.
old-location: wdf\iwdfioqueue_getdevice.htm
tech.root: wdf
ms.assetid: e1c1a67e-a18d-4eef-88ce-cd7edd371f54
ms.date: 02/26/2018
ms.keywords: GetDevice, GetDevice method, GetDevice method,IWDFIoQueue interface, IWDFIoQueue interface,GetDevice method, IWDFIoQueue.GetDevice, IWDFIoQueue::GetDevice, UMDFQueueObjectRef_ecef922c-aff2-49ac-84bd-17e7e2e784a1.xml, umdf.iwdfioqueue_getdevice, wdf.iwdfioqueue_getdevice, wudfddi/IWDFIoQueue::GetDevice
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
-	IWDFIoQueue.GetDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoQueue::GetDevice


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetDevice</b> method retrieves the interface to the device that owns the I/O queue.


## -parameters




### -param ppWdfDevice [out]

A pointer to a variable that receives a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556917">IWDFDevice</a> interface for the device object, if the call succeeds; otherwise, this parameter is <b>NULL</b>.


## -returns



None




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556917">IWDFDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558943">IWDFIoQueue</a>
 

 

