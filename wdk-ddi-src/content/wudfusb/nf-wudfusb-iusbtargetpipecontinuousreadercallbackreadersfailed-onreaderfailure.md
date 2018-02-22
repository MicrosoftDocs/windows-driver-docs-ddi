---
UID: NF:wudfusb.IUsbTargetPipeContinuousReaderCallbackReadersFailed.OnReaderFailure
title: IUsbTargetPipeContinuousReaderCallbackReadersFailed::OnReaderFailure method
author: windows-driver-content
description: A driver's OnReaderFailure event callback function informs the driver that a continuous reader has reported an error while processing a read request.
old-location: wdf\iusbtargetpipecontinuousreadercallbackreadersfailed_onreaderfailure.htm
old-project: wdf
ms.assetid: ad91208e-e57a-4b80-b1a1-13b9f7eb1119
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: OnReaderFailure method, IUsbTargetPipeContinuousReaderCallbackReadersFailed interface, wdf.iusbtargetpipecontinuousreadercallbackreadersfailed_onreaderfailure, OnReaderFailure method, umdf.iusbtargetpipecontinuousreadercallbackreadersfailed_onreaderfailure, wudfusb/IUsbTargetPipeContinuousReaderCallbackReadersFailed::OnReaderFailure, OnReaderFailure, IUsbTargetPipeContinuousReaderCallbackReadersFailed::OnReaderFailure, IUsbTargetPipeContinuousReaderCallbackReadersFailed interface, OnReaderFailure method, UMDFUSBref_01c8b9de-ab85-4cc6-abec-238dcda2b1e8.xml, IUsbTargetPipeContinuousReaderCallbackReadersFailed
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: wudfusb.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	wudfusb.h
apiname:
-	IUsbTargetPipeContinuousReaderCallbackReadersFailed.OnReaderFailure
product: Windows
targetos: Windows
req.typenames: "*PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE"
req.product: Windows 10 or later.
---

# IUsbTargetPipeContinuousReaderCallbackReadersFailed::OnReaderFailure method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver's <b>OnReaderFailure</b> event callback function informs the driver that a continuous reader has reported an error while processing a read request.


## -syntax


````
BOOL OnReaderFailure(
  [in] IWDFUsbTargetPipe *pPipe,
  [in] HRESULT           hrStatus
);
````


## -parameters




### -param pPipe [in]

A pointer to the <a href="..\wudfusb\nn-wudfusb-iwdfusbtargetpipe.md">IWDFUsbTargetPipe</a> interface for the USB pipe on which the driver has enabled a continuous reader.


### -param hrStatus [in]

The HRESULT-typed status value that the USB pipe's I/O target returned.


## -returns



The <b>OnReaderFailure</b> event callback function must return a Boolean value. If the return value is <b>TRUE</b>, the framework resets the USB pipe and then restarts the continuous reader. If the callback function returns <b>FALSE</b>, the framework does not reset the device or restart the continuous reader.




## -remarks



To register an <b>OnReaderFailure</b> callback function, your driver must provide a pointer to the driver's <a href="..\wudfusb\nn-wudfusb-iusbtargetpipecontinuousreadercallbackreadersfailed.md">IUsbTargetPipeContinuousReaderCallbackReadersFailed</a> interface when it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff560395">IWDFUsbTargetPipe2::ConfigureContinuousReader</a>.

If a driver has created a continuous reader for a USB pipe, the framework calls the driver's <b>OnReaderFailure</b> callback function if the driver's I/O target reports an error when it completes a read request. (If the I/O target successfully completes the request, the framework calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556910">IUsbTargetPipeContinuousReaderCallbackReadComplete::OnReaderCompletion</a> callback function.) 

Before the framework calls a driver's <b>OnReaderFailure</b> callback function, it tries to cancel all in-progress read requests. No read requests are in progress when the framework calls the <b>OnReaderFailure</b> callback function. The framework does not queue any additional read requests until the <b>OnReaderFailure</b> callback function returns.

For information about how the framework synchronizes calls to the <b>OnReaderFailure</b> callback function with calls to other callback functions, see the Remarks section of <a href="https://msdn.microsoft.com/library/windows/hardware/ff556910">IUsbTargetPipeContinuousReaderCallbackReadComplete::OnReaderCompletion</a>.

The <b>OnReaderFailure</b> callback function must not call <a href="https://msdn.microsoft.com/library/windows/hardware/ff559217">IWDFIoTargetStateManagement::Stop</a> to stop the continuous reader's USB target. (In fact, calling <b>IWDFIoTargetStateManagement::Stop</b> in an <b>OnReaderFailure</b> callback function causes a deadlock.) In addition, the callback function must not call <a href="https://msdn.microsoft.com/library/windows/hardware/ff559213">IWDFIoTargetStateManagement::Start</a> to restart the continuous reader. Instead, the framework restarts the reader if the callback function returns <b>TRUE</b>. For more information about when to call <b>IWDFIoTargetStateManagement::Start</b> and <b>IWDFIoTargetStateManagement::Stop</b> for a continuous reader, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/working-with-usb-pipes-in-umdf-1-x-drivers">Working with USB Pipes in UMDF</a>.

If a driver does not provide an <b>OnReaderFailure</b> callback function and the driver's I/O target reports an error, the framework resets the USB pipe and restarts the continuous reader. 

For more information about the <b>OnReaderFailure</b> callback function and USB I/O targets, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/usb-i-o-targets-in-umdf">Handling a USB I/O Target</a>.




## -see-also

<a href="..\wudfusb\nn-wudfusb-iusbtargetpipecontinuousreadercallbackreadersfailed.md">IUsbTargetPipeContinuousReaderCallbackReadersFailed</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556910">IUsbTargetPipeContinuousReaderCallbackReadComplete::OnReaderCompletion</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IUsbTargetPipeContinuousReaderCallbackReadersFailed::OnReaderFailure method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

