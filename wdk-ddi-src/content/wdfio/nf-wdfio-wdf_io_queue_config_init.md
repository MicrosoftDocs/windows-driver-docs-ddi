---
UID: NF:wdfio.WDF_IO_QUEUE_CONFIG_INIT
title: WDF_IO_QUEUE_CONFIG_INIT function (wdfio.h)
description: The WDF_IO_QUEUE_CONFIG_INIT function initializes a driver's WDF_IO_QUEUE_CONFIG structure.
old-location: wdf\wdf_io_queue_config_init.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WDF_IO_QUEUE_CONFIG_INIT function"]
ms.keywords: DFQueueObjectRef_637df7c0-f8bc-4436-9144-628c85bfae1a.xml, WDF_IO_QUEUE_CONFIG_INIT, WDF_IO_QUEUE_CONFIG_INIT function, kmdf.wdf_io_queue_config_init, wdf.wdf_io_queue_config_init, wdfio/WDF_IO_QUEUE_CONFIG_INIT
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - WDF_IO_QUEUE_CONFIG_INIT
 - wdfio/WDF_IO_QUEUE_CONFIG_INIT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfio.h
api_name:
 - WDF_IO_QUEUE_CONFIG_INIT
---

# WDF_IO_QUEUE_CONFIG_INIT function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_IO_QUEUE_CONFIG_INIT</b> function initializes a driver's <a href="/windows-hardware/drivers/ddi/wdfio/ns-wdfio-_wdf_io_queue_config">WDF_IO_QUEUE_CONFIG</a> structure.

## -parameters

### -param Config 

[out]
A pointer to the driver's <a href="/windows-hardware/drivers/ddi/wdfio/ns-wdfio-_wdf_io_queue_config">WDF_IO_QUEUE_CONFIG</a> structure.

### -param DispatchType 

[in]
A <a href="/windows-hardware/drivers/ddi/wdfio/ne-wdfio-_wdf_io_queue_dispatch_type">WDF_IO_QUEUE_DISPATCH_TYPE</a> enumerator that identifies the request dispatching type for the queue.

## -remarks

Drivers should call <b>WDF_IO_QUEUE_CONFIG_INIT</b> when creating a power-managed I/O queue that is not a device's default queue. The <b>WDF_IO_QUEUE_CONFIG_INIT</b> function zeros the specified <a href="/windows-hardware/drivers/ddi/wdfio/ns-wdfio-_wdf_io_queue_config">WDF_IO_QUEUE_CONFIG</a> structure and sets its <b>Size</b> member. It also sets the <b>PowerManaged</b> member to <b>WdfUseDefault</b> and stores the specified dispatching type in the <b>DispatchType</b> member.

Starting in KMDF version 1.9, if <i>DispatchType</i> is set to <b>WdfIoQueueDispatchParallel</b>, <b>WDF_IO_QUEUE_CONFIG_INIT</b> sets the structure's <b>NumberOfPresentedRequests</b> member to -1. This value indicates that the framework can deliver an unlimited number of I/O requests to the driver.


#### Examples

The following code example initializes <a href="/windows-hardware/drivers/ddi/wdfio/ns-wdfio-_wdf_io_queue_config">WDF_IO_QUEUE_CONFIG</a> structure and then calls <a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuecreate">WdfIoQueueCreate</a>.

```cpp
WDF_IO_QUEUE_CONFIG  queueConfig;
NTSTATUS  status = STATUS_SUCCESS;
WDFQUEUE  readQueue;

WDF_IO_QUEUE_CONFIG_INIT(
                         &queueConfig,
                         WdfIoQueueDispatchManual
                         );
status = WdfIoQueueCreate(
                          hDevice,
                          &queueConfig,
                          WDF_NO_OBJECT_ATTRIBUTES,
                          &readQueue
                          );
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfio/ns-wdfio-_wdf_io_queue_config">WDF_IO_QUEUE_CONFIG</a>



<a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdf_io_queue_config_init_default_queue">WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE</a>



<a href="/windows-hardware/drivers/ddi/wdfio/ne-wdfio-_wdf_io_queue_dispatch_type">WDF_IO_QUEUE_DISPATCH_TYPE</a>



<a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuecreate">WdfIoQueueCreate</a>
