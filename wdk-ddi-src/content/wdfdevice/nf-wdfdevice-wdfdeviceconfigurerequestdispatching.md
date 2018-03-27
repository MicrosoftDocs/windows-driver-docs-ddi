---
UID: NF:wdfdevice.WdfDeviceConfigureRequestDispatching
title: WdfDeviceConfigureRequestDispatching function
author: windows-driver-content
description: The WdfDeviceConfigureRequestDispatching method causes the framework to queue a specified type of I/O requests to a specified I/O queue.
old-location: wdf\wdfdeviceconfigurerequestdispatching.htm
old-project: wdf
ms.assetid: aba4cccd-267d-48cc-a6ff-be19802adfdc
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_d1874c0c-e889-4225-8bbf-e8292edcb716.xml, WdfDeviceConfigureRequestDispatching, WdfDeviceConfigureRequestDispatching method, kmdf.wdfdeviceconfigurerequestdispatching, wdf.wdfdeviceconfigurerequestdispatching, wdfdevice/WdfDeviceConfigureRequestDispatching
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfDeviceConfigureRequestDispatching
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceConfigureRequestDispatching function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceConfigureRequestDispatching</b> method causes the framework to queue a specified type of I/O requests to a specified I/O queue.


## -parameters




### -param Device [in]

Supplies a handle to a framework device object.


### -param Queue [in]

Supplies a handle to a framework queue object.


### -param RequestType [in]

Supplies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552503">WDF_REQUEST_TYPE</a>-typed enumerator that identifies the type of request to be queued. The only valid enumerators are: 

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
 

The method might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



Each call to <b>WdfDeviceConfigureRequestDispatching</b> specifies one request type. If you want a single I/O queue to receive multiple types of requests (for example, read and write requests), your driver can call <b>WdfDeviceConfigureRequestDispatching</b> multiple times for a single I/O queue.

For more information about <b>WdfDeviceConfigureRequestDispatching</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-i-o-queues">Creating I/O Queues</a> and <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/managing-i-o-queues">Managing I/O Queues</a>.


#### Examples

The following code example initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552359">WDF_IO_QUEUE_CONFIG</a> structure, creates an I/O queue, and then configures the queue so that it receives write requests.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_IO_QUEUE_CONFIG queueConfig;
WDFQUEUE WriteQueue;

WDF_IO_QUEUE_CONFIG_INIT(
                         &amp;queueConfig,
                         WdfIoQueueDispatchSequential
                         );
queueConfig.EvtIoWrite = MyEvtIoWrite;
status = WdfIoQueueCreate(
                          Device,
                          &amp;queueConfig,
                          WDF_NO_OBJECT_ATTRIBUTES,
                          &amp;WriteQueue
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
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552360">WDF_IO_QUEUE_CONFIG_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547401">WdfIoQueueCreate</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceConfigureRequestDispatching method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

