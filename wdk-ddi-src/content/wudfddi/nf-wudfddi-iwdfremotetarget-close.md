---
UID: NF:wudfddi.IWDFRemoteTarget.Close
title: IWDFRemoteTarget::Close method
author: windows-driver-content
description: The Close method closes a remote I/O target.
old-location: wdf\iwdfremotetarget_close.htm
old-project: wdf
ms.assetid: c24082c4-0c79-4956-8035-79198cb2b7ee
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFRemoteTarget, IWDFRemoteTarget::Close, Close
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
req.alt-api: IWDFRemoteTarget.Close
req.alt-loc: WUDFx.dll
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
req.typenames: *PPOWER_ACTION, POWER_ACTION
req.product: Windows 10 or later.
---

# IWDFRemoteTarget::Close method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Close</b> method closes a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/general-i-o-targets-in-umdf">remote I/O target</a>.



## -syntax

````
HRESULT Close();
````


## -parameters


## -returns
The <b>Close</b> method always returns S_OK.

The <b>Close</b> method always returns S_OK.

The <b>Close</b> method always returns S_OK.


## -remarks
If your driver provides an <a href="https://msdn.microsoft.com/library/windows/hardware/ff556900">IRemoteTargetCallbackRemoval::OnRemoteTargetRemoveComplete</a> callback function, the callback function must call <b>Close</b>. 

The <b>Close</b> method completes or cancels all I/O requests that the driver has sent to the I/O target. 

After a driver calls <b>Close</b>, the driver cannot send I/O requests to the I/O target. 

For more information about the <b>Close</b> method, see <a href="https://msdn.microsoft.com/479487b2-5ce5-4522-b195-58ee50d210b6">Controlling a General I/O Target's State in UMDF</a>.

The following code example shows an <a href="https://msdn.microsoft.com/library/windows/hardware/ff556900">IRemoteTargetCallbackRemoval::OnRemoteTargetRemoveComplete</a> callback function that calls <b>Close</b>.


## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfremotetarget.md">IWDFRemoteTarget</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560259">IWDFRemoteTarget::CloseForQueryRemove</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFRemoteTarget::Close method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

