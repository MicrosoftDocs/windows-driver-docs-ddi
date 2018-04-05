---
UID: NN:prcomoem.IPrintCoreUI2
title: IPrintCoreUI2
author: windows-driver-content
description: This section describes the methods defined for the IPrintCoreUI2 COM Interface.
old-location: print\iprintcoreui2_interface.htm
old-project: print
ms.assetid: e2d2e486-d69d-4a6d-aaab-a7b8806665b4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintCoreUI2, IPrintCoreUI2 interface [Print Devices], IPrintCoreUI2 interface [Print Devices], described, prcomoem/IPrintCoreUI2, print.iprintcoreui2_interface, print_unidrv-pscript_ui_e96a2262-fab6-4128-b312-90fde72006e0.xml
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
-	IPrintCoreUI2
product:
- Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintCoreUI2 interface


## -description


This section describes the methods defined for the <a href="https://msdn.microsoft.com/3c9df0ac-d823-4c27-bd34-85765f48b972">IPrintCoreUI2 COM Interface</a>.

This interface inherits from the <a href="https://msdn.microsoft.com/ed11789f-750d-4f29-b5e0-ab299a1388db">IPrintOemDriverUI COM Interface</a>. The methods in this interface are provided by the Windows XP Pscript5 driver, for the sole use of its user interface plug-ins. Method prototypes appear in prcomoem.h.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintCoreUI2</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IPrintCoreUI2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrintCoreUI2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548556">DrvGetDriverSetting</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreUI2::DrvGetDriverSetting</code> method is provided by the Windows XP Pscript5 driver so that Pscript5 user interface plug-ins can obtain the current status of printer features and other internal information.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548641">DrvUpdateUISetting</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreUI2::DrvUpdateUISetting</code> method is provided by the Windows XP Pscript5 driver so that Pscript5 user interface plug-ins can notify the driver of a modified user interface option.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548652">DrvUpgradeRegistrySetting</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreUI2::DrvUpgradeRegistrySetting</code> method is provided by the Windows XP Pscript5 driver so that Pscript5 user interface plug-ins can update device settings stored in the registry.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/815a20f4-9bd7-4f8d-8444-545097d1c4b3">EnumConstrainedOptions</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreUI2::EnumConstrainedOptions</code> method determines which options of a feature are constrained.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/e5c16b6d-555d-4360-b781-4d22be81ab56">EnumFeatures</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreUI2::EnumFeatures</code> method enumerates a printer's available features.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/9ae20927-6ef4-4566-939c-967ce1d99874">EnumOptions</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreUI2::EnumOptions</code> method enumerates the available options of a specific feature.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/6f3d16a9-bac7-44da-9d16-0f737d12d952">GetFeatureAttribute</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreUI2::GetFeatureAttribute</code> method retrieves the feature attribute list or the value of a specific feature attribute.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/fa5555df-4ada-40f3-9878-e6ba3dac2345">GetGlobalAttribute</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreUI2::GetGlobalAttribute</code> method retrieves the global attribute list or the value of a specific global attribute.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/cf5420fb-3414-47a7-a53d-3d109589b64d">GetOptionAttribute</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreUI2::GetOptionAttribute</code> method retrieves the option attribute list or the value of a specific option attribute.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451244">GetOptions</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreUI2::GetOptions</code> method retrieves the driver's current feature settings in the format of a list of feature/option keyword pairs.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/0136df19-9491-47ea-9a8f-c9a932646686">QuerySimulationSupport</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreUI2::QuerySimulationSupport</code> method retrieves a spooler simulation capability structure, which indicates the kinds of simulation the spooler supports.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/b608e331-6b13-4b27-8bb1-00a7c2fef281">SetOptions</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreUI2::SetOptions</code> method sets the driver's feature settings.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/3161620e-6155-4587-b978-599d526d792c">WhyConstrained</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreUI2::WhyConstrained</code> method determines why the specified feature/option selection is constrained.

</td>
</tr>
</table> 

