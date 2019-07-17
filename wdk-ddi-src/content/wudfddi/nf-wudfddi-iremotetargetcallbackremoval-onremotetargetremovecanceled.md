---
UID: NF:wudfddi.IRemoteTargetCallbackRemoval.OnRemoteTargetRemoveCanceled
title: IRemoteTargetCallbackRemoval::OnRemoteTargetRemoveCanceled (wudfddi.h)
description: A UMDF-based driver's OnRemoteTargetRemoveCanceled event callback function performs operations that are necessary when the operating system cancels the removal of a remote I/O target's device.
old-location: wdf\iremotetargetcallbackremoval_onremotetargetremovecanceled.htm
tech.root: wdf
ms.assetid: 26a6e9e7-f1bb-4174-a640-f665cecfd191
ms.date: 02/26/2018
ms.keywords: IRemoteTargetCallbackRemoval interface,OnRemoteTargetRemoveCanceled method, IRemoteTargetCallbackRemoval.OnRemoteTargetRemoveCanceled, IRemoteTargetCallbackRemoval::OnRemoteTargetRemoveCanceled, OnRemoteTargetRemoveCanceled, OnRemoteTargetRemoveCanceled method, OnRemoteTargetRemoveCanceled method,IRemoteTargetCallbackRemoval interface, UMDFIoTargetObjectRef_aa4d89fd-ad91-46ea-a55d-4c89d65da13e.xml, umdf.iremotetargetcallbackremoval_onremotetargetremovecanceled, wdf.iremotetargetcallbackremoval_onremotetargetremovecanceled, wudfddi/IRemoteTargetCallbackRemoval::OnRemoteTargetRemoveCanceled
ms.topic: method
f1_keywords:
 - "wudfddi/IRemoteTargetCallbackRemoval.OnRemoteTargetRemoveCanceled"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Wudfddi.h
api_name:
- IRemoteTargetCallbackRemoval.OnRemoteTargetRemoveCanceled
product:
- Windows
targetos: Windows
req.typenames: 
---

# IRemoteTargetCallbackRemoval::OnRemoteTargetRemoveCanceled


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A UMDF-based driver's <b>OnRemoteTargetRemoveCanceled</b> event callback function performs operations that are necessary when the operating system cancels the removal of a remote I/O target's device.


## -parameters




### -param pWdfRemoteTarget [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfremotetarget">IWDFRemoteTarget</a> interface of a remote target object that represents a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/general-i-o-targets-in-umdf">remote I/O target</a>. The driver obtains this pointer when it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfdevice2-createremotetarget">IWDFDevice2::CreateRemoteTarget</a>.


## -returns



None.




## -remarks



If your driver provides an <b>OnRemoteTargetRemoveCanceled</b> event callback function, the callback function must do the following:

<ol>
<li>
Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfremotetarget-reopen">IWDFRemoteTarget::Reopen</a>.

</li>
<li>
Do any driver-specific actions that your driver requires to restart I/O to the remote I/O target.

</li>
</ol>
If the driver does not provide this callback function, the framework calls <b>IWDFRemoteTarget::Reopen</b> for the driver.

For more information about the <b>OnRemoteTargetRemoveCanceled</b> event callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/controlling-a-general-i-o-target-s-state-in-umdf">Controlling a General I/O Target's State in UMDF</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iremotetargetcallbackremoval">IRemoteTargetCallbackRemoval</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iremotetargetcallbackremoval-onremotetargetqueryremove">IRemoteTargetCallbackRemoval::OnRemoteTargetQueryRemove</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iremotetargetcallbackremoval-onremotetargetremovecomplete">IRemoteTargetCallbackRemoval::OnRemoteTargetRemoveComplete</a>
 

 

