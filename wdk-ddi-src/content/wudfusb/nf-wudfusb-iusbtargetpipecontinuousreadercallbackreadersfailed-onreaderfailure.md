---
UID: NF:wudfusb.IUsbTargetPipeContinuousReaderCallbackReadersFailed.OnReaderFailure
title: IUsbTargetPipeContinuousReaderCallbackReadersFailed::OnReaderFailure (wudfusb.h)
description: A driver's OnReaderFailure event callback function informs the driver that a continuous reader has reported an error while processing a read request.
old-location: wdf\iusbtargetpipecontinuousreadercallbackreadersfailed_onreaderfailure.htm
tech.root: wdf
ms.assetid: ad91208e-e57a-4b80-b1a1-13b9f7eb1119
ms.date: 02/26/2018
ms.keywords: IUsbTargetPipeContinuousReaderCallbackReadersFailed interface,OnReaderFailure method, IUsbTargetPipeContinuousReaderCallbackReadersFailed.OnReaderFailure, IUsbTargetPipeContinuousReaderCallbackReadersFailed::OnReaderFailure, OnReaderFailure, OnReaderFailure method, OnReaderFailure method,IUsbTargetPipeContinuousReaderCallbackReadersFailed interface, UMDFUSBref_01c8b9de-ab85-4cc6-abec-238dcda2b1e8.xml, umdf.iusbtargetpipecontinuousreadercallbackreadersfailed_onreaderfailure, wdf.iusbtargetpipecontinuousreadercallbackreadersfailed_onreaderfailure, wudfusb/IUsbTargetPipeContinuousReaderCallbackReadersFailed::OnReaderFailure
ms.topic: method
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
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- wudfusb.h
api_name:
- IUsbTargetPipeContinuousReaderCallbackReadersFailed.OnReaderFailure
product:
- Windows
targetos: Windows
req.typenames: 
---

# IUsbTargetPipeContinuousReaderCallbackReadersFailed::OnReaderFailure


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver's <b>OnReaderFailure</b> event callback function informs the driver that a continuous reader has reported an error while processing a read request.


## -parameters




### -param pPipe [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nn-wudfusb-iwdfusbtargetpipe">IWDFUsbTargetPipe</a> interface for the USB pipe on which the driver has enabled a continuous reader.


### -param hrStatus [in]

The HRESULT-typed status value that the USB pipe's I/O target returned.


## -returns



The <b>OnReaderFailure</b> event callback function must return a Boolean value. If the return value is <b>TRUE</b>, the framework resets the USB pipe and then restarts the continuous reader. If the callback function returns <b>FALSE</b>, the framework does not reset the device or restart the continuous reader.




## -remarks



To register an <b>OnReaderFailure</b> callback function, your driver must provide a pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nn-wudfusb-iusbtargetpipecontinuousreadercallbackreadersfailed">IUsbTargetPipeContinuousReaderCallbackReadersFailed</a> interface when it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nf-wudfusb-iwdfusbtargetpipe2-configurecontinuousreader">IWDFUsbTargetPipe2::ConfigureContinuousReader</a>.

If a driver has created a continuous reader for a USB pipe, the framework calls the driver's <b>OnReaderFailure</b> callback function if the driver's I/O target reports an error when it completes a read request. (If the I/O target successfully completes the request, the framework calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nf-wudfusb-iusbtargetpipecontinuousreadercallbackreadcomplete-onreadercompletion">IUsbTargetPipeContinuousReaderCallbackReadComplete::OnReaderCompletion</a> callback function.) 

Before the framework calls a driver's <b>OnReaderFailure</b> callback function, it tries to cancel all in-progress read requests. No read requests are in progress when the framework calls the <b>OnReaderFailure</b> callback function. The framework does not queue any additional read requests until the <b>OnReaderFailure</b> callback function returns.

For information about how the framework synchronizes calls to the <b>OnReaderFailure</b> callback function with calls to other callback functions, see the Remarks section of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nf-wudfusb-iusbtargetpipecontinuousreadercallbackreadcomplete-onreadercompletion">IUsbTargetPipeContinuousReaderCallbackReadComplete::OnReaderCompletion</a>.

The <b>OnReaderFailure</b> callback function must not call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiotargetstatemanagement-stop">IWDFIoTargetStateManagement::Stop</a> to stop the continuous reader's USB target. (In fact, calling <b>IWDFIoTargetStateManagement::Stop</b> in an <b>OnReaderFailure</b> callback function causes a deadlock.) In addition, the callback function must not call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiotargetstatemanagement-start">IWDFIoTargetStateManagement::Start</a> to restart the continuous reader. Instead, the framework restarts the reader if the callback function returns <b>TRUE</b>. For more information about when to call <b>IWDFIoTargetStateManagement::Start</b> and <b>IWDFIoTargetStateManagement::Stop</b> for a continuous reader, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/working-with-usb-pipes-in-umdf-1-x-drivers">Working with USB Pipes in UMDF</a>.

If a driver does not provide an <b>OnReaderFailure</b> callback function and the driver's I/O target reports an error, the framework resets the USB pipe and restarts the continuous reader. 

For more information about the <b>OnReaderFailure</b> callback function and USB I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/usb-i-o-targets-in-umdf">Handling a USB I/O Target</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nf-wudfusb-iusbtargetpipecontinuousreadercallbackreadcomplete-onreadercompletion">IUsbTargetPipeContinuousReaderCallbackReadComplete::OnReaderCompletion</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nn-wudfusb-iusbtargetpipecontinuousreadercallbackreadersfailed">IUsbTargetPipeContinuousReaderCallbackReadersFailed</a>
 

 

