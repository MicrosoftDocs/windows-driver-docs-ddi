---
UID: NF:wudfddi.IWDFRemoteTarget.Close
title: IWDFRemoteTarget::Close (wudfddi.h)
description: The Close method closes a remote I/O target.
old-location: wdf\iwdfremotetarget_close.htm
tech.root: wdf
ms.assetid: c24082c4-0c79-4956-8035-79198cb2b7ee
ms.date: 02/26/2018
ms.keywords: Close, Close method, Close method,IWDFRemoteTarget interface, IWDFRemoteTarget interface,Close method, IWDFRemoteTarget.Close, IWDFRemoteTarget::Close, UMDFIoTargetObjectRef_1e5aba5f-fd82-4d59-abb6-915e8a49ad22.xml, umdf.iwdfremotetarget_close, wdf.iwdfremotetarget_close, wudfddi/IWDFRemoteTarget::Close
f1_keywords:
 - "wudfddi/IWDFRemoteTarget.Close"
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
- IWDFRemoteTarget.Close
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFRemoteTarget::Close


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Close</b> method closes a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/general-i-o-targets-in-umdf">remote I/O target</a>.


## -returns



The <b>Close</b> method always returns S_OK.




## -remarks



If your driver provides an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iremotetargetcallbackremoval-onremotetargetremovecomplete">IRemoteTargetCallbackRemoval::OnRemoteTargetRemoveComplete</a> callback function, the callback function must call <b>Close</b>. 

The <b>Close</b> method completes or cancels all I/O requests that the driver has sent to the I/O target. 

After a driver calls <b>Close</b>, the driver cannot send I/O requests to the I/O target. 

For more information about the <b>Close</b> method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/controlling-a-general-i-o-target-s-state-in-umdf">Controlling a General I/O Target's State in UMDF</a>.


#### Examples

The following code example shows an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iremotetargetcallbackremoval-onremotetargetremovecomplete">IRemoteTargetCallbackRemoval::OnRemoteTargetRemoveComplete</a> callback function that calls <b>Close</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID 
STDMETHODCALLTYPE
CMyRemoteTarget::OnRemoteTargetRemoveComplete(
    __in IWDFRemoteTarget *FxTarget
    )
{
    //
    // Here, do any driver-specific actions that your driver requires
    // to close the remote I/O target.
    //
...
    //
    // Close the target.
    //
    FxTarget->Close();
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfremotetarget">IWDFRemoteTarget</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfremotetarget-closeforqueryremove">IWDFRemoteTarget::CloseForQueryRemove</a>
 

 

