---
UID: NF:wdfio.WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE
title: WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE function
author: windows-driver-content
description: The WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE function initializes a driver's WDF_IO_QUEUE_CONFIG structure.
old-location: wdf\wdf_io_queue_config_init_default_queue.htm
old-project: wdf
ms.assetid: c7d0c483-b534-471b-8172-174abdbb3c6a
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , A, C, D, DFQueueObjectRef_e566e464-d9a3-44bf-a5a6-bb9b741ffe0f.xml, E, F, G, I, L, N, O, Q, T, U, W, WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE, WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE function, _, kmdf.wdf_io_queue_config_init_default_queue, wdf.wdf_io_queue_config_init_default_queue, wdfio/WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE"
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfio.h
apiname:
-	WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE
product: Windows
targetos: Windows
req.typenames: WDF_IO_QUEUE_STATE
req.product: Windows 10 or later.
---

# WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE</b> function initializes a driver's <a href="..\wdfio\ns-wdfio-_wdf_io_queue_config.md">WDF_IO_QUEUE_CONFIG</a> structure.


## -syntax


````
VOID WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE(
  _Out_ PWDF_IO_QUEUE_CONFIG       Config,
  _In_  WDF_IO_QUEUE_DISPATCH_TYPE DispatchType
);
````


## -parameters




### -param Config [out]

A pointer to the driver's <a href="..\wdfio\ns-wdfio-_wdf_io_queue_config.md">WDF_IO_QUEUE_CONFIG</a> structure.


### -param DispatchType [in]

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_io_queue_dispatch_type.md">WDF_IO_QUEUE_DISPATCH_TYPE</a> enumerator that identifies the request dispatching type for the queue.


## -returns



None




## -remarks



Drivers should call <b>WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE</b> when creating a power-managed I/O queue that is a device's default queue. The <b>WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE</b> function zeros the specified <a href="..\wdfio\ns-wdfio-_wdf_io_queue_config.md">WDF_IO_QUEUE_CONFIG</a> structure and sets its <b>Size</b> member. It also sets the <b>PowerManaged</b> member to <b>WdfUseDefault</b>, sets the <b>DefaultQueue</b> member to <b>TRUE</b>, and stores the specified dispatching type in the <b>DispatchType</b> member.

Starting in KMDF version 1.9, if <i>DispatchType</i> is set to <b>WdfIoQueueDispatchParallel</b>, <b>WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE</b> sets the structure's <b>NumberOfPresentedRequests</b> member to -1. This value indicates that the framework can deliver an unlimited number of I/O requests to the driver.

For a code example that uses <b>WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE</b>, see <a href="..\wdfio\nf-wdfio-wdfioqueuecreate.md">WdfIoQueueCreate</a>.




## -see-also

<a href="..\wudfddi_types\ne-wudfddi_types-_wdf_io_queue_dispatch_type.md">WDF_IO_QUEUE_DISPATCH_TYPE</a>



<a href="..\wdfio\nf-wdfio-wdfioqueuecreate.md">WdfIoQueueCreate</a>



<a href="..\wdfio\nf-wdfio-wdf_io_queue_config_init.md">WDF_IO_QUEUE_CONFIG_INIT</a>



<a href="..\wdfio\ns-wdfio-_wdf_io_queue_config.md">WDF_IO_QUEUE_CONFIG</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

