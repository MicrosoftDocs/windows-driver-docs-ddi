---
UID: NS:wdfio._WDF_IO_QUEUE_CONFIG
title: "_WDF_IO_QUEUE_CONFIG"
author: windows-driver-content
description: The WDF_IO_QUEUE_CONFIG structure contains configuration information for a framework queue object.
old-location: wdf\wdf_io_queue_config.htm
old-project: wdf
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
req.irql: Any IRQL.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfio.h
api_name:
-	WDF_IO_QUEUE_CONFIG
product: Windows
targetos: Windows
req.typenames: WDF_IO_QUEUE_CONFIG, *PWDF_IO_QUEUE_CONFIG
req.product: Windows 10 or later.
---

# _WDF_IO_QUEUE_CONFIG structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_IO_QUEUE_CONFIG</b> structure contains configuration information for a framework queue object.


## -syntax


````
typedef struct _WDF_IO_QUEUE_CONFIG {
  ULONG                                       Size;
  WDF_IO_QUEUE_DISPATCH_TYPE                  DispatchType;
  WDF_TRI_STATE                               PowerManaged;
  BOOLEAN                                     AllowZeroLengthRequests;
  BOOLEAN                                     DefaultQueue;
  PFN_WDF_IO_QUEUE_IO_DEFAULT                 EvtIoDefault;
  PFN_WDF_IO_QUEUE_IO_READ                    EvtIoRead;
  PFN_WDF_IO_QUEUE_IO_WRITE                   EvtIoWrite;
  PFN_WDF_IO_QUEUE_IO_DEVICE_CONTROL          EvtIoDeviceControl;
  PFN_WDF_IO_QUEUE_IO_INTERNAL_DEVICE_CONTROL EvtIoInternalDeviceControl;
  PFN_WDF_IO_QUEUE_IO_STOP                    EvtIoStop;
  PFN_WDF_IO_QUEUE_IO_RESUME                  EvtIoResume;
  PFN_WDF_IO_QUEUE_IO_CANCELED_ON_QUEUE       EvtIoCanceledOnQueue;
  union {
    struct {
      ULONG NumberOfPresentedRequests;
    } Parallel;
  } Settings;
  WDFDRIVER                                   Driver;
} WDF_IO_QUEUE_CONFIG, *PWDF_IO_QUEUE_CONFIG;
````


## -struct-fields




### -field Size

The length, in bytes, of this structure.


### -field DispatchType

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_io_queue_dispatch_type.md">WDF_IO_QUEUE_DISPATCH_TYPE</a> enumerator that identifies the request dispatching type for the queue.


### -field PowerManaged

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_tri_state.md">WDF_TRI_STATE</a>-typed value that, if set to <b>WdfTrue</b>, indicates that the framework handles power management of the queue. 

If set to <b>WdfFalse</b>, the driver must handle power management of the queue. 

If set to <b>WdfDefault</b>, the framework handles power management for the queue unless the driver calls <a href="..\wdffdo\nf-wdffdo-wdffdoinitsetfilter.md">WdfFdoInitSetFilter</a>. 

Drivers above the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/power-policy-ownership">power policy owner</a> in the driver stack must not set the <b>PowerManaged</b> member to <b>WdfTrue</b>. 

For more information about power-managed I/O queues, see <a href="https://msdn.microsoft.com/2e1bf9d2-615b-49b0-b677-f41b23c42eda">Power Management for I/O Queues</a>. 


### -field AllowZeroLengthRequests

A Boolean value that, if <b>TRUE</b>, indicates that the driver expects to receive read or write requests that have a buffer length of zero, so the framework delivers these requests to the driver. If <b>FALSE</b>, the framework does not deliver these requests to the driver; instead, it completes them with a completion status of STATUS_SUCCESS.


### -field DefaultQueue

A Boolean value that, if <b>TRUE</b>, indicates that the queue will be the device's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-i-o-queues">default I/O queue</a>. If <b>FALSE</b>, the queue will not be the device's default queue.


### -field EvtIoDefault

A pointer to the driver's queue-specific <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_default.md">EvtIoDefault</a> callback function, or <b>NULL</b>.


### -field EvtIoRead

A pointer to the driver's queue-specific <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_read.md">EvtIoRead</a> callback function, or <b>NULL</b>.


### -field EvtIoWrite

A pointer to the driver's queue-specific <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_write.md">EvtIoWrite</a> callback function, or <b>NULL</b>.


### -field EvtIoDeviceControl

A pointer to the driver's queue-specific <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_device_control.md">EvtIoDeviceControl</a> callback function, or <b>NULL</b>.


### -field EvtIoInternalDeviceControl

A pointer to the driver's queue-specific <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_internal_device_control.md">EvtIoInternalDeviceControl</a> callback function, or <b>NULL</b>.


### -field EvtIoStop

A pointer to the driver's queue-specific <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_stop.md">EvtIoStop</a> callback function, or <b>NULL</b>.


### -field EvtIoResume

A pointer to the driver's queue-specific <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_resume.md">EvtIoResume</a> callback function, or <b>NULL</b>.


### -field EvtIoCanceledOnQueue

A pointer to the driver's queue-specific <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_canceled_on_queue.md">EvtIoCanceledOnQueue</a> callback function, or <b>NULL</b>.


### -field Settings


### -field Settings.Parallel


### -field Settings.Parallel.NumberOfPresentedRequests

For the parallel <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dispatching-methods-for-i-o-requests">dispatching method</a>, the maximum number of I/O requests that the framework asynchronously delivers to the I/O queue's request handlers. For more information, see the following Remarks section. For the sequential and manual dispatching methods, this member must be zero. This member is available in version 1.9 and later versions of KMDF.


### -field Driver

For internal use only.  Set to NULL. This member is available in version 1.11 and later versions of KMDF.



## -remarks



The driver must initialize the <b>WDF_IO_QUEUE_CONFIG</b> structure by calling <a href="..\wdfio\nf-wdfio-wdf_io_queue_config_init.md">WDF_IO_QUEUE_CONFIG_INIT</a> or <a href="..\wdfio\nf-wdfio-wdf_io_queue_config_init_default_queue.md">WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE</a>.

The WDF_IO_QUEUE_CONFIG structure is used as an input parameter to <a href="..\wdfio\nf-wdfio-wdfioqueuecreate.md">WdfIoQueueCreate</a>.

Beginning with version 1.9 of KMDF, drivers can use the <b>NumberOfPresentedRequests</b> member to specify the maximum number of I/O requests that the framework asynchronously delivers to a parallel I/O queue's request handlers. After the framework has delivered the specified number of I/O requests to the driver, it does not deliver more requests from the queue until the driver <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">completes</a>, <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/canceling-i-o-requests">cancels</a>, or <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/requeuing-i-o-requests">requeues</a> at least one of the requests. 

For parallel queues, 
     <a href="..\wdfio\nf-wdfio-wdf_io_queue_config_init.md">WDF_IO_QUEUE_CONFIG_INIT</a> and <a href="..\wdfio\nf-wdfio-wdf_io_queue_config_init_default_queue.md">WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE</a> set the <b>NumberOfPresentedRequests</b> member to its default value (-1), which indicates that the framework can deliver an unlimited number of I/O requests to the driver.




## -see-also

<a href="..\wdfio\nf-wdfio-wdf_io_queue_config_init.md">WDF_IO_QUEUE_CONFIG_INIT</a>



<a href="..\wdfio\nf-wdfio-wdfioqueuecreate.md">WdfIoQueueCreate</a>



<a href="..\wdfio\nf-wdfio-wdf_io_queue_config_init_default_queue.md">WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE</a>



<a href="..\wudfddi_types\ne-wudfddi_types-_wdf_io_queue_dispatch_type.md">WDF_IO_QUEUE_DISPATCH_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_IO_QUEUE_CONFIG structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

