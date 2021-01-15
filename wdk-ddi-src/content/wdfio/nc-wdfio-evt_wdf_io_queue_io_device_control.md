---
UID: NC:wdfio.EVT_WDF_IO_QUEUE_IO_DEVICE_CONTROL
title: EVT_WDF_IO_QUEUE_IO_DEVICE_CONTROL (wdfio.h)
description: A driver's EvtIoDeviceControl event callback function processes a specified device I/O control request.
old-location: wdf\evtiodevicecontrol.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["EVT_WDF_IO_QUEUE_IO_DEVICE_CONTROL callback function"]
ms.keywords: DFQueueObjectRef_90eafb20-dd9c-49ca-b435-fdee9b13e4e1.xml, EVT_WDF_IO_QUEUE_IO_DEVICE_CONTROL, EVT_WDF_IO_QUEUE_IO_DEVICE_CONTROL callback, EvtIoDeviceControl, EvtIoDeviceControl callback function, kmdf.evtiodevicecontrol, wdf.evtiodevicecontrol, wdfio/EvtIoDeviceControl
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
req.irql: <= DISPATCH_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_WDF_IO_QUEUE_IO_DEVICE_CONTROL
 - wdfio/EVT_WDF_IO_QUEUE_IO_DEVICE_CONTROL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdfio.h
api_name:
 - EVT_WDF_IO_QUEUE_IO_DEVICE_CONTROL
---

# EVT_WDF_IO_QUEUE_IO_DEVICE_CONTROL callback function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtIoDeviceControl</i> event callback function processes a specified device I/O control request.

## -parameters

### -param Queue 

[in]
A handle to the framework queue object that is associated with the I/O request.

### -param Request 

[in]
A handle to a framework request object.

### -param OutputBufferLength 

[in]
The length, in bytes, of the request's output buffer, if an output buffer is available.

### -param InputBufferLength 

[in]
The length, in bytes, of the request's input buffer, if an input buffer is available.

### -param IoControlCode 

[in]
The driver-defined or system-defined I/O control code (IOCTL) that is associated with the request.

## -remarks

A driver registers an <i>EvtIoDeviceControl</i> callback function when it calls <a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuecreate">WdfIoQueueCreate</a>. For more information about calling <b>WdfIoQueueCreate</b>, see <a href="/windows-hardware/drivers/wdf/creating-i-o-queues">Creating I/O Queues</a>.

If a driver has registered an <i>EvtIoDeviceControl</i> callback function for a device's I/O queue, the callback function receives every I/O control request (<a href="/windows-hardware/drivers/ifs/irp-mj-device-control">IRP_MJ_DEVICE_CONTROL</a>) from the queue. For more information, see <a href="/windows-hardware/drivers/wdf/request-handlers">Request Handlers</a>.

The <i>EvtIoDeviceControl</i> callback function must process each received I/O request in some manner. For more information, see <a href="/windows-hardware/drivers/wdf/processing-i-o-requests">Processing I/O Requests</a>.

Drivers receive I/O control requests when a user application calls <a href="/windows/win32/api/ioapiset/nf-ioapiset-deviceiocontrol">DeviceIoControl</a> (described in Microsoft Windows SDK documentation) or when another driver creates a request by calling either <a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a> or <a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetformatrequestforioctl">WdfIoTargetFormatRequestForIoctl</a>.

The type of operation to be performed depends on the value of the <i>IoControlCode</i> parameter. You must determine the set of <i>IoControlCode</i> values that applications and other drivers can send to your driver. For more information about IOCTLs, see <a href="/windows-hardware/drivers/kernel/using-i-o-control-codes">Using I/O Control Codes</a>.

Most device I/O control operations require an input buffer, an output buffer, or both. For information about how the driver can access a request's buffers, see <a href="/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in Framework-Based Drivers</a>.

The techniques that your driver can use to access the request's input and output buffers (if they exist) depend on the <i>TransferType</i> field of the IOCTL. The value of the IOCTL's <i>TransferType</i> field can be METHOD_BUFFERED, METHOD_DIRECT_IN, METHOD_DIRECT_OUT, or METHOD_NEITHER. For more information about the <i>TransferType</i> field, see <a href="/windows-hardware/drivers/kernel/defining-i-o-control-codes">Defining I/O Control Codes</a>.

The <i>EvtIoDeviceControl</i> callback function can be called at IRQL <= DISPATCH_LEVEL, unless the <b>ExecutionLevel</b> member of the device or driver's <a href="/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure is set to <b>WdfExecutionLevelPassive</b>.

If the IRQL is PASSIVE_LEVEL, the framework calls the callback function within a <a href="/windows-hardware/drivers/kernel/critical-regions-and-guarded-regions">critical region</a>.

For more information about IRQL levels for request handlers, see <a href="/windows-hardware/drivers/wdf/using-automatic-synchronization">Using Automatic Synchronization</a>.

A driver's <i>EvtIoDeviceControl</i> callback function should not call the following queue object methods:<dl>
<dd>
<a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuedrainsynchronously">WdfIoQueueDrainSynchronously</a>
</dd>
<dd>
<a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuepurgesynchronously">WdfIoQueuePurgeSynchronously</a>
</dd>
<dd>
<a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuestopsynchronously">WdfIoQueueStopSynchronously</a>
</dd>
</dl>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_internal_device_control">EvtIoInternalDeviceControl</a>



<a href="/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuecreate">WdfIoQueueCreate</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetformatrequestforioctl">WdfIoTargetFormatRequestForIoctl</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>

