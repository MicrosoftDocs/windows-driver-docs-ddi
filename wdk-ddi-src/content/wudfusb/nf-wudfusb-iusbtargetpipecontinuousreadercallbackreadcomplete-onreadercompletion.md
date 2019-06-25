---
UID: NF:wudfusb.IUsbTargetPipeContinuousReaderCallbackReadComplete.OnReaderCompletion
title: IUsbTargetPipeContinuousReaderCallbackReadComplete::OnReaderCompletion (wudfusb.h)
description: A driver's OnReaderCompletion event callback function informs the driver that a continuous reader has successfully completed a read request.
old-location: wdf\iusbtargetpipecontinuousreadercallbackreadcomplete_onreadercompletion.htm
tech.root: wdf
ms.assetid: 946e0206-7609-4dc7-91c2-a6aadad91751
ms.date: 02/26/2018
ms.keywords: IUsbTargetPipeContinuousReaderCallbackReadComplete interface,OnReaderCompletion method, IUsbTargetPipeContinuousReaderCallbackReadComplete.OnReaderCompletion, IUsbTargetPipeContinuousReaderCallbackReadComplete::OnReaderCompletion, OnReaderCompletion, OnReaderCompletion method, OnReaderCompletion method,IUsbTargetPipeContinuousReaderCallbackReadComplete interface, UMDFUSBref_a221433f-9a32-4205-8f12-a0c891dbe8bf.xml, umdf.iusbtargetpipecontinuousreadercallbackreadcomplete_onreadercompletion, wdf.iusbtargetpipecontinuousreadercallbackreadcomplete_onreadercompletion, wudfusb/IUsbTargetPipeContinuousReaderCallbackReadComplete::OnReaderCompletion
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
- IUsbTargetPipeContinuousReaderCallbackReadComplete.OnReaderCompletion
product:
- Windows
targetos: Windows
req.typenames: 
---

# IUsbTargetPipeContinuousReaderCallbackReadComplete::OnReaderCompletion


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver's <b>OnReaderCompletion</b> event callback function informs the driver that a continuous reader has successfully completed a read request.


## -parameters




### -param pPipe [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nn-wudfusb-iwdfusbtargetpipe">IWDFUsbTargetPipe</a> interface for the USB pipe on which the driver has enabled a continuous reader.


### -param pMemory [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfmemory">IWDFMemory</a> interface for a read buffer that contains data that was read from the USB pipe.


### -param NumBytesTransferred [in]

The number of bytes that the read buffer contains.


### -param Context [in]

A pointer to driver-supplied context information that the driver provided when it previously called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nf-wudfusb-iwdfusbtargetpipe2-configurecontinuousreader">IWDFUsbTargetPipe2::ConfigureContinuousReader</a>.


## -returns



None.




## -remarks



To register an <b>IUsbTargetPipeContinuousReaderCallbackReadComplete::OnReaderCompletion</b> callback function, your driver must provide a pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nn-wudfusb-iusbtargetpipecontinuousreadercallbackreadcomplete">IUsbTargetPipeContinuousReaderCallbackReadComplete</a> interface when it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nf-wudfusb-iwdfusbtargetpipe2-configurecontinuousreader">IWDFUsbTargetPipe2::ConfigureContinuousReader</a>.

If a driver has created a continuous reader for a USB pipe, the framework calls the driver's <b>OnReaderCompletion</b> callback function each time the driver's I/O target successfully completes a read request. If the I/O target does not successfully complete a request, the framework calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nf-wudfusb-iusbtargetpipecontinuousreadercallbackreadersfailed-onreaderfailure">IUsbTargetPipeContinuousReaderCallbackReadersFailed::OnReaderFailure</a> callback function. 

To access the buffer that contains data that was read from the device, the driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfmemory-getdatabuffer">IWDFMemory::GetDataBuffer</a>. The framework writes the data into the buffer, after the header that is defined by the <i>HeaderLength</i> parameter of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nf-wudfusb-iwdfusbtargetpipe2-configurecontinuousreader">IWDFUsbTargetPipe2::ConfigureContinuousReader</a>. Note that the pointer that <b>IWDFMemory::GetDataBuffer</b> returns points to the beginning of the header, but the <b>OnReaderCompletion</b> callback function's <i>NumBytesTransferred</i> parameter does not include the header's length.

By default, the framework deletes the buffer's memory object after the <b>OnReaderCompletion</b> callback function returns. However, you might want the memory object to remain valid after the callback function returns. For example, you might want your driver to store the memory object's interface pointer in the framework pipe object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfobject-assigncontext">context space</a> so that the driver can process the memory object's contents after the callback function returns. To extend the lifetime of the memory object, the callback function must call the buffer's <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/umdf-based-on-com-subset">IWDFMemory::AddRef</a> method. Subsequently, the driver must call the buffer's <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/umdf-based-on-com-subset">IWDFMemory::Release</a> method so that the framework can delete the object.

The framework synchronizes calls to the <b>OnReaderCompletion</b> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nf-wudfusb-iusbtargetpipecontinuousreadercallbackreadersfailed-onreaderfailure">IUsbTargetPipeContinuousReaderCallbackReadersFailed::OnReaderFailure</a> callback functions according to the following rules:

<ul>
<li>
These callback functions do not run simultaneously for an individual USB pipe.

</li>
<li>
If the driver creates multiple continuous readers for multiple USB pipes, with multiple <b>OnReaderCompletion</b> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nf-wudfusb-iusbtargetpipecontinuousreadercallbackreadersfailed-onreaderfailure">OnReaderFailure</a> callback functions, the multiple callback functions can run simultaneously.

</li>
<li>
If the driver has specified the default <i>NumPendingReads</i> value when it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nf-wudfusb-iwdfusbtargetpipe2-configurecontinuousreader">IWDFUsbTargetPipe2::ConfigureContinuousReader</a> (or if it specifies any <i>NumPendingReads</i> value that is greater than 1), and if a read request completes while the <b>OnReaderCompletion</b> callback function is executing, the framework can call the <b>OnReaderCompletion</b> callback function again before the callback function returns.

</li>
<li>
The framework does not synchronize these callback functions with any other callback functions.

</li>
</ul>
When your driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nf-wudfusb-iwdfusbtargetpipe2-configurecontinuousreader">IWDFUsbTargetPipe2::ConfigureContinuousReader</a>, it can specify an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iobjectcleanup-oncleanup">IObjectCleanup::OnCleanup</a> callback function. The framework will call that callback function when it attempts to delete the memory object, after the <b>OnReaderCompletion</b> callback function returns. 

For more information about the <b>OnReaderCompletion</b> callback function and USB I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/usb-i-o-targets-in-umdf">Handling a USB I/O Target</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nn-wudfusb-iusbtargetpipecontinuousreadercallbackreadcomplete">IUsbTargetPipeContinuousReaderCallbackReadComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nf-wudfusb-iusbtargetpipecontinuousreadercallbackreadersfailed-onreaderfailure">IUsbTargetPipeContinuousReaderCallbackReadersFailed::OnReaderFailure</a>
 

 

