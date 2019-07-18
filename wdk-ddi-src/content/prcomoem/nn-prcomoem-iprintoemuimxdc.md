---
UID: NN:prcomoem.IPrintOemUIMXDC
title: IPrintOemUIMXDC (prcomoem.h)
description: This section describes the methods that are defined for the IPrintOemUIMXDC COM interface.
old-location: print\iprintoemuimxdc_interface.htm
tech.root: print
ms.assetid: 4a70c0a7-9de7-48ed-a678-64832f078018
ms.date: 04/20/2018
ms.keywords: IPrintOemUIMXDC, IPrintOemUIMXDC interface [Print Devices], IPrintOemUIMXDC interface [Print Devices],described, prcomoem/IPrintOemUIMXDC, print.iprintoemuimxdc_interface, print_unidrv-pscript_ui_120354fc-1e37-41c9-b273-c28fde18079f.xml
ms.topic: interface
f1_keywords:
 - "prcomoem/IPrintOemUIMXDC"
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
- IPrintOemUIMXDC
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUIMXDC interface


## -description


This section describes the methods that are defined for the IPrintOemUIMXDC COM interface.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintOemUIMXDC</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPrintOemUIMXDC</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrintOemUIMXDC</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemuimxdc-adjustdpi">AdjustDPI</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUIMXDC::AdjustDPI</code> method enables an XPS filter pipeline driver to use UnidrvUI.dll or PS5UI.dll to support configuration of image resolution.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemuimxdc-adjustimageablearea">AdjustImageableArea</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUIMXDC::AdjustImageableArea</code> method enables an XPS filter pipeline driver to use UnidrvUI.dll or PS5UI.dll to support configuration of the printable area, including orientation and direction of rotation.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemuimxdc-adjustimagecompression">AdjustImageCompression</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUIMXDC::AdjustImageCompression</code> method allows an XPS filter pipeline driver to use UnidrvUI.dll or PS5UI.dll to support configuration of compression level for JPEG or PNG images.

</td>
</tr>
</table> 

