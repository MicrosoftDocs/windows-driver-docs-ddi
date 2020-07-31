---
UID: NF:wudfddi.IWDFRemoteTarget.GetState
title: IWDFRemoteTarget::GetState (wudfddi.h)
description: The GetState method returns the current state of a remote I/O target.
old-location: wdf\iwdfremotetarget_getstate.htm
tech.root: wdf
ms.assetid: 3918d764-c5bb-42b6-8b06-a2d544511a96
ms.date: 02/26/2018
keywords: ["IWDFRemoteTarget::GetState"]
ms.keywords: GetState, GetState method, GetState method,IWDFRemoteTarget interface, IWDFRemoteTarget interface,GetState method, IWDFRemoteTarget.GetState, IWDFRemoteTarget::GetState, UMDFIoTargetObjectRef_34bf0f92-927a-4733-9897-5aa146998136.xml, umdf.iwdfremotetarget_getstate, wdf.iwdfremotetarget_getstate, wudfddi/IWDFRemoteTarget::GetState
f1_keywords:
 - "wudfddi/IWDFRemoteTarget.GetState"
 - "IWDFRemoteTarget.GetState"
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
- IWDFRemoteTarget.GetState
targetos: Windows
req.typenames: 
---

# IWDFRemoteTarget::GetState


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetState</b> method returns the current state of a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/general-i-o-targets-in-umdf">remote I/O target</a>.


## -returns



<b>GetState</b> returns a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ne-wdfiotarget-_wdf_io_target_state">WDF_IO_TARGET_STATE</a>-typed value that identifies the state of the remote I/O target.




## -remarks



For more information about remote I/O target states, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/controlling-a-general-i-o-target-s-state-in-umdf">Controlling a General I/O Target's State in UMDF</a>.


#### Examples

The following code example determines whether a remote I/O target is closed.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>if (FxRemoteTarget->GetState() == WdfIoTargetClosed)
{
...
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfremotetarget">IWDFRemoteTarget</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ne-wdfiotarget-_wdf_io_target_state">WDF_IO_TARGET_STATE</a>
 

 

