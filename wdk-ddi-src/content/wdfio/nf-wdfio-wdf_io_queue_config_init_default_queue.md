---
UID: NF:wdfio.WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE
title: WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE function
author: windows-driver-content
description: The WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE function initializes a driver's WDF_IO_QUEUE_CONFIG structure.
old-location: wdf\wdf_io_queue_config_init_default_queue.htm
old-project: wdf
ms.assetid: c7d0c483-b534-471b-8172-174abdbb3c6a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFQueueObjectRef_e566e464-d9a3-44bf-a5a6-bb9b741ffe0f.xml, WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE, WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE function, kmdf.wdf_io_queue_config_init_default_queue, wdf.wdf_io_queue_config_init_default_queue, wdfio/WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE
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
-	WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE
product:
- Windows
targetos: Windows
req.typenames: WDF_IO_QUEUE_STATE
req.product: Windows 10 or later.
---

# WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE</b> function initializes a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552359">WDF_IO_QUEUE_CONFIG</a> structure.


## -parameters




### -param Config [out]

A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552359">WDF_IO_QUEUE_CONFIG</a> structure.


### -param DispatchType [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff552362">WDF_IO_QUEUE_DISPATCH_TYPE</a> enumerator that identifies the request dispatching type for the queue.


## -returns



None




## -remarks



Drivers should call <b>WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE</b> when creating a power-managed I/O queue that is a device's default queue. The <b>WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE</b> function zeros the specified <a href="https://msdn.microsoft.com/library/windows/hardware/ff552359">WDF_IO_QUEUE_CONFIG</a> structure and sets its <b>Size</b> member. It also sets the <b>PowerManaged</b> member to <b>WdfUseDefault</b>, sets the <b>DefaultQueue</b> member to <b>TRUE</b>, and stores the specified dispatching type in the <b>DispatchType</b> member.

Starting in KMDF version 1.9, if <i>DispatchType</i> is set to <b>WdfIoQueueDispatchParallel</b>, <b>WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE</b> sets the structure's <b>NumberOfPresentedRequests</b> member to -1. This value indicates that the framework can deliver an unlimited number of I/O requests to the driver.

For a code example that uses <b>WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547401">WdfIoQueueCreate</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552359">WDF_IO_QUEUE_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552360">WDF_IO_QUEUE_CONFIG_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552362">WDF_IO_QUEUE_DISPATCH_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547401">WdfIoQueueCreate</a>
 

 

