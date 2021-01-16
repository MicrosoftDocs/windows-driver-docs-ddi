---
UID: NF:wudfddi.IWDFWorkItem.GetParentObject
title: IWDFWorkItem::GetParentObject (wudfddi.h)
description: The GetParentObject method returns the parent framework object of this interface's work item.
old-location: wdf\iwdfworkitem_getparentobject.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["IWDFWorkItem::GetParentObject"]
ms.keywords: GetParentObject, GetParentObject method, GetParentObject method,IWDFWorkItem interface, IWDFWorkItem interface,GetParentObject method, IWDFWorkItem.GetParentObject, IWDFWorkItem::GetParentObject, umdf.iwdfworkitem_getparentobject, wdf.iwdfworkitem_getparentobject, wudfddi/IWDFWorkItem::GetParentObject
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
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
 - IWDFWorkItem::GetParentObject
 - wudfddi/IWDFWorkItem::GetParentObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFWorkItem::GetParentObject
---

# IWDFWorkItem::GetParentObject


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetParentObject</b> method returns the parent framework object of this interface's  work item.

## -returns

A pointer to the parent object interface.

## -remarks

For more information, see <a href="/windows-hardware/drivers/wdf/using-workitems">Using Work Items</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfworkitem">IWDFWorkItem</a>

