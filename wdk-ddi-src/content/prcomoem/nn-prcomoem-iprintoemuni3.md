---
UID: NN:prcomoem.IPrintOemUni3
title: IPrintOemUni3 (prcomoem.h)
description: This section describes the methods defined for the IPrintOemUni3 COM interface.
old-location: print\iprintoemuni3_interface.htm
tech.root: print
ms.assetid: cf5705fb-8420-4eec-99d4-d56f192da581
ms.date: 04/20/2018
ms.keywords: IPrintOemUni3, IPrintOemUni3 interface [Print Devices], IPrintOemUni3 interface [Print Devices],described, prcomoem/IPrintOemUni3, print.iprintoemuni3_interface, print_unidrv-pscript_rendering_631f975d-1d52-4db8-8e90-71cdb99f4ef1.xml
ms.topic: interface
f1_keywords:
 - "prcomoem/IPrintOemUni3"
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
- IPrintOemUni3
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUni3 interface


## -description


This section describes the methods defined for the <b>IPrintOemUni3</b> COM interface.

The <b>IPrintOemUni3</b> COM interface includes its own methods as well as those that belong to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nn-prcomoem-iprintoemuni">IPrintOemUni</a> COM interface and the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nn-prcomoem-iprintoemuni2">IPrintOemUni2</a> COM interface.

The <b>IPrintOemUni3</b> COM interface is available in Windows Vista and later.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintOemUni3</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPrintOemUni3</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrintOemUni3</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemuni3-downloadpattern">DownloadPattern</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni3::DownloadPattern</code> method downloads a pattern to a printer.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemuni3-getimplementedmethod">GetImplementedMethod</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni3::GetImplementedMethod</code> method is used by Unidrv to determine which <b>IPrintOemUni</b> interface methods a rendering plug-in has implemented.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemuni3-getpdevadjustment">GetPDEVAdjustment</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni3::GetPDEVAdjustment</code> method enables a plug-in to override specific <a href="https://docs.microsoft.com/windows-hardware/drivers/">PDEV</a> settings.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemuni3-setbandsize">SetBandSize</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni3::SetBandSize</code> method can be used with Unidrv-supported printers to specify the desired band size on the printed output.

</td>
</tr>
</table> 

