---
UID: NF:wdfio.WdfIoQueueStart
title: WdfIoQueueStart function (wdfio.h)
description: The WdfIoQueueStart method enables an I/O queue to start receiving and delivering new I/O requests.
old-location: wdf\wdfioqueuestart.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WdfIoQueueStart function"]
ms.keywords: DFQueueObjectRef_15829d65-ee6a-455d-a0c6-cf21f5426e31.xml, WdfIoQueueStart, WdfIoQueueStart method, kmdf.wdfioqueuestart, wdf.wdfioqueuestart, wdfio/WdfIoQueueStart
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfIoQueueStart
 - wdfio/WdfIoQueueStart
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
 - WUDFx02000.dll
 - WUDFx02000.dll.dll
api_name:
 - WdfIoQueueStart
---

# WdfIoQueueStart function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfIoQueueStart</b> method enables an I/O queue to start receiving and delivering new I/O requests.

## -parameters

### -param Queue [in]


A handle to a framework queue object.

## -remarks

A bug check occurs if the driver supplies an invalid object handle.



If I/O requests are in the I/O queue when the driver calls <b>WdfIoQueueStart</b>, the same thread that calls <b>WdfIoQueueStart</b> can call the driver's <a href="/windows-hardware/drivers/wdf/request-handlers">request handlers</a> before <b>WdfIoQueueStart</b> returns. Therefore, when the driver calls <b>WdfIoQueueStart</b>, it must not hold any <a href="/windows-hardware/drivers/wdf/using-framework-locks">locks</a> that the request handlers attempt to acquire. Otherwise, a deadlock can result.

For more information about the <b>WdfIoQueueStart</b> method, see <a href="/windows-hardware/drivers/wdf/managing-i-o-queues">Managing I/O Queues</a>.


#### Examples

The following code example purges a specified I/O queue and then restarts the queue.

```cpp
WdfIoQueuePurge(
                ReadQueue, 
                WDF_NO_EVENT_CALLBACK, 
                WDF_NO_CONTEXT
                );
WdfIoQueueStart(ReadQueue);
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuepurge">WdfIoQueuePurge</a>



<a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuestop">WdfIoQueueStop</a>
