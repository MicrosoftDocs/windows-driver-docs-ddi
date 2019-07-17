---
UID: NN:prcomoem.IPrintOemUI2
title: IPrintOemUI2 (prcomoem.h)
description: This section describes the methods defined for the IPrintOemUI2 COM interface.
old-location: print\iprintoemui2_interface.htm
tech.root: print
ms.assetid: 9b7afb56-7abb-4f20-b69d-12a28d7e3617
ms.date: 04/20/2018
ms.keywords: IPrintOemUI2, IPrintOemUI2 interface [Print Devices], IPrintOemUI2 interface [Print Devices],described, prcomoem/IPrintOemUI2, print.iprintoemui2_interface, print_unidrv-pscript_ui_838f6394-df99-4045-9059-6ff480212733.xml
ms.topic: interface
f1_keywords:
 - "prcomoem/IPrintOemUI2"
req.header: prcomoem.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- prcomoem.h
api_name:
- IPrintOemUI2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUI2 interface


## -description


This section describes the methods defined for the <b>IPrintOemUI2</b> COM interface.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintOemUI2</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPrintOemUI2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrintOemUI2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemui2-documentevent">DocumentEvent</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUI2::DocumentEvent</code> method allows a UI plug-in to replace the core driver UI module's default implementation of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winddiui/nf-winddiui-drvdocumentevent">DrvDocumentEvent</a> DDI.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemui2-hidestandardui">HideStandardUI</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUI2::HideStandardUI</code> method allows a user interface plug-in to specify whether the standard property sheets should be displayed or hidden. Beginning with Microsoft Windows XP, this method can be implemented by a Pscript5 user interface plug-in. Beginning with Windows Vista, this method can be implemented by a Unidrv user interface plug-in.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemui2-queryjobattributes">QueryJobAttributes</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUI2::QueryJobAttributes</code> method allows a UI plug-in to postprocess the core driver's results after a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winddiui/nf-winddiui-drvqueryjobattributes">DrvQueryJobAttributes</a> DDI. The plug-in can choose to overwrite the values that the core driver placed in the <i>lpAttributeInfo</i> output buffer.

</td>
</tr>
</table> 

