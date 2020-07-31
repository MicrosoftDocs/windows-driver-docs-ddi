---
UID: NF:wudfddi.IWDFIoTargetStateManagement.GetState
title: IWDFIoTargetStateManagement::GetState (wudfddi.h)
description: The GetState method returns the current state of a local I/O target.
old-location: wdf\iwdfiotargetstatemanagement_getstate.htm
tech.root: wdf
ms.assetid: f915294f-457f-4913-b4b0-e94e1806a06d
ms.date: 02/26/2018
keywords: ["IWDFIoTargetStateManagement::GetState"]
ms.keywords: GetState, GetState method, GetState method,IWDFIoTargetStateManagement interface, IWDFIoTargetStateManagement interface,GetState method, IWDFIoTargetStateManagement.GetState, IWDFIoTargetStateManagement::GetState, UMDFIoTargetObjectRef_0a52ff77-9947-49a1-958a-ffe6e61ec169.xml, umdf.iwdfiotargetstatemanagement_getstate, wdf.iwdfiotargetstatemanagement_getstate, wudfddi/IWDFIoTargetStateManagement::GetState
f1_keywords:
 - "wudfddi/IWDFIoTargetStateManagement.GetState"
 - "IWDFIoTargetStateManagement.GetState"
req.header: wudfddi.h
req.include-header: Wudfddi.h
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
- IWDFIoTargetStateManagement.GetState
targetos: Windows
req.typenames: 
---

# IWDFIoTargetStateManagement::GetState


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetState</b> method returns the current state of a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/general-i-o-targets-in-umdf">local  I/O target</a>.


## -returns



<b>GetState</b> returns a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ne-wdfiotarget-_wdf_io_target_state">WDF_IO_TARGET_STATE</a>-typed value that identifies the state of the I/O target.




## -remarks



For more information about <b>GetState</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/controlling-a-general-i-o-target-s-state">Controlling a General I/O Target's State</a>. 



For more information about I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-i-o-targets-in-umdf">Using I/O Targets</a>.




#### Examples

The following code example determines whether a local I/O target is stopped.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>    if (m_pIoTargetInterruptPipeStateMgmt->GetState() == WdfIoTargetStopped)
    {
    ...
    }
</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiotargetstatemanagement">IWDFIoTargetStateManagement</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfremotetarget-getstate">IWDFRemoteTarget::GetState</a>
 

 

