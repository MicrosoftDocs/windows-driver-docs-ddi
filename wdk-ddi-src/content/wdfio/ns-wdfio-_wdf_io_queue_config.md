---
UID: NS:wdfio._WDF_IO_QUEUE_CONFIG
title: "_WDF_IO_QUEUE_CONFIG"
author: windows-driver-content
description: The WDF_IO_QUEUE_CONFIG structure contains configuration information for a framework queue object.
old-location: wdf\wdf_io_queue_config.htm
tech.root: wdf
ms.assetid: aa8b64a7-eae9-444c-892f-841ca5a610cf
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWDF_IO_QUEUE_CONFIG, DFQueueObjectRef_5fda62f6-b76d-4691-9354-e091af8a5567.xml, PWDF_IO_QUEUE_CONFIG, PWDF_IO_QUEUE_CONFIG structure pointer, WDF_IO_QUEUE_CONFIG, WDF_IO_QUEUE_CONFIG structure, _WDF_IO_QUEUE_CONFIG, kmdf.wdf_io_queue_config, wdf.wdf_io_queue_config, wdfio/PWDF_IO_QUEUE_CONFIG, wdfio/WDF_IO_QUEUE_CONFIG"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Windows
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
-	WDF_IO_QUEUE_CONFIG
product:
- Windows
targetos: Windows
req.typenames: WDF_IO_QUEUE_CONFIG, *PWDF_IO_QUEUE_CONFIG
---

# _WDF_IO_QUEUE_CONFIG structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_IO_QUEUE_CONFIG</b> structure contains configuration information for a framework queue object.


## -struct-fields




### -field Size

The length, in bytes, of this structure.


### -field DispatchType

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff552362">WDF_IO_QUEUE_DISPATCH_TYPE</a> enumerator that identifies the request dispatching type for the queue.


### -field PowerManaged

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff552533">WDF_TRI_STATE</a>-typed value that, if set to <b>WdfTrue</b>, indicates that the framework handles power management of the queue. 

If set to <b>WdfFalse</b>, the driver must handle power management of the queue. 

If set to <b>WdfDefault</b>, the framework handles power management for the queue unless the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff547273">WdfFdoInitSetFilter</a>. 

Drivers above the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/power-policy-ownership">power policy owner</a> in the driver stack must not set the <b>PowerManaged</b> member to <b>WdfTrue</b>. 

For more information about power-managed I/O queues, see <a href="https://msdn.microsoft.com/2e1bf9d2-615b-49b0-b677-f41b23c42eda">Power Management for I/O Queues</a>. 


### -field AllowZeroLengthRequests

A Boolean value that, if <b>TRUE</b>, indicates that the driver expects to receive read or write requests that have a buffer length of zero, so the framework delivers these requests to the driver. If <b>FALSE</b>, the framework does not deliver these requests to the driver; instead, it completes them with a completion status of STATUS_SUCCESS.


### -field DefaultQueue

A Boolean value that, if <b>TRUE</b>, indicates that the queue will be the device's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-i-o-queues">default I/O queue</a>. If <b>FALSE</b>, the queue will not be the device's default queue.


### -field EvtIoDefault

A pointer to the driver's queue-specific <a href="https://msdn.microsoft.com/0b834d01-5603-43e8-9b74-9292610cc06d">EvtIoDefault</a> callback function, or <b>NULL</b>.


### -field EvtIoRead

A pointer to the driver's queue-specific <a href="https://msdn.microsoft.com/d6fbb153-1355-4e94-b5d3-a218bd8c565d">EvtIoRead</a> callback function, or <b>NULL</b>.


### -field EvtIoWrite

A pointer to the driver's queue-specific <a href="https://msdn.microsoft.com/5a0fa3b4-d020-4664-afa4-352573d4f079">EvtIoWrite</a> callback function, or <b>NULL</b>.


### -field EvtIoDeviceControl

A pointer to the driver's queue-specific <a href="https://msdn.microsoft.com/3e3c4c53-e557-4bd1-8b7d-be59dde4b9ce">EvtIoDeviceControl</a> callback function, or <b>NULL</b>.


### -field EvtIoInternalDeviceControl

A pointer to the driver's queue-specific <a href="https://msdn.microsoft.com/268d2323-57a3-4674-90e6-d7142804175b">EvtIoInternalDeviceControl</a> callback function, or <b>NULL</b>.


### -field EvtIoStop

A pointer to the driver's queue-specific <a href="https://msdn.microsoft.com/71a789f1-4f10-44c3-8bd0-a0ea74ec28ab">EvtIoStop</a> callback function, or <b>NULL</b>.


### -field EvtIoResume

A pointer to the driver's queue-specific <a href="https://msdn.microsoft.com/97731224-bf08-4578-958e-729acbb5a628">EvtIoResume</a> callback function, or <b>NULL</b>.


### -field EvtIoCanceledOnQueue

A pointer to the driver's queue-specific <a href="https://msdn.microsoft.com/1b938ee8-a5f3-4a1e-9beb-231d88aa5848">EvtIoCanceledOnQueue</a> callback function, or <b>NULL</b>.


### -field Settings


### -field Settings.Parallel


### -field Settings.Parallel.NumberOfPresentedRequests

For the parallel <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dispatching-methods-for-i-o-requests">dispatching method</a>, the maximum number of I/O requests that the framework asynchronously delivers to the I/O queue's request handlers. For more information, see the following Remarks section. For the sequential and manual dispatching methods, this member must be zero. This member is available in version 1.9 and later versions of KMDF.


### -field Driver

For internal use only.  Set to NULL. This member is available in version 1.11 and later versions of KMDF.



## -remarks



The driver must initialize the <b>WDF_IO_QUEUE_CONFIG</b> structure by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff552360">WDF_IO_QUEUE_CONFIG_INIT</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff552361">WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE</a>.

The WDF_IO_QUEUE_CONFIG structure is used as an input parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547401">WdfIoQueueCreate</a>.

Beginning with version 1.9 of KMDF, drivers can use the <b>NumberOfPresentedRequests</b> member to specify the maximum number of I/O requests that the framework asynchronously delivers to a parallel I/O queue's request handlers. After the framework has delivered the specified number of I/O requests to the driver, it does not deliver more requests from the queue until the driver <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">completes</a>, <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/canceling-i-o-requests">cancels</a>, or <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/requeuing-i-o-requests">requeues</a> at least one of the requests. 

For parallel queues, 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff552360">WDF_IO_QUEUE_CONFIG_INIT</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff552361">WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE</a> set the <b>NumberOfPresentedRequests</b> member to its default value (-1), which indicates that the framework can deliver an unlimited number of I/O requests to the driver.




## -see-also




[WDF_IO_QUEUE_CONFIG_INIT](https://docs.microsoft.com/en-us/windows-hardware/drivers/ddi/content/wdfio/nf-wdfio-wdf_io_queue_config_init)

[WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE](https://docs.microsoft.com/en-us/windows-hardware/drivers/ddi/content/wdfio/nf-wdfio-wdf_io_queue_config_init_default_queue)

[WDF_IO_QUEUE_DISPATCH_TYPE](https://docs.microsoft.com/en-us/windows-hardware/drivers/ddi/content/wdfio/ne-wdfio-_wdf_io_queue_dispatch_type)

[WdfIoQueueCreate](https://docs.microsoft.com/en-us/windows-hardware/drivers/ddi/content/wdfio/nf-wdfio-wdfioqueuecreate)


[WdfIoQueueReadyNotify](https://docs.microsoft.com/en-us/windows-hardware/drivers/ddi/content/wdfio/nf-wdfio-wdfioqueuereadynotify)
 

