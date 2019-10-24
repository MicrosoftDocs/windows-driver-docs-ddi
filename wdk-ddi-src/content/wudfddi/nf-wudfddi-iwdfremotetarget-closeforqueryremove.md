---
UID: NF:wudfddi.IWDFRemoteTarget.CloseForQueryRemove
title: IWDFRemoteTarget::CloseForQueryRemove (wudfddi.h)
description: The CloseForQueryRemove method closes a remote I/O target because the operating system might allow the device to be removed.
old-location: wdf\iwdfremotetarget_closeforqueryremove.htm
tech.root: wdf
ms.assetid: 9e23ae80-7c39-4cee-b1ab-80085f24d41f
ms.date: 02/26/2018
ms.keywords: CloseForQueryRemove, CloseForQueryRemove method, CloseForQueryRemove method,IWDFRemoteTarget interface, IWDFRemoteTarget interface,CloseForQueryRemove method, IWDFRemoteTarget.CloseForQueryRemove, IWDFRemoteTarget::CloseForQueryRemove, UMDFIoTargetObjectRef_b816e346-75b1-4da2-a9cf-f6db32abb3ed.xml, umdf.iwdfremotetarget_closeforqueryremove, wdf.iwdfremotetarget_closeforqueryremove, wudfddi/IWDFRemoteTarget::CloseForQueryRemove
ms.topic: method
f1_keywords:
 - "wudfddi/IWDFRemoteTarget.CloseForQueryRemove"
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
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFRemoteTarget.CloseForQueryRemove
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFRemoteTarget::CloseForQueryRemove


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CloseForQueryRemove</b> method closes a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/general-i-o-targets-in-umdf">remote I/O target</a> because the operating system might allow the device to be removed.


## -parameters






## -returns



The <b>CloseForQueryRemove</b> method always returns S_OK.




## -remarks



If your driver provides an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iremotetargetcallbackremoval-onremotetargetqueryremove">IRemoteTargetCallbackRemoval::OnRemoteTargetQueryRemove</a> callback function, the callback function must call <b>CloseForQueryRemove</b> if it returns <b>TRUE</b> to indicate that the device can be removed. 

The <b>CloseForQueryRemove</b> method completes or cancels all I/O requests that the driver has sent to the I/O target.

After a driver calls <b>CloseForQueryRemove</b>, the driver cannot send I/O requests to the I/O target until it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfremotetarget-reopen">IWDFRemoteTarget::Reopen</a>.

For more information about the <b>CloseForQueryRemove</b> method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/controlling-a-general-i-o-target-s-state-in-umdf">Controlling a General I/O Target's State in UMDF</a>.


#### Examples

The following code example shows an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iremotetargetcallbackremoval-onremotetargetqueryremove">IRemoteTargetCallbackRemoval::OnRemoteTargetQueryRemove</a> callback function that calls <b>CloseForQueryRemove</b>.

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
    FxTarget->CloseForQueryRemove();

    //
    // Return TRUE if you want to allow removal of the device.
    //
    return TRUE;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfremotetarget">IWDFRemoteTarget</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfremotetarget-close">IWDFRemoteTarget::Close</a>
 

 

