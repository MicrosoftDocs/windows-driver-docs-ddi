---
UID: NF:wudfddi.IWDFIoQueue.GetState
title: IWDFIoQueue::GetState method
author: windows-driver-content
description: The GetState method retrieves the state of an I/O queue.
old-location: wdf\iwdfioqueue_getstate.htm
old-project: wdf
ms.assetid: 42dc9bbe-b00d-4187-ab07-0c268a061298
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFIoQueue::GetState, UMDFQueueObjectRef_81051128-228b-476a-b27f-5c542558d8a8.xml, umdf.iwdfioqueue_getstate, wdf.iwdfioqueue_getstate, IWDFIoQueue interface, GetState method, GetState, IWDFIoQueue, GetState method, IWDFIoQueue interface, wudfddi/IWDFIoQueue::GetState, GetState method
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
-	IWDFIoQueue.GetState
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFIoQueue::GetState method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetState</b> method retrieves the state of an I/O queue.


## -syntax


````
WDF_IO_QUEUE_STATE GetState(
  [out] ULONG *pulNumOfRequestsInQueue,
  [out] ULONG *pulNumOfRequestsInDriver
);
````


## -parameters




#### - pulNumOfRequestsInQueue [out]

A pointer to a variable that receives the number of I/O requests that are currently in the I/O queue (that is, that have not been delivered to the driver).


#### - pulNumOfRequestsInDriver [out]

A pointer to a variable that receives the number of I/O requests that the driver accepted from the I/O queue but that the driver has not completed, canceled, or forwarded to another I/O queue.


## -returns


<b>GetState</b> returns a bitwise OR of <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_io_queue_state.md">WDF_IO_QUEUE_STATE</a>-typed values that provides the state of the queue.



## -remarks


The total number of requests that are associated with the I/O queue is the sum of the values that the <i>pulNumOfRequestsInQueue</i> and <i>pulNumOfRequestsInDriver</i> parameters point to.



## -see-also

<a href="..\wudfddi_types\ne-wudfddi_types-_wdf_io_queue_state.md">WDF_IO_QUEUE_STATE</a>

<a href="..\wudfddi\nn-wudfddi-iwdfioqueue.md">IWDFIoQueue</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoQueue::GetState method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

