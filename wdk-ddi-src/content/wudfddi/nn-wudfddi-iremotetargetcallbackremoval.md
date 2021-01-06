---
UID: NN:wudfddi.IRemoteTargetCallbackRemoval
title: IRemoteTargetCallbackRemoval (wudfddi.h)
description: The IRemoteTargetCallbackRemoval interface provides callback functions that the framework calls to notify the driver about events that are associated with the removal of a remote I/O target.
old-location: wdf\iremotetargetcallbackremoval.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["IRemoteTargetCallbackRemoval interface"]
ms.keywords: IRemoteTargetCallbackRemoval, IRemoteTargetCallbackRemoval interface, IRemoteTargetCallbackRemoval interface,described, UMDFIoTargetObjectRef_7508512a-9bfc-4563-bf01-48e9caf6ba4f.xml, umdf.iremotetargetcallbackremoval, wdf.iremotetargetcallbackremoval, wudfddi/IRemoteTargetCallbackRemoval
req.header: wudfddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IRemoteTargetCallbackRemoval
 - wudfddi/IRemoteTargetCallbackRemoval
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - wudfddi.h
api_name:
 - IRemoteTargetCallbackRemoval
---

# IRemoteTargetCallbackRemoval interface


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IRemoteTargetCallbackRemoval</b> interface provides callback functions that the framework calls to notify the driver about events that are associated with the removal of a <a href="/windows-hardware/drivers/wdf/general-i-o-targets-in-umdf">remote I/O target</a>.

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IRemoteTargetCallbackRemoval</b> interface inherits from the <a href="/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IRemoteTargetCallbackRemoval</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -remarks

If your driver supports an <b>IRemoteTargetCallbackRemoval</b> interface for a device, the <b>IUnknown::QueryInterface</b> method that the driver passes to <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice2-createremotetarget">IWDFDevice2::CreateRemoteTarget</a> must return the interface.
