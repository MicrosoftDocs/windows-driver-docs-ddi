---
UID: NF:wudfddi.IRemoteTargetCallbackRemoval.OnRemoteTargetRemoveComplete
title: IRemoteTargetCallbackRemoval::OnRemoteTargetRemoveComplete (wudfddi.h)
description: A UMDF-based driver's OnRemoteTargetRemoveComplete event callback function performs operations that are necessary after the operating system completes the removal of a remote I/O target's device.
old-location: wdf\iremotetargetcallbackremoval_onremotetargetremovecomplete.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["IRemoteTargetCallbackRemoval::OnRemoteTargetRemoveComplete"]
ms.keywords: IRemoteTargetCallbackRemoval interface,OnRemoteTargetRemoveComplete method, IRemoteTargetCallbackRemoval.OnRemoteTargetRemoveComplete, IRemoteTargetCallbackRemoval::OnRemoteTargetRemoveComplete, OnRemoteTargetRemoveComplete, OnRemoteTargetRemoveComplete method, OnRemoteTargetRemoveComplete method,IRemoteTargetCallbackRemoval interface, UMDFIoTargetObjectRef_bec0246d-a3e9-41b2-b577-fef78c8e4668.xml, umdf.iremotetargetcallbackremoval_onremotetargetremovecomplete, wdf.iremotetargetcallbackremoval_onremotetargetremovecomplete, wudfddi/IRemoteTargetCallbackRemoval::OnRemoteTargetRemoveComplete
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
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IRemoteTargetCallbackRemoval::OnRemoteTargetRemoveComplete
 - wudfddi/IRemoteTargetCallbackRemoval::OnRemoteTargetRemoveComplete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Wudfddi.h
api_name:
 - IRemoteTargetCallbackRemoval::OnRemoteTargetRemoveComplete
---

# IRemoteTargetCallbackRemoval::OnRemoteTargetRemoveComplete


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A UMDF-based driver's <b>OnRemoteTargetRemoveComplete</b> event callback function performs operations that are necessary after the operating system completes the removal of a remote I/O target's device.

## -parameters

### -param pWdfRemoteTarget 

[in]
A pointer to the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfremotetarget">IWDFRemoteTarget</a> interface of a remote target object that represents a <a href="/windows-hardware/drivers/wdf/general-i-o-targets-in-umdf">remote I/O target</a>. The driver obtains this pointer when it calls <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice2-createremotetarget">IWDFDevice2::CreateRemoteTarget</a>.

## -remarks

If your driver provides an <b>OnRemoteTargetRemoveComplete</b> event callback function, the callback function should do the following:

<ol>
<li>
Do any driver-specific actions that your driver requires to close the remote I/O target.

</li>
<li>
Call <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfremotetarget-close">IWDFRemoteTarget::Close</a>.

</li>
</ol>
If the driver does not provide this callback function, the framework calls <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfremotetarget-close">IWDFRemoteTarget::Close</a> for the driver.

For more information about the <b>OnRemoteTargetRemoveComplete</b> event callback function, see <a href="/windows-hardware/drivers/wdf/controlling-a-general-i-o-target-s-state-in-umdf">Controlling a General I/O Target's State in UMDF</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iremotetargetcallbackremoval">IRemoteTargetCallbackRemoval</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iremotetargetcallbackremoval-onremotetargetqueryremove">IRemoteTargetCallbackRemoval::OnRemoteTargetQueryRemove</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iremotetargetcallbackremoval-onremotetargetremovecanceled">IRemoteTargetCallbackRemoval::OnRemoteTargetRemoveCanceled</a>

