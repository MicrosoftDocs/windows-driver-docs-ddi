---
UID: NF:wudfddi.IWDFIoQueue.GetState
title: IWDFIoQueue::GetState (wudfddi.h)
description: The GetState method retrieves the state of an I/O queue.
old-location: wdf\iwdfioqueue_getstate.htm
tech.root: wdf
ms.assetid: 42dc9bbe-b00d-4187-ab07-0c268a061298
ms.date: 02/26/2018
keywords: ["IWDFIoQueue::GetState"]
ms.keywords: GetState, GetState method, GetState method,IWDFIoQueue interface, IWDFIoQueue interface,GetState method, IWDFIoQueue.GetState, IWDFIoQueue::GetState, UMDFQueueObjectRef_81051128-228b-476a-b27f-5c542558d8a8.xml, umdf.iwdfioqueue_getstate, wdf.iwdfioqueue_getstate, wudfddi/IWDFIoQueue::GetState
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFIoQueue::GetState
 - wudfddi/IWDFIoQueue::GetState
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFIoQueue.GetState
---

# IWDFIoQueue::GetState


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetState</b> method retrieves the state of an I/O queue.

## -parameters

### -param pulNumOfRequestsInQueue 

[out]
A pointer to a variable that receives the number of I/O requests that are currently in the I/O queue (that is, that have not been delivered to the driver).

### -param pulNumOfRequestsInDriver 

[out]
A pointer to a variable that receives the number of I/O requests that the driver accepted from the I/O queue but that the driver has not completed, canceled, or forwarded to another I/O queue.

## -returns

<b>GetState</b> returns a bitwise OR of <a href="/windows-hardware/drivers/ddi/wudfddi_types/ne-wudfddi_types-_wdf_io_queue_state">WDF_IO_QUEUE_STATE</a>-typed values that provides the state of the queue.

## -remarks

The total number of requests that are associated with the I/O queue is the sum of the values that the <i>pulNumOfRequestsInQueue</i> and <i>pulNumOfRequestsInDriver</i> parameters point to.

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfioqueue">IWDFIoQueue</a>



<a href="/windows-hardware/drivers/ddi/wudfddi_types/ne-wudfddi_types-_wdf_io_queue_state">WDF_IO_QUEUE_STATE</a>