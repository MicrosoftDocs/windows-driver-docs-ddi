---
UID: NN:wudfddi.IWDFNamedPropertyStore
title: IWDFNamedPropertyStore (wudfddi.h)
description: The IWDFNamedPropertyStore interface exposes a property-store object.
old-location: wdf\iwdfnamedpropertystore.htm
tech.root: wdf
ms.assetid: f31a88c1-468f-4756-a5fa-b4aa0b8fe51d
ms.date: 02/26/2018
ms.keywords: IWDFNamedPropertyStore, IWDFNamedPropertyStore interface, IWDFNamedPropertyStore interface,described, UMDFPropertyStoreObjectRef_139eb19f-8bb7-42ba-ab86-44f5f35e0faf.xml, umdf.iwdfnamedpropertystore, wdf.iwdfnamedpropertystore, wudfddi/IWDFNamedPropertyStore
ms.topic: interface
f1_keywords:
 - "wudfddi/IWDFNamedPropertyStore"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFNamedPropertyStore
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFNamedPropertyStore interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IWDFNamedPropertyStore</b> interface exposes a property-store object.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFNamedPropertyStore</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IWDFNamedPropertyStore</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWDFNamedPropertyStore</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfnamedpropertystore-getnameat">IWDFNamedPropertyStore::GetNameAt</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfnamedpropertystore-getnameat">GetNameAt</a> method retrieves the name of a property.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfnamedpropertystore-getnamecount">IWDFNamedPropertyStore::GetNameCount</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfnamedpropertystore-getnamecount">GetNameCount</a> method retrieves the number of properties in a property store.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfnamedpropertystore-getnamedvalue">IWDFNamedPropertyStore::GetNamedValue</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfnamedpropertystore-getnamedvalue">GetNamedValue</a> method retrieves the value of a property.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfnamedpropertystore-setnamedvalue">IWDFNamedPropertyStore::SetNamedValue</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfnamedpropertystore-setnamedvalue">SetNamedValue</a> method sets the value of a property.

</td>
</tr>
</table> 

