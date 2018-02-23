---
UID: NN:prcomoem.IPrintCoreHelper
title: IPrintCoreHelper
author: windows-driver-content
description: This section describes the methods that are defined for the IPrintCoreHelper COM interface.
old-location: print\iprintcorehelper_interface.htm
old-project: print
ms.assetid: db13410f-e4cb-4077-bb4b-7963e97b435c
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: print.iprintcorehelper_interface, IPrintCoreHelper interface [Print Devices], IPrintCoreHelper interface [Print Devices], described, IPrintCoreHelper, prcomoem/IPrintCoreHelper, print_unidrv-pscript_allplugins_9609acef-24e8-4802-9c70-196fef2b011f.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	prcomoem.h
apiname:
-	IPrintCoreHelper
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintCoreHelper interface


## -description


This section describes the methods that are defined for the <b>IPrintCoreHelper</b> COM interface.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintCoreHelper</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IPrintCoreHelper</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrintCoreHelper</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/d4b91262-f349-4824-bab0-5e3725a81cb3">CreateInstanceOfMSXMLObject</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelper::CreateInstanceOfMSXMLObject</b> method creates an instance of an MSXML 6.0 object by using the correct MSXML DLL. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/16a9417c-6d47-49fc-9ba9-e2b522255942">EnumConstrainedOptions</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelper::EnumConstrainedOptions</b> method provides a list of all of the options that are constrained in a particular feature, based on current settings.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/21eddcfe-fe86-4135-a91c-42ec6e8e428a">EnumFeatures</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelper::EnumFeatures</b> method gets a list of all available features, including synthesized and core driver-implement features.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/2e46e8cd-b5e5-4116-b42c-b7adcee9d520">EnumOptions</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelper::EnumOptions</b> method gets a list of available options for the given feature. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/09fc48eb-b124-45b1-a796-71d9a6961e07">GetFontSubstitution</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelper::GetFontSubstitution</b> method indicates which device font, if any, is used as a substitution font for a specified TrueType font.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451273">GetOption</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelper::GetOption</b> method gets a specified option for a given feature.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/2d0278b0-0011-4946-a095-5fef77a8b194">SetFontSubstitution</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelper::SetFontSubstitution</b> method specifies the device font to print in place of a given TrueType font. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/0441558c-db3d-46d1-a251-a32e98098e9e">SetOptions</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelper::SetOptions</b> method sets multiple feature-option pairs at the same time.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/de3fdbd4-9647-4369-9c23-4779aa768b1b">WhyConstrained</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelper::WhyConstrained</b> method provides a list of options that are constraining the specified feature-option pair in the current configuration.

</td>
</tr>
</table> 

