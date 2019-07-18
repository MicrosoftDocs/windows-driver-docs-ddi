---
UID: NN:prcomoem.IPrintCoreHelperUni
title: IPrintCoreHelperUni (prcomoem.h)
description: This section describes the methods that are defined for the IPrintCoreHelperUni COM interface.
old-location: print\iprintcorehelperuni_interface.htm
tech.root: print
ms.assetid: e581d190-8185-45c1-80c7-ff8eb305360e
ms.date: 04/20/2018
ms.keywords: IPrintCoreHelperUni, IPrintCoreHelperUni interface [Print Devices], IPrintCoreHelperUni interface [Print Devices],described, prcomoem/IPrintCoreHelperUni, print.iprintcorehelperuni_interface, print_unidrv-pscript_allplugins_ca505d1f-1b52-4a61-a2d8-d8fea10cda76.xml
ms.topic: interface
f1_keywords:
 - "prcomoem/IPrintCoreHelperUni"
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
- IPrintCoreHelperUni
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintCoreHelperUni interface


## -description


This section describes the methods that are defined for the <code>IPrintCoreHelperUni</code> COM interface.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintCoreHelperUni</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPrintCoreHelperUni</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrintCoreHelperUni</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcorehelperuni-createdefaultgdlsnapshot">CreateDefaultGDLSnapshot</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreHelperUni::CreateDefaultGDLSnapshot</code> method gets a GDL snapshot based on the driver default configuration.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcorehelperuni-creategdlsnapshot">CreateGDLSnapshot</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreHelperUni::CreateGDLSnapshot</code> method creates a GDL snapshot of the driver configuration file based on the current configuration. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcorehelperuni-createinstanceofmsxmlobject">CreateInstanceOfMSXMLObject</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreHelperUni::CreateInstanceOfMSXMLObject</code> method creates an instance of an MSXML object. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcorehelperuni-enumconstrainedoptions">EnumConstrainedOptions</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreHelperUni::EnumConstrainedOptions</code> method provides a list of all of the options that are constrained in a particular feature, based on current settings.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcorehelperuni-enumfeatures">EnumFeatures</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreHelperUni::EnumFeatures</code> method gets a list of all available features, including synthesized and core driver-implement features.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcorehelperuni-enumoptions">EnumOptions</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreHelperUni::EnumOptions</code> method gets a list of available options for the given feature. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcorehelperuni-getfontsubstitution">GetFontSubstitution</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreHelperUni::GetFontSubstitution</code> method indicates which device font, if any, is used as a substitution font for a specified TrueType font.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintschemafeature-getoption">GetOption</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreHelperUni::GetOption</code> method gets a specified option for a given feature.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcorehelperuni-setfontsubstitution">SetFontSubstitution</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreHelperUni::SetFontSubstitution</code> method specifies the device font to print in place of a given TrueType font. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcorehelperuni-setoptions">SetOptions</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreHelperUni::SetOptions</code> method sets multiple feature-option pairs at the same time.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcorehelperuni-whyconstrained">WhyConstrained</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreHelperUni::WhyConstrained</code> method provides a list of options that constrain the specified feature-option pair in the current configuration. 

</td>
</tr>
</table> 

