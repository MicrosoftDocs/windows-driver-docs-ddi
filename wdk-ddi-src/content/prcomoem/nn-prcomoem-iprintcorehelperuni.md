---
UID: NN:prcomoem.IPrintCoreHelperUni
title: IPrintCoreHelperUni
author: windows-driver-content
description: This section describes the methods that are defined for the IPrintCoreHelperUni COM interface.
old-location: print\iprintcorehelperuni_interface.htm
old-project: print
ms.assetid: e581d190-8185-45c1-80c7-ff8eb305360e
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: IPrintCoreHelperUni, IPrintCoreHelperUni interface [Print Devices], IPrintCoreHelperUni interface [Print Devices],described, prcomoem/IPrintCoreHelperUni, print.iprintcorehelperuni_interface, print_unidrv-pscript_allplugins_ca505d1f-1b52-4a61-a2d8-d8fea10cda76.xml
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	prcomoem.h
api_name:
-	IPrintCoreHelperUni
product: Windows
targetos: Windows
req.typenames: 
---

# IPrintCoreHelperUni interface


## -description


This section describes the methods that are defined for the <code>IPrintCoreHelperUni</code> COM interface.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintCoreHelperUni</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IPrintCoreHelperUni</b> also has these types of members:
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
<a href="https://msdn.microsoft.com/987c3721-d8a8-4aac-8f42-6eac9b5ccdc5">CreateDefaultGDLSnapshot</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreHelperUni::CreateDefaultGDLSnapshot</code> method gets a GDL snapshot based on the driver default configuration.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/3dd9c7f9-27d4-45d2-8692-4270818c1823">CreateGDLSnapshot</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreHelperUni::CreateGDLSnapshot</code> method creates a GDL snapshot of the driver configuration file based on the current configuration. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/801ad433-4d52-4947-93f5-a11521a4df18">CreateInstanceOfMSXMLObject</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreHelperUni::CreateInstanceOfMSXMLObject</code> method creates an instance of an MSXML object. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/362d858a-5087-4cd2-8778-e6564297bc8f">EnumConstrainedOptions</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreHelperUni::EnumConstrainedOptions</code> method provides a list of all of the options that are constrained in a particular feature, based on current settings.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/ed21e52b-13a6-4a89-8bbc-9cbf72e3d9fd">EnumFeatures</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreHelperUni::EnumFeatures</code> method gets a list of all available features, including synthesized and core driver-implement features.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/07ed6417-1cdc-4a56-88c3-c2171c54e77c">EnumOptions</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreHelperUni::EnumOptions</code> method gets a list of available options for the given feature. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/f11b3b85-d01b-4133-9279-bff0001e04f9">GetFontSubstitution</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreHelperUni::GetFontSubstitution</code> method indicates which device font, if any, is used as a substitution font for a specified TrueType font.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451273">GetOption</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreHelperUni::GetOption</code> method gets a specified option for a given feature.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/73afb4e9-23c7-473c-937f-045bf5e332f7">SetFontSubstitution</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreHelperUni::SetFontSubstitution</code> method specifies the device font to print in place of a given TrueType font. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/f9dd7b32-7a87-427e-9efe-861301249add">SetOptions</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreHelperUni::SetOptions</code> method sets multiple feature-option pairs at the same time.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/99cd35f3-ebae-4ef2-b6fa-96853b3639ee">WhyConstrained</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreHelperUni::WhyConstrained</code> method provides a list of options that constrain the specified feature-option pair in the current configuration. 

</td>
</tr>
</table> 

