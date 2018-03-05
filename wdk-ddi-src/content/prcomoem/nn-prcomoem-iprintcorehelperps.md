---
UID: NN:prcomoem.IPrintCoreHelperPS
title: IPrintCoreHelperPS
author: windows-driver-content
description: This section describes the methods that are defined for the IPrintCoreHelperPS COM interface.
old-location: print\iprintcorehelperps_interface.htm
old-project: print
ms.assetid: 2be594f1-1eb1-42e0-a345-ee7edf4d96dd
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintCoreHelperPS, IPrintCoreHelperPS interface [Print Devices], IPrintCoreHelperPS interface [Print Devices], described, prcomoem/IPrintCoreHelperPS, print.iprintcorehelperps_interface, print_unidrv-pscript_allplugins_793ff9db-3ae7-4c10-a84e-bc974a72529e.xml
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
req.lib: prcomoem.h
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
-	IPrintCoreHelperPS
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintCoreHelperPS interface


## -description


This section describes the methods that are defined for the <b>IPrintCoreHelperPS</b> COM interface. 


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintCoreHelperPS</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IPrintCoreHelperPS</b> also has these types of members:
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
<a href="https://msdn.microsoft.com/017f6e00-694b-4ada-86be-cf2be047fa88">CreateInstanceOfMSXMLObject</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelperPS::CreateInstanceOfMSXMLObject</b> method creates an instance of an MSXML object. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/106119cd-80ed-4d26-a7c1-fda5a49b080c">EnumConstrainedOptions</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelperPS::EnumConstrainedOptions</b> method provides a list of all of the options that are constrained in a particular feature, based on current settings.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/c67c15a4-3dbf-4317-b6d5-e52f426e7619">EnumFeatures</a>
</td>
<td align="left" width="63%">
The<b> IPrintCoreHelperPS::EnumFeatures</b> method gets a list of all available features, including synthesized and core driver-implement features.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/bd23f4e6-7a99-4347-ae29-a1e832db2e03">EnumOptions</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelperPS::EnumOptions</b> method gets a list of available options for the given feature. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/bf5d9081-20c8-43da-a71f-f089c2885b49">GetFeatureAttribute</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelperPS::GetFeatureAttribute</b> method retrieves the feature attribute list or the value of a specific feature attribute.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/d5f71935-8371-413d-a602-a9a4a9e976c3">GetFontSubstitution</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelperPS::GetFontSubstitution</b> method indicates which device font, if any, is used as a substitution font for a specified TrueType font.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/4243ac31-83a7-47b5-8406-9d9537fbeb11">GetGlobalAttribute</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelperPS::GetGlobalAttribute</b> method retrieves the global attribute list or the value of a specific global attribute.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451273">GetOption</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelperPS::GetOption</b> method gets a specified option for a given feature.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/66e794e6-ded0-41b1-b52b-d886bb58a4ff">GetOptionAttribute</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelperPS::GetOptionAttribute</b> method retrieves the option attribute list or the value of a specific option attribute.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/2f3b47db-8e4e-4a76-a08a-acd2b903247e">SetFontSubstitution</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelperPS::SetFontSubstitution</b> method specifies the device font to print in place of a given TrueType font. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/ba80f0f5-ecea-41d7-8ddd-58b417e1fbe7">SetOptions</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelperPS::SetOptions</b> method sets multiple feature-option pairs at the same time.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/23953142-9246-41cf-91b4-75b1a3f6128e">WhyConstrained</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelperPS::WhyConstrained</b> method provides a list of options that constrain the specified feature-option pair in the current configuration.

</td>
</tr>
</table> 

