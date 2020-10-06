---
UID: NN:wudfddi.IWDFRemoteInterfaceInitialize
title: IWDFRemoteInterfaceInitialize (wudfddi.h)
description: UMDF-based drivers receive the IWDFRemoteInterfaceInitialize interface as input to an IPnpCallbackRemoteInterfaceNotification::OnRemoteInterfaceArrival callback function.
old-location: wdf\iwdfremoteinterfaceinitialize.htm
tech.root: wdf
ms.assetid: 54954874-d67a-4e8b-b791-105e8018f8ca
ms.date: 02/26/2018
keywords: ["IWDFRemoteInterfaceInitialize interface"]
ms.keywords: IWDFRemoteInterfaceInitialize, IWDFRemoteInterfaceInitialize interface, IWDFRemoteInterfaceInitialize interface,described, UMDFIoTargetObjectRef_0536631b-c316-41e7-856b-94a3c991c318.xml, umdf.iwdfremoteinterfaceinitialize, wdf.iwdfremoteinterfaceinitialize, wudfddi/IWDFRemoteInterfaceInitialize
req.header: wudfddi.h
req.include-header: 
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFRemoteInterfaceInitialize
 - wudfddi/IWDFRemoteInterfaceInitialize
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFRemoteInterfaceInitialize
---

# IWDFRemoteInterfaceInitialize interface


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

UMDF-based drivers receive the <b>IWDFRemoteInterfaceInitialize</b> interface as input to an <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallbackremoteinterfacenotification-onremoteinterfacearrival">IPnpCallbackRemoteInterfaceNotification::OnRemoteInterfaceArrival</a> callback function.

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFRemoteInterfaceInitialize</b> interface inherits from the <a href="/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IWDFRemoteInterfaceInitialize</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>