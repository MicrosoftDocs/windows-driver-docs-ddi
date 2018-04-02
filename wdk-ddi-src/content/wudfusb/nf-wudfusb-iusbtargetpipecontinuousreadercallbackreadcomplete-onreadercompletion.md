---
UID: NF:wudfusb.IUsbTargetPipeContinuousReaderCallbackReadComplete.OnReaderCompletion
title: IUsbTargetPipeContinuousReaderCallbackReadComplete::OnReaderCompletion method
author: windows-driver-content
description: A driver's OnReaderCompletion event callback function informs the driver that a continuous reader has successfully completed a read request.
old-location: wdf\iusbtargetpipecontinuousreadercallbackreadcomplete_onreadercompletion.htm
old-project: wdf
ms.assetid: 946e0206-7609-4dc7-91c2-a6aadad91751
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IUsbTargetPipeContinuousReaderCallbackReadComplete, IUsbTargetPipeContinuousReaderCallbackReadComplete interface, OnReaderCompletion method, IUsbTargetPipeContinuousReaderCallbackReadComplete::OnReaderCompletion, OnReaderCompletion method, OnReaderCompletion method, IUsbTargetPipeContinuousReaderCallbackReadComplete interface, OnReaderCompletion,IUsbTargetPipeContinuousReaderCallbackReadComplete.OnReaderCompletion, UMDFUSBref_a221433f-9a32-4205-8f12-a0c891dbe8bf.xml, umdf.iusbtargetpipecontinuousreadercallbackreadcomplete_onreadercompletion, wdf.iusbtargetpipecontinuousreadercallbackreadcomplete_onreadercompletion, wudfusb/IUsbTargetPipeContinuousReaderCallbackReadComplete::OnReaderCompletion
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	wudfusb.h
api_name:
-	IUsbTargetPipeContinuousReaderCallbackReadComplete.OnReaderCompletion
product:
- Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# IUsbTargetPipeContinuousReaderCallbackReadComplete::OnReaderCompletion method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver's <b>OnReaderCompletion</b> event callback function informs the driver that a continuous reader has successfully completed a read request.


## -parameters




### -param pPipe [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560391">IWDFUsbTargetPipe</a> interface for the USB pipe on which the driver has enabled a continuous reader.


### -param pMemory [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559249">IWDFMemory</a> interface for a read buffer that contains data that was read from the USB pipe.


### -param NumBytesTransferred [in]

The number of bytes that the read buffer contains.


### -param Context [in]

A pointer to driver-supplied context information that the driver provided when it previously called <a href="https://msdn.microsoft.com/library/windows/hardware/ff560395">IWDFUsbTargetPipe2::ConfigureContinuousReader</a>.


## -returns



None.




## -remarks



To register an <b>IUsbTargetPipeContinuousReaderCallbackReadComplete::OnReaderCompletion</b> callback function, your driver must provide a pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556908">IUsbTargetPipeContinuousReaderCallbackReadComplete</a> interface when it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff560395">IWDFUsbTargetPipe2::ConfigureContinuousReader</a>.

If a driver has created a continuous reader for a USB pipe, the framework calls the driver's <b>OnReaderCompletion</b> callback function each time the driver's I/O target successfully completes a read request. If the I/O target does not successfully complete a request, the framework calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556915">IUsbTargetPipeContinuousReaderCallbackReadersFailed::OnReaderFailure</a> callback function. 

To access the buffer that contains data that was read from the device, the driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff560152">IWDFMemory::GetDataBuffer</a>. The framework writes the data into the buffer, after the header that is defined by the <i>HeaderLength</i> parameter of <a href="https://msdn.microsoft.com/library/windows/hardware/ff560395">IWDFUsbTargetPipe2::ConfigureContinuousReader</a>. Note that the pointer that <b>IWDFMemory::GetDataBuffer</b> returns points to the beginning of the header, but the <b>OnReaderCompletion</b> callback function's <i>NumBytesTransferred</i> parameter does not include the header's length.

By default, the framework deletes the buffer's memory object after the <b>OnReaderCompletion</b> callback function returns. However, you might want the memory object to remain valid after the callback function returns. For example, you might want your driver to store the memory object's interface pointer in the framework pipe object's <a href="https://msdn.microsoft.com/9b543d5d-ed6d-4440-b5ad-aefca69dd489">context space</a> so that the driver can process the memory object's contents after the callback function returns. To extend the lifetime of the memory object, the callback function must call the buffer's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/umdf-based-on-com-subset">IWDFMemory::AddRef</a> method. Subsequently, the driver must call the buffer's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/umdf-based-on-com-subset">IWDFMemory::Release</a> method so that the framework can delete the object.

The framework synchronizes calls to the <b>OnReaderCompletion</b> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff556915">IUsbTargetPipeContinuousReaderCallbackReadersFailed::OnReaderFailure</a> callback functions according to the following rules:

<ul>
<li>
These callback functions do not run simultaneously for an individual USB pipe.

</li>
<li>
If the driver creates multiple continuous readers for multiple USB pipes, with multiple <b>OnReaderCompletion</b> and <a href="https://msdn.microsoft.com/ad91208e-e57a-4b80-b1a1-13b9f7eb1119">OnReaderFailure</a> callback functions, the multiple callback functions can run simultaneously.

</li>
<li>
If the driver has specified the default <i>NumPendingReads</i> value when it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff560395">IWDFUsbTargetPipe2::ConfigureContinuousReader</a> (or if it specifies any <i>NumPendingReads</i> value that is greater than 1), and if a read request completes while the <b>OnReaderCompletion</b> callback function is executing, the framework can call the <b>OnReaderCompletion</b> callback function again before the callback function returns.

</li>
<li>
The framework does not synchronize these callback functions with any other callback functions.

</li>
</ul>
When your driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff560395">IWDFUsbTargetPipe2::ConfigureContinuousReader</a>, it can specify an <a href="https://msdn.microsoft.com/library/windows/hardware/ff556760">IObjectCleanup::OnCleanup</a> callback function. The framework will call that callback function when it attempts to delete the memory object, after the <b>OnReaderCompletion</b> callback function returns. 

For more information about the <b>OnReaderCompletion</b> callback function and USB I/O targets, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/usb-i-o-targets-in-umdf">Handling a USB I/O Target</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556908">IUsbTargetPipeContinuousReaderCallbackReadComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556915">IUsbTargetPipeContinuousReaderCallbackReadersFailed::OnReaderFailure</a>
 

 

