---
UID: NF:wdfdevice.WdfDeviceConfigureRequestDispatching
title: WdfDeviceConfigureRequestDispatching function
author: windows-driver-content
description: The WdfDeviceConfigureRequestDispatching method causes the framework to queue a specified type of I/O requests to a specified I/O queue.
old-location: wdf\wdfdeviceconfigurerequestdispatching.htm
old-project: wdf
ms.assetid: aba4cccd-267d-48cc-a6ff-be19802adfdc
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfDeviceConfigureRequestDispatching
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
req.alt-api: WdfDeviceConfigureRequestDispatching
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
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
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceConfigureRequestDispatching function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceConfigureRequestDispatching</b> method causes the framework to queue a specified type of I/O requests to a specified I/O queue.



## -syntax

````
NTSTATUS WdfDeviceConfigureRequestDispatching(
  _In_ WDFDEVICE        Device,
  _In_ WDFQUEUE         Queue,
  _In_ WDF_REQUEST_TYPE RequestType
);
````


## -parameters

### -param Device [in]

Supplies a handle to a framework device object.


### -param Queue [in]

Supplies a handle to a framework queue object.


### -param RequestType [in]

Supplies a <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_request_type.md">WDF_REQUEST_TYPE</a>-typed enumerator that identifies the type of request to be queued. The only valid enumerators are: 

<dl>
<dd>
<b>WdfRequestTypeCreate</b>

</dd>
<dd>
<b>WdfRequestTypeRead</b>

</dd>
<dd>
<b>WdfRequestTypeWrite</b>

</dd>
<dd>
<b>WdfRequestTypeDeviceControl</b>

</dd>
<dd>
<b>WdfRequestTypeDeviceControlInternal</b>

</dd>
</dl>

## -returns
If the operation succeeds, the method returns STATUS_SUCCESS. Additional return values include:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An input parameter is invalid.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The amount of available memory is too low.

<dl>
<dt><b>STATUS_WDF_BUSY</b></dt>
</dl>The driver has already assigned a queue to the specified request type.

 

The method might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.


## -remarks
Each call to <b>WdfDeviceConfigureRequestDispatching</b> specifies one request type. If you want a single I/O queue to receive multiple types of requests (for example, read and write requests), your driver can call <b>WdfDeviceConfigureRequestDispatching</b> multiple times for a single I/O queue.

For more information about <b>WdfDeviceConfigureRequestDispatching</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-i-o-queues">Creating I/O Queues</a> and <a href="https://msdn.microsoft.com/83cc87c8-7e2d-4f79-a580-0519d327e7ba">Managing I/O Queues</a>.

The following code example initializes a <a href="..\wdfio\ns-wdfio-_wdf_io_queue_config.md">WDF_IO_QUEUE_CONFIG</a> structure, creates an I/O queue, and then configures the queue so that it receives write requests.


## -see-also
<dl>
<dt>
<a href="..\wdfio\nf-wdfio-wdf_io_queue_config_init.md">WDF_IO_QUEUE_CONFIG_INIT</a>
</dt>
<dt>
<a href="..\wdfio\nf-wdfio-wdfioqueuecreate.md">WdfIoQueueCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceConfigureRequestDispatching method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

