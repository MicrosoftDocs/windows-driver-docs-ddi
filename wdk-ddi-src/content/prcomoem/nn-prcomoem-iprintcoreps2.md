---
UID: NN:prcomoem.IPrintCorePS2
title: IPrintCorePS2 (prcomoem.h)
description: This section describes the methods defined for the IPrintCorePS2 COM Interface. Method prototypes are defined in prcomoem.h.
old-location: print\iprintcoreps2_interface.htm
tech.root: print
ms.assetid: bf7e15df-49ba-4850-acf6-dab5dc137f48
ms.date: 04/20/2018
ms.keywords: IPrintCorePS2, IPrintCorePS2 interface [Print Devices], IPrintCorePS2 interface [Print Devices],described, prcomoem/IPrintCorePS2, print.iprintcoreps2_interface, print_unidrv-pscript_rendering_ee16e348-6dec-4820-ab6c-d41adecf8c74.xml
ms.topic: interface
f1_keywords:
 - "prcomoem/IPrintCorePS2"
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
- IPrintCorePS2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintCorePS2 interface


## -description


This section describes the methods defined for the <a href="https://docs.microsoft.com/windows-hardware/drivers/print/iprintcoreps2-com-interface">IPrintCorePS2 COM Interface</a>. Method prototypes are defined in prcomoem.h.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintCorePS2</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPrintCorePS2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrintCorePS2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printoem/nc-printoem-pfn_drvwritespoolbuf">DrvWriteSpoolBuf</a>
</td>
<td align="left" width="63%">
The <code>IPrintCorePS2::DrvWriteSpoolBuf</code> method is provided by the Pscript5 driver so that a <a href="https://docs.microsoft.com/windows-hardware/drivers/print/rendering-plug-ins">rendering plug-in</a> can send printer data to the spooler.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcoreps2-enumfeatures">EnumFeatures</a>
</td>
<td align="left" width="63%">
The <code>IPrintCorePS2::EnumFeatures</code> method enumerates a printer's available features.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcoreps2-enumoptions">EnumOptions</a>
</td>
<td align="left" width="63%">
The <code>IPrintCorePS2::EnumOptions</code> method enumerates the available options of a specific feature.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcoreps2-getfeatureattribute">GetFeatureAttribute</a>
</td>
<td align="left" width="63%">
The <code>IPrintCorePS2::GetFeatureAttribute</code> method retrieves the feature attribute list or the value of a specific feature attribute.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcoreps2-getglobalattribute">GetGlobalAttribute</a>
</td>
<td align="left" width="63%">
The <code>IPrintCorePS2::GetGlobalAttribute</code> method retrieves the global attribute list or the value of a specific global attribute.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcoreps2-getoptionattribute">GetOptionAttribute</a>
</td>
<td align="left" width="63%">
The <code>IPrintCorePS2::GetOptionAttribute</code> method retrieves the option attribute list or the value of a specific option attribute.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintschemacapabilities-getoptions">GetOptions</a>
</td>
<td align="left" width="63%">
The <code>IPrintCorePS2::GetOptions</code> method retrieves the driver's current feature settings in the format of a list of feature/option keyword pairs.

</td>
</tr>
</table> 

