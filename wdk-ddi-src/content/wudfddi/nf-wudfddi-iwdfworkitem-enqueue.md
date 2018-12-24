---
UID: NF:wudfddi.IWDFWorkItem.Enqueue
title: IWDFWorkItem::Enqueue
description: The Enqueue method adds this interface's framework work-item object to the system's work-item queue.
old-location: wdf\iwdfworkitem_enqueue.htm
tech.root: wdf
ms.assetid: 61A889D5-122F-4091-90D6-EDD43D52A14A
ms.date: 02/26/2018
ms.keywords: Enqueue, Enqueue method, Enqueue method,IWDFWorkItem interface, IWDFWorkItem interface,Enqueue method, IWDFWorkItem.Enqueue, IWDFWorkItem::Enqueue, umdf.iwdfworkitem_enqueue, wdf.iwdfworkitem_enqueue, wudfddi/IWDFWorkItem::Enqueue
ms.topic: method
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
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
-	IWDFWorkItem.Enqueue
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFWorkItem::Enqueue


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


   The <b>Enqueue</b> method adds this interface's framework work-item object to the system's work-item queue.
  


## -parameters






## -returns



This method does not return a value.




## -remarks



If your driver reuses its work-item objects, the driver can call <b>Enqueue</b> again for the same work item before a worker thread has removed the work item from the queue and called the driver’s <a href="https://msdn.microsoft.com/4CCA1F5E-C92E-4D8D-A8C0-B8E9A0F29703">OnWorkItem</a> callback function.

 However, UMDF won't add the work item to the queue if it is already there. Therefore, your <a href="https://msdn.microsoft.com/4CCA1F5E-C92E-4D8D-A8C0-B8E9A0F29703">OnWorkItem</a> callback function must process all queued work each time that it is called.

For more information, see <a href="https://msdn.microsoft.com/4617A33F-9026-45FF-9CC2-7215423E6D35">Using Work Items</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406734">IWDFWorkItem</a>



<a href="https://msdn.microsoft.com/4CCA1F5E-C92E-4D8D-A8C0-B8E9A0F29703">OnWorkItem</a>
 

 

