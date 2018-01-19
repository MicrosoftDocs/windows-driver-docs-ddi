---
UID: NF:wdfio.WdfIoQueueCreate
title: WdfIoQueueCreate function
author: windows-driver-content
description: The WdfIoQueueCreate method creates and configures an I/O queue for a specified device.
old-location: wdf\wdfioqueuecreate.htm
old-project: wdf
ms.assetid: cd7e993e-1381-4b0c-b046-716e839dbb62
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfIoQueueCreate
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
req.alt-api: WdfIoQueueCreate
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: ChangeQueueState, DriverCreate, DrvAckIoStop, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: WDF_IO_QUEUE_STATE
req.product: Windows 10 or later.
---

# WdfIoQueueCreate function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfIoQueueCreate</b> method creates and configures an I/O queue for a specified device.



## -syntax

````
NTSTATUS WdfIoQueueCreate(
  _In_      WDFDEVICE              Device,
  _In_      PWDF_IO_QUEUE_CONFIG   Config,
  _In_opt_  PWDF_OBJECT_ATTRIBUTES QueueAttributes,
  _Out_opt_ WDFQUEUE               *Queue
);
````


## -parameters

### -param Device [in]

A handle to the framework device object that the queue will be associated with. 


### -param Config [in]

A pointer to a caller-allocated <a href="..\wdfio\ns-wdfio-_wdf_io_queue_config.md">WDF_IO_QUEUE_CONFIG</a> structure.


### -param QueueAttributes [in, optional]

A pointer to a caller-allocated <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that specifies object attributes for the new object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES. 


### -param Queue [out, optional]

A pointer to a location that receives a handle to a framework queue object.


## -returns
<b>WdfIoQueueCreate</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An input parameter is invalid.
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>The size of the <a href="..\wdfio\ns-wdfio-_wdf_io_queue_config.md">WDF_IO_QUEUE_CONFIG</a> structure is incorrect.
<dl>
<dt><b>STATUS_POWER_STATE_INVALID</b></dt>
</dl>The framework is performing a power management operation.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The amount of available memory is too low.
<dl>
<dt><b>STATUS_WDF_NO_CALLBACK</b></dt>
</dl>The <a href="..\wdfio\ns-wdfio-_wdf_io_queue_config.md">WDF_IO_QUEUE_CONFIG</a> structure does not specify any <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-handlers">request handlers</a>, and the dispatching method is not <b>WdfIoQueueDispatchManual</b>.
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>The driver is attempting to create a default queue while a default queue already exists for the device, or an internal error occurred.

 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
Each call to <b>WdfIoQueueCreate</b> creates an I/O queue for a device. Your driver can create multiple I/O queues for each device. 

The <i>Config</i> and <i>QueueAttributes</i> parameters specify the queue's configuration and object attributes.

By default, the framework device object that the <i>Device</i> parameter specifies becomes the parent object for the new framework queue object. If the driver specifies a parent object in the <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure's <b>ParentObject</b> member, the parent object can be a framework device object or any object whose chain of parents leads to a framework device object. The framework will delete the queue object when it deletes the parent object.

If your driver provides <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a> or <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_destroy.md">EvtDestroyCallback</a> callback functions for the framework queue object, the framework calls these callback functions at IRQL = PASSIVE_LEVEL.

For more information about <b>WdfIoQueueCreate</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-i-o-queues">Creating I/O Queues</a>.

The following code example is the section of an <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function that creates a device's default I/O queue. The example initializes a <a href="..\wdfio\ns-wdfio-_wdf_io_queue_config.md">WDF_IO_QUEUE_CONFIG</a> structure and then calls <b>WdfIoQueueCreate</b>.


## -see-also
<dl>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestforwardtoioqueue.md">WdfRequestForwardToIoQueue</a>
</dt>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceconfigurerequestdispatching.md">WdfDeviceConfigureRequestDispatching</a>
</dt>
<dt>
<a href="..\wdfio\ns-wdfio-_wdf_io_queue_config.md">WDF_IO_QUEUE_CONFIG</a>
</dt>
<dt>
<a href="..\wdfio\nf-wdfio-wdf_io_queue_config_init_default_queue.md">WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE</a>
</dt>
<dt>
<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoQueueCreate method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

