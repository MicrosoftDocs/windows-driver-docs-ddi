---
UID: NF:wdfdevice.WdfDeviceConfigureRequestDispatching
title: WdfDeviceConfigureRequestDispatching function (wdfdevice.h)
description: The WdfDeviceConfigureRequestDispatching method causes the framework to queue a specified type of I/O requests to a specified I/O queue.
old-location: wdf\wdfdeviceconfigurerequestdispatching.htm
tech.root: wdf
ms.assetid: aba4cccd-267d-48cc-a6ff-be19802adfdc
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_d1874c0c-e889-4225-8bbf-e8292edcb716.xml, WdfDeviceConfigureRequestDispatching, WdfDeviceConfigureRequestDispatching method, kmdf.wdfdeviceconfigurerequestdispatching, wdf.wdfdeviceconfigurerequestdispatching, wdfdevice/WdfDeviceConfigureRequestDispatching
f1_keywords:
 - "wdfdevice/WdfDeviceConfigureRequestDispatching"
req.header: wdfdevice.h
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
- WdfDeviceConfigureRequestDispatching
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceConfigureRequestDispatching function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfDeviceConfigureRequestDispatching</b> method causes the framework to queue a specified type of I/O requests to a specified I/O queue.


## -parameters




### -param Device [in]

Supplies a handle to a framework device object.


### -param Queue [in]

Supplies a handle to a framework queue object.


### -param RequestType [in]

Supplies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ne-wdfrequest-_wdf_request_type">WDF_REQUEST_TYPE</a>-typed enumerator that identifies the type of request to be queued. The only valid enumerators are: 

<b>WdfRequestTypeCreate</b>

<b>WdfRequestTypeRead</b>

<b>WdfRequestTypeWrite</b>

<b>WdfRequestTypeDeviceControl</b>

<b>WdfRequestTypeDeviceControlInternal</b>


## -returns



If the operation succeeds, the method returns STATUS_SUCCESS. Additional return values include:

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
<dt><b>STATUS_WDF_BUSY</b></dt>
</dl>
</td>
<td width="60%">
The driver has already assigned a queue to the specified request type.

</td>
</tr>
</table>
 

The method might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



Each call to <b>WdfDeviceConfigureRequestDispatching</b> specifies one request type. If you want a single I/O queue to receive multiple types of requests (for example, read and write requests), your driver can call <b>WdfDeviceConfigureRequestDispatching</b> multiple times for a single I/O queue.

For more information about <b>WdfDeviceConfigureRequestDispatching</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-i-o-queues">Creating I/O Queues</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/managing-i-o-queues">Managing I/O Queues</a>.


#### Examples

The following code example initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/ns-wdfio-_wdf_io_queue_config">WDF_IO_QUEUE_CONFIG</a> structure, creates an I/O queue, and then configures the queue so that it receives write requests.

```cpp
WDF_IO_QUEUE_CONFIG queueConfig;
WDFQUEUE WriteQueue;

WDF_IO_QUEUE_CONFIG_INIT(
                         &queueConfig,
                         WdfIoQueueDispatchSequential
                         );
queueConfig.EvtIoWrite = MyEvtIoWrite;
status = WdfIoQueueCreate(
                          Device,
                          &queueConfig,
                          WDF_NO_OBJECT_ATTRIBUTES,
                          &WriteQueue
                          );
if(!NT_SUCCESS(status)) {
    return status;
}
status = WdfDeviceConfigureRequestDispatching(
                                              Device,
                                              WriteQueue,
                                              WdfRequestTypeWrite
                                              );
if(!NT_SUCCESS(status)) {
    return status;
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdf_io_queue_config_init">WDF_IO_QUEUE_CONFIG_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuecreate">WdfIoQueueCreate</a>
 

 

