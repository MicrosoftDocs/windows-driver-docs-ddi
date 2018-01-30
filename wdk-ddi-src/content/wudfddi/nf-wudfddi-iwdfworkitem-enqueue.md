---
UID: NF:wudfddi.IWDFWorkItem.Enqueue
title: IWDFWorkItem::Enqueue method
author: windows-driver-content
description: The Enqueue method adds this interface's framework work-item object to the system's work-item queue.
old-location: wdf\iwdfworkitem_enqueue.htm
old-project: wdf
ms.assetid: 61A889D5-122F-4091-90D6-EDD43D52A14A
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFWorkItem::Enqueue, IWDFWorkItem interface, Enqueue method, wudfddi/IWDFWorkItem::Enqueue, Enqueue, Enqueue method, Enqueue method, IWDFWorkItem interface, IWDFWorkItem, umdf.iwdfworkitem_enqueue, wdf.iwdfworkitem_enqueue
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	IWDFWorkItem.Enqueue
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IWDFWorkItem::Enqueue method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


   The <b>Enqueue</b> method adds this interface's framework work-item object to the system's work-item queue.
  


## -syntax


````
void Enqueue();
````


## -parameters





## -returns


This method does not return a value.



## -remarks


If your driver reuses its work-item objects, the driver can call <b>Enqueue</b> again for the same work item before a worker thread has removed the work item from the queue and called the driver’s <a href="..\wudfworkitem\nc-wudfworkitem-wudf_workitem_function.md">OnWorkItem</a> callback function.

 However, UMDF won't add the work item to the queue if it is already there. Therefore, your <a href="..\wudfworkitem\nc-wudfworkitem-wudf_workitem_function.md">OnWorkItem</a> callback function must process all queued work each time that it is called.

For more information, see <a href="https://msdn.microsoft.com/4617A33F-9026-45FF-9CC2-7215423E6D35">Using Work Items</a>.



## -see-also

<a href="..\wudfworkitem\nc-wudfworkitem-wudf_workitem_function.md">OnWorkItem</a>

<a href="..\wudfddi\nn-wudfddi-iwdfworkitem.md">IWDFWorkItem</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFWorkItem::Enqueue method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

