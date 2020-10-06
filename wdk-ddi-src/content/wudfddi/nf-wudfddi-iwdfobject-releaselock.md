---
UID: NF:wudfddi.IWDFObject.ReleaseLock
title: IWDFObject::ReleaseLock (wudfddi.h)
description: The ReleaseLock method allows the framework to call methods of interfaces that are registered by the driver that the framework previously prevented from calling because the driver called the IWDFObject::AcquireLock method.
old-location: wdf\iwdfobject_releaselock.htm
tech.root: wdf
ms.assetid: 05771d81-d2e1-4787-a190-e7ef4d9ebcc9
ms.date: 02/26/2018
keywords: ["IWDFObject::ReleaseLock"]
ms.keywords: IWDFObject interface,ReleaseLock method, IWDFObject.ReleaseLock, IWDFObject::ReleaseLock, ReleaseLock, ReleaseLock method, ReleaseLock method,IWDFObject interface, UMDFBaseObjectRef_bdc7490f-170b-42bb-91af-435ee5dc3e5a.xml, umdf.iwdfobject_releaselock, wdf.iwdfobject_releaselock, wudfddi/IWDFObject::ReleaseLock
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFObject::ReleaseLock
 - wudfddi/IWDFObject::ReleaseLock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFObject.ReleaseLock
---

# IWDFObject::ReleaseLock


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>ReleaseLock</b> method allows the framework to call methods of interfaces that are registered by the driver that the framework previously prevented from calling because the driver called the <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfobject-acquirelock">IWDFObject::AcquireLock</a> method.

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfobject">IWDFObject</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfobject-acquirelock">IWDFObject::AcquireLock</a>