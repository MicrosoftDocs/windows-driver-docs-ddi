---
UID: NF:wdfusb.WdfUsbTargetPipeConfigContinuousReader
title: WdfUsbTargetPipeConfigContinuousReader function (wdfusb.h)
description: The WdfUsbTargetPipeConfigContinuousReader method configures the framework to continuously read from a specified USB pipe.
old-location: wdf\wdfusbtargetpipeconfigcontinuousreader.htm
tech.root: wdf
ms.assetid: 56ed3c4f-bcfa-417d-a276-9934e3bc1666
ms.date: 02/26/2018
keywords: ["WdfUsbTargetPipeConfigContinuousReader function"]
ms.keywords: DFUsbRef_80432bbe-cb71-4bd1-9c0b-a71ea1f5c809.xml, WdfUsbTargetPipeConfigContinuousReader, WdfUsbTargetPipeConfigContinuousReader method, kmdf.wdfusbtargetpipeconfigcontinuousreader, wdf.wdfusbtargetpipeconfigcontinuousreader, wdfusb/WdfUsbTargetPipeConfigContinuousReader
f1_keywords:
 - "wdfusb/WdfUsbTargetPipeConfigContinuousReader"
 - "WdfUsbTargetPipeConfigContinuousReader"
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
req.irql: <=DISPATCH_LEVEL
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
- WdfUsbTargetPipeConfigContinuousReader
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfUsbTargetPipeConfigContinuousReader function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfUsbTargetPipeConfigContinuousReader</b> method configures the framework to continuously read from a specified USB pipe.


## -parameters




### -param Pipe [in]

A handle to a framework pipe object that was obtained by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbinterfacegetconfiguredpipe">WdfUsbInterfaceGetConfiguredPipe</a>. 


### -param Config [in]

A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_continuous_reader_config">WDF_USB_CONTINUOUS_READER_CONFIG</a> structure.


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
The size of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_continuous_reader_config">WDF_USB_CONTINUOUS_READER_CONFIG</a> structure that the <i>Config</i> parameter specified was incorrect.

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
The <b>HeaderLength</b>, <b>TransferLength</b>, or <b>TrailerLength</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_continuous_reader_config">WDF_USB_CONTINUOUS_READER_CONFIG</a> structure that the <i>Config</i> parameter specified a size what was too large or otherwise invalid.

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
 

For a list of other return values that the <b>WdfUsbTargetPipeConfigContinuousReader</b> method might return, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-creation-errors">Framework Object Creation Errors</a>.

This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



You can configure a continuous reader for a bulk pipe or an interrupt pipe. The pipe must have an input endpoint.

After calling <b>WdfUsbTargetPipeConfigContinuousReader</b> to configure a continuous reader, your driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetstart">WdfIoTargetStart</a> to start the reader. To stop the reader, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetstop">WdfIoTargetStop</a>.

Typically, a driver calls <b>WdfUsbTargetPipeConfigContinuousReader</b> from within its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a> callback function. The driver should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetstart">WdfIoTargetStart</a> from within its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_entry">EvtDeviceD0Entry</a> callback function and should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetstop">WdfIoTargetStop</a> from within its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_exit">EvtDeviceD0Exit</a> callback function.

Each time the pipe's I/O target successfully completes a read request, the framework calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nc-wdfusb-evt_wdf_usb_reader_completion_routine">EvtUsbTargetPipeReadComplete</a> callback function. If the I/O target reports a failure while processing a request, the framework calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nc-wdfusb-evt_wdf_usb_readers_failed">EvtUsbTargetPipeReadersFailed</a> callback function after all read requests have been completed. (Therefore, the <i>EvtUsbTargetPipeReadComplete</i> callback function will not be called while the <i>EvtUsbTargetPipeReadersFailed</i> callback function is executing).

If you do not supply the optional <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nc-wdfusb-evt_wdf_usb_readers_failed">EvtUsbTargetPipeReadersFailed</a> callback, the framework responds to a failed read attempt by sending another read request. Therefore if the bus is in a state where it is not accepting reads, the framework continually sends new requests to recover from a failed read.

After a driver has called <b>WdfUsbTargetPipeConfigContinuousReader</b>, the driver cannot use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetpipereadsynchronously">WdfUsbTargetPipeReadSynchronously</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestsend">WdfRequestSend</a> to send I/O requests to the pipe unless the continuous reader has been stopped. To stop the reader, the driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetstop">WdfIoTargetStop</a> or return <b>FALSE</b> from its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nc-wdfusb-evt_wdf_usb_readers_failed">EvtUsbTargetPipeReadersFailed</a> callback function.  If the driver calls <b>WdfUsbTargetPipeReadSynchronously</b> while the reader is stopped, it must set the WDF_REQUEST_SEND_OPTION_IGNORE_TARGET_STATE flag in the <b>Flags</b> member of the <i>RequestOptions</i> parameter. Otherwise the request will be pended until the target is restarted.

The framework sets the USBD_SHORT_TRANSFER_OK flag in its internal <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a>. Setting this flag allows the last packet of a data transfer to be less than the maximum packet size.

For more information about the <b>WdfUsbTargetPipeConfigContinuousReader</b> method and USB I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/working-with-usb-pipes">Reading from a Pipe</a>.


#### Examples

The following code example initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_continuous_reader_config">WDF_USB_CONTINUOUS_READER_CONFIG</a> structure and calls <b>WdfUsbTargetPipeConfigContinuousReader</b>.

```cpp
WDF_USB_CONTINUOUS_READER_CONFIG  contReaderConfig;
NTSTATUS  status;

WDF_USB_CONTINUOUS_READER_CONFIG_INIT(
                                      &contReaderConfig,
                                      OsrFxEvtUsbInterruptPipeReadComplete,
                                      DeviceContext,
                                      sizeof(UCHAR)
                                      );
status = WdfUsbTargetPipeConfigContinuousReader(
                                      Pipe,
                                      &contReaderConfig
                                      );
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_entry">EvtDeviceD0Entry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_exit">EvtDeviceD0Exit</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nc-wdfusb-evt_wdf_usb_reader_completion_routine">EvtUsbTargetPipeReadComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nc-wdfusb-evt_wdf_usb_readers_failed">EvtUsbTargetPipeReadersFailed</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_continuous_reader_config">WDF_USB_CONTINUOUS_READER_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_continuous_reader_config_init">WDF_USB_CONTINUOUS_READER_CONFIG_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetstart">WdfIoTargetStart</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetstop">WdfIoTargetStop</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbinterfacegetconfiguredpipe">WdfUsbInterfaceGetConfiguredPipe</a>
 

 

