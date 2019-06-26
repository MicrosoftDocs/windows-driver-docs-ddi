---
UID: NN:prcomoem.IPrintCoreHelperPS
title: IPrintCoreHelperPS (prcomoem.h)
description: This section describes the methods that are defined for the IPrintCoreHelperPS COM interface.
old-location: print\iprintcorehelperps_interface.htm
tech.root: print
ms.assetid: 2be594f1-1eb1-42e0-a345-ee7edf4d96dd
ms.date: 04/20/2018
ms.keywords: IPrintCoreHelperPS, IPrintCoreHelperPS interface [Print Devices], IPrintCoreHelperPS interface [Print Devices],described, prcomoem/IPrintCoreHelperPS, print.iprintcorehelperps_interface, print_unidrv-pscript_allplugins_793ff9db-3ae7-4c10-a84e-bc974a72529e.xml
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- prcomoem.h
api_name:
- IPrintCoreHelperPS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintCoreHelperPS interface


## -description


This section describes the methods that are defined for the <b>IPrintCoreHelperPS</b> COM interface. 


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintCoreHelperPS</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPrintCoreHelperPS</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrintCoreHelperPS</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcorehelperps-createinstanceofmsxmlobject">CreateInstanceOfMSXMLObject</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelperPS::CreateInstanceOfMSXMLObject</b> method creates an instance of an MSXML object. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcorehelperps-enumconstrainedoptions">EnumConstrainedOptions</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelperPS::EnumConstrainedOptions</b> method provides a list of all of the options that are constrained in a particular feature, based on current settings.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcorehelperps-enumfeatures">EnumFeatures</a>
</td>
<td align="left" width="63%">
The<b> IPrintCoreHelperPS::EnumFeatures</b> method gets a list of all available features, including synthesized and core driver-implement features.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcorehelperps-enumoptions">EnumOptions</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelperPS::EnumOptions</b> method gets a list of available options for the given feature. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcorehelperps-getfeatureattribute">GetFeatureAttribute</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelperPS::GetFeatureAttribute</b> method retrieves the feature attribute list or the value of a specific feature attribute.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcorehelperps-getfontsubstitution">GetFontSubstitution</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelperPS::GetFontSubstitution</b> method indicates which device font, if any, is used as a substitution font for a specified TrueType font.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcorehelperps-getglobalattribute">GetGlobalAttribute</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelperPS::GetGlobalAttribute</b> method retrieves the global attribute list or the value of a specific global attribute.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintschemafeature-getoption">GetOption</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelperPS::GetOption</b> method gets a specified option for a given feature.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcorehelperps-getoptionattribute">GetOptionAttribute</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelperPS::GetOptionAttribute</b> method retrieves the option attribute list or the value of a specific option attribute.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcorehelperps-setfontsubstitution">SetFontSubstitution</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelperPS::SetFontSubstitution</b> method specifies the device font to print in place of a given TrueType font. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcorehelperps-setoptions">SetOptions</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelperPS::SetOptions</b> method sets multiple feature-option pairs at the same time.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcorehelperps-whyconstrained">WhyConstrained</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelperPS::WhyConstrained</b> method provides a list of options that constrain the specified feature-option pair in the current configuration.

</td>
</tr>
</table> 

