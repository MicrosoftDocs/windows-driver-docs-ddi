---
UID: NF:wdfusb.WdfUsbTargetPipeConfigContinuousReader
title: WdfUsbTargetPipeConfigContinuousReader function
author: windows-driver-content
description: The WdfUsbTargetPipeConfigContinuousReader method configures the framework to continuously read from a specified USB pipe.
old-location: wdf\wdfusbtargetpipeconfigcontinuousreader.htm
tech.root: wdf
ms.assetid: 56ed3c4f-bcfa-417d-a276-9934e3bc1666
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFUsbRef_80432bbe-cb71-4bd1-9c0b-a71ea1f5c809.xml, WdfUsbTargetPipeConfigContinuousReader, WdfUsbTargetPipeConfigContinuousReader method, kmdf.wdfusbtargetpipeconfigcontinuousreader, wdf.wdfusbtargetpipeconfigcontinuousreader, wdfusb/WdfUsbTargetPipeConfigContinuousReader
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, FailD0EntryIoTargetState, KmdfIrql, KmdfIrql2, UsbContReader, UsbKmdfIrql, UsbKmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
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
-	WdfUsbTargetPipeConfigContinuousReader
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfUsbTargetPipeConfigContinuousReader function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbTargetPipeConfigContinuousReader</b> method configures the framework to continuously read from a specified USB pipe.


## -parameters




### -param Pipe [in]

A handle to a framework pipe object that was obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550057">WdfUsbInterfaceGetConfiguredPipe</a>. 


### -param Config [in]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff552561">WDF_USB_CONTINUOUS_READER_CONFIG</a> structure.


## -returns



<b>WdfUsbTargetPipeConfigContinuousReader</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The size of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552561">WDF_USB_CONTINUOUS_READER_CONFIG</a> structure that the <i>Config</i> parameter specified was incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was detected.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Insufficient memory was available.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The pipe's type was not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INTEGER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
The <b>HeaderLength</b>, <b>TransferLength</b>, or <b>TrailerLength</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552561">WDF_USB_CONTINUOUS_READER_CONFIG</a> structure that the <i>Config</i> parameter specified a size what was too large or otherwise invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_BUFFER_SIZE</b></dt>
</dl>
</td>
<td width="60%">
The size of the read buffer was not a multiple of the pipe's maximum packet size.

</td>
</tr>
</table>
 

For a list of other return values that the <b>WdfUsbTargetPipeConfigContinuousReader</b> method might return, see <a href="https://msdn.microsoft.com/f5345c88-1c3a-4b32-9c93-c252713f7641">Framework Object Creation Errors</a>.

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



You can configure a continuous reader for a bulk pipe or an interrupt pipe. The pipe must have an input endpoint.

After calling <b>WdfUsbTargetPipeConfigContinuousReader</b> to configure a continuous reader, your driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548677">WdfIoTargetStart</a> to start the reader. To stop the reader, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548680">WdfIoTargetStop</a>.

Typically, a driver calls <b>WdfUsbTargetPipeConfigContinuousReader</b> from within its <a href="https://msdn.microsoft.com/a3d4a983-8a75-44be-bd72-8673d89f9f87">EvtDevicePrepareHardware</a> callback function. The driver should call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548677">WdfIoTargetStart</a> from within its <a href="https://msdn.microsoft.com/0cfabb0f-2d5e-4445-8683-d2916de5b549">EvtDeviceD0Entry</a> callback function and should call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548680">WdfIoTargetStop</a> from within its <a href="https://msdn.microsoft.com/bc3af732-f9ab-43a4-bc6f-7fa0b4c05a66">EvtDeviceD0Exit</a> callback function.

Each time the pipe's I/O target successfully completes a read request, the framework calls the driver's <a href="https://msdn.microsoft.com/da762d78-6d73-4ab9-83a8-297c6f48855b">EvtUsbTargetPipeReadComplete</a> callback function. If the I/O target reports a failure while processing a request, the framework calls the driver's <a href="https://msdn.microsoft.com/a9e21f47-1a60-419a-839e-8869f9fd4dd7">EvtUsbTargetPipeReadersFailed</a> callback function after all read requests have been completed. (Therefore, the <i>EvtUsbTargetPipeReadComplete</i> callback function will not be called while the <i>EvtUsbTargetPipeReadersFailed</i> callback function is executing).

If you do not supply the optional <a href="https://msdn.microsoft.com/a9e21f47-1a60-419a-839e-8869f9fd4dd7">EvtUsbTargetPipeReadersFailed</a> callback, the framework responds to a failed read attempt by sending another read request. Therefore if the bus is in a state where it is not accepting reads, the framework continually sends new requests to recover from a failed read.

After a driver has called <b>WdfUsbTargetPipeConfigContinuousReader</b>, the driver cannot use <a href="https://msdn.microsoft.com/library/windows/hardware/ff551155">WdfUsbTargetPipeReadSynchronously</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a> to send I/O requests to the pipe unless the continuous reader has been stopped. To stop the reader, the driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548680">WdfIoTargetStop</a> or return <b>FALSE</b> from its <a href="https://msdn.microsoft.com/a9e21f47-1a60-419a-839e-8869f9fd4dd7">EvtUsbTargetPipeReadersFailed</a> callback function.  If the driver calls <b>WdfUsbTargetPipeReadSynchronously</b> while the reader is stopped, it must set the WDF_REQUEST_SEND_OPTION_IGNORE_TARGET_STATE flag in the <b>Flags</b> member of the <i>RequestOptions</i> parameter. Otherwise the request will be pended until the target is restarted.

The framework sets the USBD_SHORT_TRANSFER_OK flag in its internal <a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a>. Setting this flag allows the last packet of a data transfer to be less than the maximum packet size.

For more information about the <b>WdfUsbTargetPipeConfigContinuousReader</b> method and USB I/O targets, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/working-with-usb-pipes">Reading from a Pipe</a>.


#### Examples

The following code example initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552561">WDF_USB_CONTINUOUS_READER_CONFIG</a> structure and calls <b>WdfUsbTargetPipeConfigContinuousReader</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_USB_CONTINUOUS_READER_CONFIG  contReaderConfig;
NTSTATUS  status;

WDF_USB_CONTINUOUS_READER_CONFIG_INIT(
                                      &amp;contReaderConfig,
                                      OsrFxEvtUsbInterruptPipeReadComplete,
                                      DeviceContext,
                                      sizeof(UCHAR)
                                      );
status = WdfUsbTargetPipeConfigContinuousReader(
                                      Pipe,
                                      &amp;contReaderConfig
                                      );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/0cfabb0f-2d5e-4445-8683-d2916de5b549">EvtDeviceD0Entry</a>



<a href="https://msdn.microsoft.com/bc3af732-f9ab-43a4-bc6f-7fa0b4c05a66">EvtDeviceD0Exit</a>



<a href="https://msdn.microsoft.com/a3d4a983-8a75-44be-bd72-8673d89f9f87">EvtDevicePrepareHardware</a>



<a href="https://msdn.microsoft.com/da762d78-6d73-4ab9-83a8-297c6f48855b">EvtUsbTargetPipeReadComplete</a>



<a href="https://msdn.microsoft.com/a9e21f47-1a60-419a-839e-8869f9fd4dd7">EvtUsbTargetPipeReadersFailed</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552561">WDF_USB_CONTINUOUS_READER_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552566">WDF_USB_CONTINUOUS_READER_CONFIG_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548677">WdfIoTargetStart</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548680">WdfIoTargetStop</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550057">WdfUsbInterfaceGetConfiguredPipe</a>
 

 

