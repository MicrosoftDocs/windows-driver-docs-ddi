---
UID: NF:wudfusb.IWDFUsbTargetPipe.Flush
title: IWDFUsbTargetPipe::Flush method
author: windows-driver-content
description: The Flush method discards any data that WinUsb saved when the device returned more data than the client requested.
old-location: wdf\iwdfusbtargetpipe_flush.htm
old-project: wdf
ms.assetid: d8e5cbf7-62c7-458d-a527-2508a8a5d066
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , ,, ., :, D, F, Flush method, Flush method, IWDFUsbTargetPipe interface, Flush,IWDFUsbTargetPipe.Flush, I, IWDFUsbTargetPipe, IWDFUsbTargetPipe interface, Flush method, IWDFUsbTargetPipe::Flush, P, T, U, UMDFUSBref_5a569ab8-ccbd-47cc-93a6-8e61f366e6ee.xml, W, a, b, e, g, h, i, l, p, r, s, t, u, umdf.iwdfusbtargetpipe_flush, wdf.iwdfusbtargetpipe_flush, wudfusb/IWDFUsbTargetPipe::Flush"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfusb.h
req.include-header: Wudfusb.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: wudfusb.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFUsbTargetPipe.Flush
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# IWDFUsbTargetPipe::Flush method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Flush</b> method discards any data that WinUsb saved when the device returned more data than the client requested.


## -syntax


````
HRESULT  Flush();
````


## -parameters






## -returns



<b>Flush</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK </b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/library/windows/hardware/hh463886">Flush</a> successfully discarded any extra data that WinUsb saved. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY </b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/library/windows/hardware/hh463886">Flush</a> encountered an allocation failure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>An error code that is defined in Winerror.h</b></dt>
</dl>
</td>
<td width="60%">
This value corresponds to the error code that the WinUsb API returned.

</td>
</tr>
</table>
 




## -remarks



The <b>Flush</b> method generates a UMDF request and synchronously sends the request to the I/O target.

For more information about how <b>Flush</b> works, see the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540227">WinUsb_FlushPipe</a> function.




## -see-also

<a href="..\wudfusb\nn-wudfusb-iwdfusbtargetpipe.md">IWDFUsbTargetPipe</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540227">WinUsb_FlushPipe</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUsbTargetPipe::Flush method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

