---
UID: NF:wdfio.WDF_IO_QUEUE_CONFIG_INIT
title: WDF_IO_QUEUE_CONFIG_INIT function
author: windows-driver-content
description: The WDF_IO_QUEUE_CONFIG_INIT function initializes a driver's WDF_IO_QUEUE_CONFIG structure.
old-location: wdf\wdf_io_queue_config_init.htm
old-project: wdf
ms.assetid: 54f85485-e652-4132-a5bf-385ad9bf53f8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFQueueObjectRef_637df7c0-f8bc-4436-9144-628c85bfae1a.xml, WDF_IO_QUEUE_CONFIG_INIT, WDF_IO_QUEUE_CONFIG_INIT function, kmdf.wdf_io_queue_config_init, wdf.wdf_io_queue_config_init, wdfio/WDF_IO_QUEUE_CONFIG_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfio.h
api_name:
-	WDF_IO_QUEUE_CONFIG_INIT
product: Windows
targetos: Windows
req.typenames: WDF_IO_QUEUE_STATE
req.product: Windows 10 or later.
---

# WDF_IO_QUEUE_CONFIG_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_IO_QUEUE_CONFIG_INIT</b> function initializes a driver's <a href="..\wdfio\ns-wdfio-_wdf_io_queue_config.md">WDF_IO_QUEUE_CONFIG</a> structure.


## -syntax


````
VOID WDF_IO_QUEUE_CONFIG_INIT(
  _Out_ PWDF_IO_QUEUE_CONFIG       Config,
  _In_  WDF_IO_QUEUE_DISPATCH_TYPE DispatchType
);
````


## -parameters




### -param Config [out]

A pointer to the driver's <a href="..\wdfio\ns-wdfio-_wdf_io_queue_config.md">WDF_IO_QUEUE_CONFIG</a> structure.


### -param DispatchType [in]

A <a href="..\wdfio\ne-wdfio-_wdf_io_queue_dispatch_type.md">WDF_IO_QUEUE_DISPATCH_TYPE</a> enumerator that identifies the request dispatching type for the queue.


## -returns



None




## -remarks



Drivers should call <b>WDF_IO_QUEUE_CONFIG_INIT</b> when creating a power-managed I/O queue that is not a device's default queue. The <b>WDF_IO_QUEUE_CONFIG_INIT</b> function zeros the specified <a href="..\wdfio\ns-wdfio-_wdf_io_queue_config.md">WDF_IO_QUEUE_CONFIG</a> structure and sets its <b>Size</b> member. It also sets the <b>PowerManaged</b> member to <b>WdfUseDefault</b> and stores the specified dispatching type in the <b>DispatchType</b> member.

Starting in KMDF version 1.9, if <i>DispatchType</i> is set to <b>WdfIoQueueDispatchParallel</b>, <b>WDF_IO_QUEUE_CONFIG_INIT</b> sets the structure's <b>NumberOfPresentedRequests</b> member to -1. This value indicates that the framework can deliver an unlimited number of I/O requests to the driver.


#### Examples

The following code example initializes <a href="..\wdfio\ns-wdfio-_wdf_io_queue_config.md">WDF_IO_QUEUE_CONFIG</a> structure and then calls <a href="..\wdfio\nf-wdfio-wdfioqueuecreate.md">WdfIoQueueCreate</a>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_IO_QUEUE_CONFIG  queueConfig;
NTSTATUS  status = STATUS_SUCCESS;
WDFQUEUE  readQueue;

WDF_IO_QUEUE_CONFIG_INIT(
                         &amp;queueConfig,
                         WdfIoQueueDispatchManual
                         );
status = WdfIoQueueCreate(
                          hDevice,
                          &amp;queueConfig,
                          WDF_NO_OBJECT_ATTRIBUTES,
                          &amp;readQueue
                          );</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfio\nf-wdfio-wdf_io_queue_config_init_default_queue.md">WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE</a>



<a href="..\wdfio\ns-wdfio-_wdf_io_queue_config.md">WDF_IO_QUEUE_CONFIG</a>



<a href="..\wudfddi_types\ne-wudfddi_types-_wdf_io_queue_dispatch_type.md">WDF_IO_QUEUE_DISPATCH_TYPE</a>



<a href="..\wdfio\nf-wdfio-wdfioqueuecreate.md">WdfIoQueueCreate</a>



 

 


