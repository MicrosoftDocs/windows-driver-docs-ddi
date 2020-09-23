---
UID: NF:wudfddi.IRemoteTargetCallbackRemoval.OnRemoteTargetQueryRemove
title: IRemoteTargetCallbackRemoval::OnRemoteTargetQueryRemove (wudfddi.h)
description: A UMDF-based driver's OnRemoteTargetQueryRemove event callback function determines whether a remote I/O target's device can be stopped and removed.
old-location: wdf\iremotetargetcallbackremoval_onremotetargetqueryremove.htm
tech.root: wdf
ms.assetid: 10a9510a-a11c-46fa-adb8-b122f6c571f4
ms.date: 02/26/2018
keywords: ["IRemoteTargetCallbackRemoval::OnRemoteTargetQueryRemove"]
ms.keywords: IRemoteTargetCallbackRemoval interface,OnRemoteTargetQueryRemove method, IRemoteTargetCallbackRemoval.OnRemoteTargetQueryRemove, IRemoteTargetCallbackRemoval::OnRemoteTargetQueryRemove, OnRemoteTargetQueryRemove, OnRemoteTargetQueryRemove method, OnRemoteTargetQueryRemove method,IRemoteTargetCallbackRemoval interface, UMDFIoTargetObjectRef_7cdc408d-7527-4af9-9fef-d8ccb9c1d4c3.xml, umdf.iremotetargetcallbackremoval_onremotetargetqueryremove, wdf.iremotetargetcallbackremoval_onremotetargetqueryremove, wudfddi/IRemoteTargetCallbackRemoval::OnRemoteTargetQueryRemove
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
 - IRemoteTargetCallbackRemoval::OnRemoteTargetQueryRemove
 - wudfddi/IRemoteTargetCallbackRemoval::OnRemoteTargetQueryRemove
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Wudfddi.h
api_name:
 - IRemoteTargetCallbackRemoval.OnRemoteTargetQueryRemove
---

# IRemoteTargetCallbackRemoval::OnRemoteTargetQueryRemove


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A UMDF-based driver's <b>OnRemoteTargetQueryRemove</b> event callback function determines whether a remote I/O target's device can be stopped and removed.

## -parameters

### -param pWdfRemoteTarget 

[in]
A pointer to the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfremotetarget">IWDFRemoteTarget</a> interface of a remote target object that represents a <a href="/windows-hardware/drivers/wdf/general-i-o-targets-in-umdf">remote I/O target</a>. The driver obtains this pointer when it calls <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice2-createremotetarget">IWDFDevice2::CreateRemoteTarget</a>.

## -returns

If the driver determines that the device can be stopped and removed, the <b>OnRemoteTargetQueryRemove</b> event callback function must return <b>TRUE</b>. Otherwise, the callback function must return <b>FALSE</b>.

## -remarks

If your driver provides an <b>OnRemoteTargetQueryRemove</b> event callback function, the callback function should determine if the operating system should allow removal of the device. If the driver determines that the device can be removed, it should do the following:

<ol>
<li>
Do any driver-specific actions needed to stop I/O to the remote target.

</li>
<li>
Call <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfremotetarget-closeforqueryremove">IWDFRemoteTarget::CloseForQueryRemove</a>.

</li>
<li>
Return <b>TRUE</b> to indicate that the removal can occur. 

</li>
</ol>
If the driver determines that the device should not be removed, the callback function must return <b>FALSE</b>. Typically, drivers should avoid returning <b>FALSE</b>, because a <b>FALSE</b> return value can cause Windows to restart.

If the driver does not provide this callback function, the framework calls <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfremotetarget-closeforqueryremove">IWDFRemoteTarget::CloseForQueryRemove</a> for the driver. In other words, the framework always allows the device to be removed unless the driver provides an <b>OnRemoteTargetQueryRemove</b> event callback function.

For more information about the <b>OnRemoteTargetQueryRemove</b> event callback function, see <a href="/windows-hardware/drivers/wdf/controlling-a-general-i-o-target-s-state-in-umdf">Controlling a General I/O Target's State in UMDF</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iremotetargetcallbackremoval">IRemoteTargetCallbackRemoval</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iremotetargetcallbackremoval-onremotetargetremovecanceled">IRemoteTargetCallbackRemoval::OnRemoteTargetRemoveCanceled</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iremotetargetcallbackremoval-onremotetargetremovecomplete">IRemoteTargetCallbackRemoval::OnRemoteTargetRemoveComplete</a>