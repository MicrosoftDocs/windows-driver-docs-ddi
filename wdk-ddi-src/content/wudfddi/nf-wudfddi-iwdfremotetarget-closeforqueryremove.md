---
UID: NF:wudfddi.IWDFRemoteTarget.CloseForQueryRemove
title: IWDFRemoteTarget::CloseForQueryRemove method
author: windows-driver-content
description: The CloseForQueryRemove method closes a remote I/O target because the operating system might allow the device to be removed.
old-location: wdf\iwdfremotetarget_closeforqueryremove.htm
old-project: wdf
ms.assetid: 9e23ae80-7c39-4cee-b1ab-80085f24d41f
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: CloseForQueryRemove method, CloseForQueryRemove method, IWDFRemoteTarget interface, CloseForQueryRemove,IWDFRemoteTarget.CloseForQueryRemove, IWDFRemoteTarget, IWDFRemoteTarget interface, CloseForQueryRemove method, IWDFRemoteTarget::CloseForQueryRemove, UMDFIoTargetObjectRef_b816e346-75b1-4da2-a9cf-f6db32abb3ed.xml, umdf.iwdfremotetarget_closeforqueryremove, wdf.iwdfremotetarget_closeforqueryremove, wudfddi/IWDFRemoteTarget::CloseForQueryRemove
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
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
req.lib: wudfddi.h
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFRemoteTarget.CloseForQueryRemove
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFRemoteTarget::CloseForQueryRemove method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CloseForQueryRemove</b> method closes a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/general-i-o-targets-in-umdf">remote I/O target</a> because the operating system might allow the device to be removed.


## -syntax


````
HRESULT CloseForQueryRemove();
````


## -parameters






## -returns



The <b>CloseForQueryRemove</b> method always returns S_OK.




## -remarks



If your driver provides an <a href="https://msdn.microsoft.com/library/windows/hardware/ff556897">IRemoteTargetCallbackRemoval::OnRemoteTargetQueryRemove</a> callback function, the callback function must call <b>CloseForQueryRemove</b> if it returns <b>TRUE</b> to indicate that the device can be removed. 

The <b>CloseForQueryRemove</b> method completes or cancels all I/O requests that the driver has sent to the I/O target.

After a driver calls <b>CloseForQueryRemove</b>, the driver cannot send I/O requests to the I/O target until it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff560278">IWDFRemoteTarget::Reopen</a>.

For more information about the <b>CloseForQueryRemove</b> method, see <a href="https://msdn.microsoft.com/479487b2-5ce5-4522-b195-58ee50d210b6">Controlling a General I/O Target's State in UMDF</a>.


#### Examples

The following code example shows an <a href="https://msdn.microsoft.com/library/windows/hardware/ff556897">IRemoteTargetCallbackRemoval::OnRemoteTargetQueryRemove</a> callback function that calls <b>CloseForQueryRemove</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>BOOL
STDMETHODCALLTYPE
CMyRemoteTarget::OnRemoteTargetQueryRemove(
    __in IWDFRemoteTarget  *FxTarget
    )
{
    //
    // Here, do any driver-specific actions that your driver requires
    // to stop sending I/O requests to the I/O target.
    //
...
    //
    // Close the target.
    //
    FxTarget-&gt;CloseForQueryRemove();

    //
    // Return TRUE if you want to allow removal of the device.
    //
    return TRUE;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560253">IWDFRemoteTarget::Close</a>



<a href="..\wudfddi\nn-wudfddi-iwdfremotetarget.md">IWDFRemoteTarget</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFRemoteTarget::CloseForQueryRemove method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

