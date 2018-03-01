---
UID: NF:wudfddi.IWDFRemoteTarget.Reopen
title: IWDFRemoteTarget::Reopen method
author: windows-driver-content
description: The Reopen method reopens a remote I/O target after it has been temporarily closed.
old-location: wdf\iwdfremotetarget_reopen.htm
old-project: wdf
ms.assetid: 904904e7-ca59-4dcb-92db-8c7f6a9cbff7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IWDFRemoteTarget, IWDFRemoteTarget interface, Reopen method, IWDFRemoteTarget::Reopen, Reopen method, Reopen method, IWDFRemoteTarget interface, Reopen,IWDFRemoteTarget.Reopen, UMDFIoTargetObjectRef_13b81124-2d7f-4fed-b4f9-1a5cb647a811.xml, umdf.iwdfremotetarget_reopen, wdf.iwdfremotetarget_reopen, wudfddi/IWDFRemoteTarget::Reopen
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
-	IWDFRemoteTarget.Reopen
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFRemoteTarget::Reopen method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Reopen</b> method reopens a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/general-i-o-targets-in-umdf">remote I/O target</a> after it has been temporarily closed.


## -syntax


````
HRESULT Reopen();
````


## -parameters






## -returns



<b>Reopen</b> returns S_OK if the operation succeeds. Otherwise, the method might return the following value:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
The framework's attempt to allocate memory failed. 

</td>
</tr>
</table>
 

This method might return one of the other values that Winerror.h contains.



The framework's <a href="https://msdn.microsoft.com/e84993e1-da10-4041-8fc7-7f40806ee454">verifier</a> reports an error if the framework cannot open the file.




## -remarks



Typically, a driver calls <b>Reopen</b> from within the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556899">IRemoteTargetCallbackRemoval::OnRemoteTargetRemoveCanceled</a> callback function, but <b>Reopen</b> can instead be called after <b>OnRemoteTargetRemoveCanceled</b> returns. 

Reopen uses the file or interface name that the driver previously specified to <a href="https://msdn.microsoft.com/library/windows/hardware/ff560273">IWDFRemoteTarget::OpenFileByName</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff560276">IWDFRemoteTarget::OpenRemoteInterface</a>. If you want to change the file or interface that the driver is using, the driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff560253">IWDFRemoteTarget::Close</a>, and then it can call <b>OpenFileByName</b> or <b>OpenRemoteInterface</b> instead of <b>Reopen</b>.

For more information about <b>Reopen</b> and how to use remote I/O targets in UMDF-based drivers, see <a href="https://msdn.microsoft.com/479487b2-5ce5-4522-b195-58ee50d210b6">Controlling a General I/O Target's State in UMDF</a>.


#### Examples

The following code example shows an <a href="https://msdn.microsoft.com/library/windows/hardware/ff556899">IRemoteTargetCallbackRemoval::OnRemoteTargetRemoveCanceled</a> callback function that calls <b>Reopen</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID 
STDMETHODCALLTYPE
CMyRemoteTarget::OnRemoteTargetRemoveCanceled(
    __in IWDFRemoteTarget* FxTarget
    )
{
 if (S_OK == (FxTarget-&gt;Reopen()))
    {
    //
    // Resume sending I/O requests to the remote target.
    //
    ...
    }
 else
    {
       FxTarget-&gt;Close();
    }
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfremotetarget.md">IWDFRemoteTarget</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560253">IWDFRemoteTarget::Close</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFRemoteTarget::Reopen method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

