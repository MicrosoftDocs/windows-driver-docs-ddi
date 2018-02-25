---
UID: NF:wudfddi.IWDFRemoteTarget.Stop
title: IWDFRemoteTarget::Stop method
author: windows-driver-content
description: The Stop method temporarily stops a remote I/O target.
old-location: wdf\iwdfremotetarget_stop.htm
old-project: wdf
ms.assetid: 4aaef251-7387-4e42-a7ae-e08120fc95ff
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , ,, ., :, D, F, I, IWDFRemoteTarget, IWDFRemoteTarget interface, Stop method, IWDFRemoteTarget::Stop, R, S, Stop method, Stop method, IWDFRemoteTarget interface, Stop,IWDFRemoteTarget.Stop, T, UMDFIoTargetObjectRef_a7d1be6f-890c-4e06-9544-7bd18876b56e.xml, W, a, e, g, m, o, p, r, t, umdf.iwdfremotetarget_stop, wdf.iwdfremotetarget_stop, wudfddi/IWDFRemoteTarget::Stop"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFRemoteTarget.Stop
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFRemoteTarget::Stop method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Stop</b> method temporarily stops a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/general-i-o-targets-in-umdf">remote I/O target</a>.


## -syntax


````
HRESULT Stop(
  [in] WDF_IO_TARGET_SENT_IO_ACTION Action
);
````


## -parameters




### -param Action [in]

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_io_target_sent_io_action.md">WDF_IO_TARGET_SENT_IO_ACTION</a>-typed value that specifies how the framework should handle I/O requests that the driver has sent to the remote I/O target, if the target has not completed the requests.


## -returns



<b>Stop</b> always returns S_OK.




## -remarks



If your driver can detect recoverable errors on a remote I/O target, you might want your driver to call <b>Stop</b> to temporarily stop sending requests, and later call <a href="https://msdn.microsoft.com/library/windows/hardware/ff560280">IWDFRemoteTarget::Start</a> to resume sending requests.

For more information about <b>Stop</b>, and how to use remote I/O targets in UMDF-based drivers, see <a href="https://msdn.microsoft.com/479487b2-5ce5-4522-b195-58ee50d210b6">Controlling a General I/O Target's State in UMDF</a>.


#### Examples

The following code example stops a remote I/O target.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>RemoteTarget-&gt;Stop();</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfremotetarget.md">IWDFRemoteTarget</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560280">IWDFRemoteTarget::Start</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFRemoteTarget::Stop method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

