---
UID: NF:wdfio.WdfIoQueueCreate
title: WdfIoQueueCreate function (wdfio.h)
description: The WdfIoQueueCreate method creates and configures an I/O queue for a specified device.
old-location: wdf\wdfioqueuecreate.htm
tech.root: wdf
ms.assetid: cd7e993e-1381-4b0c-b046-716e839dbb62
ms.date: 02/26/2018
keywords: ["WdfIoQueueCreate function"]
ms.keywords: DFQueueObjectRef_97b06453-cf79-4944-85d7-530b83211353.xml, WdfIoQueueCreate, WdfIoQueueCreate method, kmdf.wdfioqueuecreate, wdf.wdfioqueuecreate, wdfio/WdfIoQueueCreate
f1_keywords:
 - "wdfio/WdfIoQueueCreate"
 - "WdfIoQueueCreate"
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
- WdfIoQueueCreate
targetos: Windows
req.typenames: 
---

# WdfIoQueueCreate function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfIoQueueCreate</b> method creates and configures an I/O queue for a specified device.


## -parameters




### -param Device 
[in]
A handle to the framework device object that the queue will be associated with. 


### -param Config 
[in]
A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/ns-wdfio-_wdf_io_queue_config">WDF_IO_QUEUE_CONFIG</a> structure.


### -param QueueAttributes 
[in, optional]
A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that specifies object attributes for the new object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES. 


### -param Queue 
[out, optional]
A pointer to a location that receives a handle to a framework queue object.


## -returns



<b>WdfIoQueueCreate</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An input parameter is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The size of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/ns-wdfio-_wdf_io_queue_config">WDF_IO_QUEUE_CONFIG</a> structure is incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_POWER_STATE_INVALID</b></dt>
</dl>
</td>
<td width="60%">
The framework is performing a power management operation.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The amount of available memory is too low.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WDF_NO_CALLBACK</b></dt>
</dl>
</td>
<td width="60%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/ns-wdfio-_wdf_io_queue_config">WDF_IO_QUEUE_CONFIG</a> structure does not specify any <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/request-handlers">request handlers</a>, and the dispatching method is not <b>WdfIoQueueDispatchManual</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The driver is attempting to create a default queue while a default queue already exists for the device, or an internal error occurred.

</td>
</tr>
</table>
 

This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Each call to <b>WdfIoQueueCreate</b> creates an I/O queue for a device. Your driver can create multiple I/O queues for each device. 

The <i>Config</i> and <i>QueueAttributes</i> parameters specify the queue's configuration and object attributes.

By default, the framework device object that the <i>Device</i> parameter specifies becomes the parent object for the new framework queue object. If the driver specifies a parent object in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure's <b>ParentObject</b> member, the parent object can be a framework device object or any object whose chain of parents leads to a framework device object. The framework will delete the queue object when it deletes the parent object.

If your driver provides <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup">EvtCleanupCallback</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_destroy">EvtDestroyCallback</a> callback functions for the framework queue object, the framework calls these callback functions at IRQL = PASSIVE_LEVEL.

For more information about <b>WdfIoQueueCreate</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-i-o-queues">Creating I/O Queues</a>.


#### Examples

The following code example is the section of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function that creates a device's default I/O queue. The example initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/ns-wdfio-_wdf_io_queue_config">WDF_IO_QUEUE_CONFIG</a> structure and then calls <b>WdfIoQueueCreate</b>.

```cpp
NTSTATUS
MyEvtDriverDeviceAdd(
    IN WDFDRIVER  Driver,
    IN PWDFDEVICE_INIT  DeviceInit
    )
{
    WDF_IO_QUEUE_CONFIG  ioQueueConfig;
    WDFQUEUE  hQueue;
...
    WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE(
                                           &ioQueueConfig,
                                           WdfIoQueueDispatchSequential
                                           );

    ioQueueConfig.EvtIoDefault = MyEvtIoDefault;

    status = WdfIoQueueCreate(
                              device,
                              &ioQueueConfig,
                              WDF_NO_OBJECT_ATTRIBUTES,
                              &hQueue
                              );
    if (!NT_SUCCESS (status)) {
        return status;
    }
...
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/ns-wdfio-_wdf_io_queue_config">WDF_IO_QUEUE_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdf_io_queue_config_init_default_queue">WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceconfigurerequestdispatching">WdfDeviceConfigureRequestDispatching</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestforwardtoioqueue">WdfRequestForwardToIoQueue</a>
 

 

