---
UID: NN:wudfddi.IWDFIoTargetStateManagement
title: IWDFIoTargetStateManagement (wudfddi.h)
description: The IWDFIoTargetStateManagement interface exposes methods that manage and monitor the state of an I/O target object.
old-location: wdf\iwdfiotargetstatemanagement.htm
tech.root: wdf
ms.assetid: 6870b6fa-1a90-4a7a-935a-4ce8eda940a1
ms.date: 02/26/2018
keywords: ["IWDFIoTargetStateManagement interface"]
ms.keywords: IWDFIoTargetStateManagement, IWDFIoTargetStateManagement interface, IWDFIoTargetStateManagement interface,described, UMDFIoTargetObjectRef_667496e9-fa1f-4c90-911d-d456ffc3b59e.xml, umdf.iwdfiotargetstatemanagement, wdf.iwdfiotargetstatemanagement, wudfddi/IWDFIoTargetStateManagement
req.header: wudfddi.h
req.include-header: 
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFIoTargetStateManagement
 - wudfddi/IWDFIoTargetStateManagement
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFIoTargetStateManagement
---

# IWDFIoTargetStateManagement interface


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IWDFIoTargetStateManagement</b> interface exposes methods that manage and monitor the state of an I/O target object.

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFIoTargetStateManagement</b> interface inherits from the <a href="https://docs.microsoft.com/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IWDFIoTargetStateManagement</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -remarks

Drivers obtain the <b>IWDFIoTargetStateManagement</b> interface by calling <b>IWDFIoTarget::QueryInterface</b>, <b>IWDFUsbTargetPipe::QueryInterface</b>, or <b>IWDFUsbTargetPipe2::QueryInterface</b>.

