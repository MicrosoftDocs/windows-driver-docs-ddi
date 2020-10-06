---
UID: NF:wudfusb.IWDFUsbTargetPipe2.ConfigureContinuousReader
title: IWDFUsbTargetPipe2::ConfigureContinuousReader (wudfusb.h)
description: The ConfigureContinuousReader method configures the framework to continuously read from a USB pipe.
old-location: wdf\iwdfusbtargetpipe2_configurecontinuousreader.htm
tech.root: wdf
ms.assetid: accb2690-0ab7-4623-8493-545e6e722a7a
ms.date: 02/26/2018
keywords: ["IWDFUsbTargetPipe2::ConfigureContinuousReader"]
ms.keywords: ConfigureContinuousReader, ConfigureContinuousReader method, ConfigureContinuousReader method,IWDFUsbTargetPipe2 interface, IWDFUsbTargetPipe2 interface,ConfigureContinuousReader method, IWDFUsbTargetPipe2.ConfigureContinuousReader, IWDFUsbTargetPipe2::ConfigureContinuousReader, UMDFUSBref_fbf1e16d-97a6-43c4-b667-a4715769009b.xml, umdf.iwdfusbtargetpipe2_configurecontinuousreader, wdf.iwdfusbtargetpipe2_configurecontinuousreader, wudfusb/IWDFUsbTargetPipe2::ConfigureContinuousReader
req.header: wudfusb.h
req.include-header: Wudfusb.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFUsbTargetPipe2::ConfigureContinuousReader
 - wudfusb/IWDFUsbTargetPipe2::ConfigureContinuousReader
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFUsbTargetPipe2.ConfigureContinuousReader
---

# IWDFUsbTargetPipe2::ConfigureContinuousReader


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>ConfigureContinuousReader</b> method configures the framework to continuously read from a USB pipe.

## -parameters

### -param TransferLength 

[in]
The maximum length, in bytes, of data that can be received from the device.

### -param HeaderLength 

[in]
An offset, in bytes, into the buffer that receives data from the device. The framework will store data from the device in a read buffer, beginning at the offset value. In other words, this space precedes the <i>TransferLength</i>-sized space in which the framework stores data from the device.

### -param TrailerLength 

[in]
The length, in bytes, of a trailing buffer space. This space follows the <i>TransferLength</i>-sized space in which the framework stores data from the device.

### -param NumPendingReads 

[in]
The number of read requests that the framework will queue to receive data from the I/O target. If this value is zero, the framework uses a default number of read requests. If the specified value is greater than the permitted maximum value, the framework uses the permitted maximum value. For more information about the <i>NumPendingReads</i> parameter, see the following Remarks section.

### -param pMemoryCleanupCallbackInterface 

[in, optional]
A pointer to a driver-supplied <b>IUnkown</b> interface that the framework uses to access an optional <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iobjectcleanup-oncleanup">IObjectCleanup::OnCleanup</a> callback function. The framework calls the callback function when it deallocates the read buffer that it creates to handle the continuous read operation. This parameter is optional and can be <b>NULL</b>.

### -param pOnCompletion 

[in]
A pointer to a driver-supplied <a href="/windows-hardware/drivers/ddi/wudfusb/nn-wudfusb-iusbtargetpipecontinuousreadercallbackreadcomplete">IUsbTargetPipeContinuousReaderCallbackReadComplete</a> interface that provides an <a href="/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iusbtargetpipecontinuousreadercallbackreadcomplete-onreadercompletion">OnReaderCompletion</a> callback function.

### -param pCompletionContext 

[in, optional]
An untyped pointer to driver-defined context information that the framework passes to the driver's <a href="/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iusbtargetpipecontinuousreadercallbackreadcomplete-onreadercompletion">IUsbTargetPipeContinuousReaderCallbackReadComplete::OnReaderCompletion</a> callback function.

### -param pOnFailure 

[in, optional]
A pointer to a driver-supplied <a href="/windows-hardware/drivers/ddi/wudfusb/nn-wudfusb-iusbtargetpipecontinuousreadercallbackreadersfailed">IUsbTargetPipeContinuousReaderCallbackReadersFailed</a> interface that provides an <a href="/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iusbtargetpipecontinuousreadercallbackreadersfailed-onreaderfailure">OnReaderFailure</a> callback function.

## -returns

<b>ConfigureContinuousReader</b> returns S_OK if the operation succeeds. Otherwise, this method can return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_NT (STATUS_INVALID_DEVICE_STATE)</b></dt>
</dl>
</td>
<td width="60%">
The driver has already configured a continuous reader for the USB pipe.

The USB pipe is not set up for bulk or interrupt input transfers.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
The framework's attempt to allocate a buffer failed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>ERROR_ARITHMETIC_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
The <i>TransferLength</i>, <i>HeaderLength</i>, or <i>TrailerLength</i> parameter specified a size that was too large or otherwise invalid. 

</td>
</tr>
</table>
 

This method might return one of the other values that Winerror.h contains.

## -remarks

You can configure a continuous reader for a bulk pipe or an interrupt pipe. The pipe must have an input endpoint.

After calling <b>ConfigureContinuousReader</b> to configure a continuous reader, your driver must call <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiotargetstatemanagement-start">IWDFIoTargetStateManagement::Start</a> to start the reader. To stop the reader, the driver must call <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiotargetstatemanagement-stop">IWDFIoTargetStateManagement::Stop</a>.

Typically, a driver calls <b>ConfigureContinuousReader</b> from within its <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallbackhardware-onpreparehardware">IPnpCallbackHardware::OnPrepareHardware</a> callback function. The driver should call <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiotargetstatemanagement-start">IWDFIoTargetStateManagement::Start</a> from within its <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallback-ond0entry">IPnpCallback::OnD0Entry</a> callback function and should call <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiotargetstatemanagement-stop">IWDFIoTargetStateManagement::Stop</a> from within its <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallback-ond0exit">IPnpCallback::OnD0Exit</a> callback function.

Each time the pipe's I/O target successfully completes a read request, the framework calls the driver's <a href="/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iusbtargetpipecontinuousreadercallbackreadcomplete-onreadercompletion">IUsbTargetPipeContinuousReaderCallbackReadComplete::OnReaderCompletion</a> callback function. If the I/O target reports a failure while processing a request, the framework calls the driver's <a href="/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iusbtargetpipecontinuousreadercallbackreadersfailed-onreaderfailure">IUsbTargetPipeContinuousReaderCallbackReadersFailed::OnReaderFailure</a> callback function after all read requests have been completed. (Therefore, the <b>OnReaderCompletion</b> callback function will not be called while the <b>OnReaderFailure</b> callback function is executing.)

Use the following guidelines to choose a value for the <i>NumPendingReads</i> parameter:

<ul>
<li>
Set <i>NumPendingReads</i> to zero if you want your driver to use the framework's default value. 

The default value is greater than one and provides reasonably good performance for many devices on many processor configurations. 

</li>
<li>
Set <i>NumPendingReads</i> to one if it is important that your driver receive data buffers in the exact order in which the device delivers the data. 

If the framework queues more than one read request, the driver might not receive the data buffers in same the order in which the device delivers the data.

</li>
<li>
Set <i>NumPendingReads</i> to a number that meets the performance requirements for your device, based on thorough performance measurements. 

First, test your device with the default value (0) for <i>NumPendingReads</i>. Your tests should include various hardware configurations, including different types and numbers of processors, and different USB host controllers and USB configurations. You can then experiment with higher values, using the same tests. A driver that might require a higher value is one for a device that has a high interrupt rate, where data can be lost if interrupts are not serviced rapidly. 

</li>
</ul>
A <i>NumPendingReads</i> value that is too large can slow down a system's performance. You should use the lowest value that meets your performance requirements. Typically, values that are higher than three or four do not improve data throughput. But higher values might reduce latency, or the chance of missing data, on a high-frequency pipe.

After a driver has called <b>ConfigureContinuousReader</b>, the driver cannot use <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-send">IWDFIoRequest::Send</a> to send I/O requests to the pipe unless the driver's <a href="/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iusbtargetpipecontinuousreadercallbackreadersfailed-onreaderfailure">IUsbTargetPipeContinuousReaderCallbackReadersFailed::OnReaderFailure</a> callback function is called and returns <b>FALSE</b>.

For more information about the <b>ConfigureContinuousReader</b> method and USB I/O targets, see <a href="/windows-hardware/drivers/wdf/working-with-usb-pipes-in-umdf-1-x-drivers">Reading from a UMDF-USB Pipe</a>.


#### Examples

The following code example configures a continuous reader. In this example, the maximum buffer size is the size of a driver-defined buffer. The header and trailer buffer offsets are set to zero, and the number of pending read operations is set to two. The example uses the target pipe's interface pointer for the <i>pCompletionContext</i> parameter, so the <a href="/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iusbtargetpipecontinuousreadercallbackreadcomplete-onreadercompletion">OnReaderCompletion</a> callback function can determine the pipe on which the read operation was completed.


```
HRESULT hr, hrQI;
IUsbTargetPipeContinuousReaderCallbackReadComplete *pOnCompletionCallback = NULL;
IUsbTargetPipeContinuousReaderCallbackReadersFailed *pOnFailureCallback= NULL;
IWDFUsbTargetPipe2 * pIUsbInterruptPipe2;

//
// Obtain interfaces.
//
hrQI = this->QueryInterface(IID_PPV_ARGS(&pOnCompletionCallback));
if (!SUCCEEDED(hrQI)) goto Error;
hrQI = this->QueryInterface(IID_PPV_ARGS(&pOnFailureCallback));
if (!SUCCEEDED(hrQI)) goto Error;
hrQI = m_pIUsbInterruptPipe->QueryInterface(IID_PPV_ARGS(&pIUsbInterruptPipe2));
if (!SUCCEEDED(hrQI)) goto Error;

//
// Configure the reader.
//
hr = pIUsbInterruptPipe2->ConfigureContinuousReader(
                                                    sizeof(m_MyBuffer), 
                                                    0,
                                                    0,
                                                    2, 
                                                    NULL,
                                                    pOnCompletionCallback,
                                                    m_pIUsbTargetPipe,
                                                    pOnFailureCallback
                                                    );
...
```


## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallback-ond0entry">IPnpCallback::OnD0Entry</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallback-ond0exit">IPnpCallback::OnD0Exit</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallbackhardware-onpreparehardware">IPnpCallbackHardware::OnPrepareHardware</a>



<a href="/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iusbtargetpipecontinuousreadercallbackreadcomplete-onreadercompletion">IUsbTargetPipeContinuousReaderCallbackReadComplete::OnReaderCompletion</a>



<a href="/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iusbtargetpipecontinuousreadercallbackreadersfailed-onreaderfailure">IUsbTargetPipeContinuousReaderCallbackReadersFailed::OnReaderFailure</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiotargetstatemanagement-start">IWDFIoTargetStateManagement::Start</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiotargetstatemanagement-stop">IWDFIoTargetStateManagement::Stop</a>



<a href="/windows-hardware/drivers/ddi/wudfusb/nn-wudfusb-iwdfusbtargetpipe2">IWDFUsbTargetPipe2</a>