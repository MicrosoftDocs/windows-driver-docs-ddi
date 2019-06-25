---
UID: NN:prcomoem.IPrintCoreUI2
title: IPrintCoreUI2 (prcomoem.h)
description: This section describes the methods defined for the IPrintCoreUI2 COM Interface.
old-location: print\iprintcoreui2_interface.htm
tech.root: print
ms.assetid: e2d2e486-d69d-4a6d-aaab-a7b8806665b4
ms.date: 04/20/2018
ms.keywords: IPrintCoreUI2, IPrintCoreUI2 interface [Print Devices], IPrintCoreUI2 interface [Print Devices],described, prcomoem/IPrintCoreUI2, print.iprintcoreui2_interface, print_unidrv-pscript_ui_e96a2262-fab6-4128-b312-90fde72006e0.xml
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
- IPrintCoreUI2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintCoreUI2 interface


## -description


This section describes the methods defined for the <a href="https://docs.microsoft.com/windows-hardware/drivers/print/iprintcoreui2-com-interface">IPrintCoreUI2 COM Interface</a>.

This interface inherits from the <a href="https://docs.microsoft.com/windows-hardware/drivers/print/iprintoemdriverui-com-interface">IPrintOemDriverUI COM Interface</a>. The methods in this interface are provided by the Windows XP Pscript5 driver, for the sole use of its user interface plug-ins. Method prototypes appear in prcomoem.h.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintCoreUI2</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPrintCoreUI2</b> also has these types of members:
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
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printoem/nc-printoem-pfn_drvgetdriversetting">DrvGetDriverSetting</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreUI2::DrvGetDriverSetting</code> method is provided by the Windows XP Pscript5 driver so that Pscript5 user interface plug-ins can obtain the current status of printer features and other internal information.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printoem/nc-printoem-pfn_drvupdateuisetting">DrvUpdateUISetting</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreUI2::DrvUpdateUISetting</code> method is provided by the Windows XP Pscript5 driver so that Pscript5 user interface plug-ins can notify the driver of a modified user interface option.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printoem/nc-printoem-pfn_drvupgraderegistrysetting">DrvUpgradeRegistrySetting</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreUI2::DrvUpgradeRegistrySetting</code> method is provided by the Windows XP Pscript5 driver so that Pscript5 user interface plug-ins can update device settings stored in the registry.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcoreui2-enumconstrainedoptions">EnumConstrainedOptions</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreUI2::EnumConstrainedOptions</code> method determines which options of a feature are constrained.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcoreui2-enumfeatures">EnumFeatures</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreUI2::EnumFeatures</code> method enumerates a printer's available features.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcoreui2-enumoptions">EnumOptions</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreUI2::EnumOptions</code> method enumerates the available options of a specific feature.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcoreui2-getfeatureattribute">GetFeatureAttribute</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreUI2::GetFeatureAttribute</code> method retrieves the feature attribute list or the value of a specific feature attribute.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcoreui2-getglobalattribute">GetGlobalAttribute</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreUI2::GetGlobalAttribute</code> method retrieves the global attribute list or the value of a specific global attribute.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcoreui2-getoptionattribute">GetOptionAttribute</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreUI2::GetOptionAttribute</code> method retrieves the option attribute list or the value of a specific option attribute.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintschemacapabilities-getoptions">GetOptions</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreUI2::GetOptions</code> method retrieves the driver's current feature settings in the format of a list of feature/option keyword pairs.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcoreui2-querysimulationsupport">QuerySimulationSupport</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreUI2::QuerySimulationSupport</code> method retrieves a spooler simulation capability structure, which indicates the kinds of simulation the spooler supports.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcoreui2-setoptions">SetOptions</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreUI2::SetOptions</code> method sets the driver's feature settings.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcoreui2-whyconstrained">WhyConstrained</a>
</td>
<td align="left" width="63%">
The <code>IPrintCoreUI2::WhyConstrained</code> method determines why the specified feature/option selection is constrained.

</td>
</tr>
</table> 

