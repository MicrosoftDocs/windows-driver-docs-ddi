---
UID: NN:prcomoem.IPrintOemUIMXDC
title: IPrintOemUIMXDC
author: windows-driver-content
description: This section describes the methods that are defined for the IPrintOemUIMXDC COM interface.
old-location: print\iprintoemuimxdc_interface.htm
old-project: print
ms.assetid: 4a70c0a7-9de7-48ed-a678-64832f078018
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: IPrintOemUIMXDC, IPrintOemUIMXDC interface [Print Devices], IPrintOemUIMXDC interface [Print Devices],described, prcomoem/IPrintOemUIMXDC, print.iprintoemuimxdc_interface, print_unidrv-pscript_ui_120354fc-1e37-41c9-b273-c28fde18079f.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	prcomoem.h
api_name:
-	IPrintOemUIMXDC
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUIMXDC interface


## -description


This section describes the methods that are defined for the IPrintOemUIMXDC COM interface.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintOemUIMXDC</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IPrintOemUIMXDC</b> also has these types of members:
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
<a href="https://msdn.microsoft.com/d725d917-08fb-4e11-824c-795e35782a06">AdjustDPI</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUIMXDC::AdjustDPI</code> method enables an XPS filter pipeline driver to use UnidrvUI.dll or PS5UI.dll to support configuration of image resolution.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/a698fcb9-1285-4201-9b49-e79dcda66043">AdjustImageableArea</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUIMXDC::AdjustImageableArea</code> method enables an XPS filter pipeline driver to use UnidrvUI.dll or PS5UI.dll to support configuration of the printable area, including orientation and direction of rotation.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/d9606c9b-4a47-4e83-ad8a-ef82e2c70de3">AdjustImageCompression</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUIMXDC::AdjustImageCompression</code> method allows an XPS filter pipeline driver to use UnidrvUI.dll or PS5UI.dll to support configuration of compression level for JPEG or PNG images.

</td>
</tr>
</table> 

