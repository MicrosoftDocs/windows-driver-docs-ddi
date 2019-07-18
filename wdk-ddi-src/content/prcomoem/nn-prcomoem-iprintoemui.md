---
UID: NN:prcomoem.IPrintOemUI
title: IPrintOemUI (prcomoem.h)
description: This section describes the methods defined for the IPrintOemUI COM interface.
old-location: print\iprintoemui_interface.htm
tech.root: print
ms.assetid: 0ef635dd-9598-4356-94fc-7e5237df9bd9
ms.date: 04/20/2018
ms.keywords: IPrintOemUI, IPrintOemUI interface [Print Devices], IPrintOemUI interface [Print Devices],described, prcomoem/IPrintOemUI, print.iprintoemui_interface, print_unidrv-pscript_ui_d2e42772-2604-4ef1-a667-70139ac8a62a.xml
ms.topic: interface
f1_keywords:
 - "prcomoem/IPrintOemUI"
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
- IPrintOemUI
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUI interface


## -description


This section describes the methods defined for the <b>IPrintOemUI</b> COM interface.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintOemUI</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPrintOemUI</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrintOemUI</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemui-commonuiprop">CommonUIProp</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUI::CommonUIProp</code> method allows a user interface plug-in to modify an existing printer property sheet page.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemui-devicecapabilities">DeviceCapabilities</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUI::DeviceCapabilities</code> method enables a user interface plug-in to specify customized device capabilities.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemui-devicepropertysheets">DevicePropertySheets</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUI::DevicePropertySheets</code> method allows a user interface plug-in to append a new page to a printer device's printer property sheet.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemui-devmode">DevMode</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUI::DevMode</code> method, provided by user interface plug-ins, performs operations on the plug-in's private DEVMODEW members.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemui-documentpropertysheets">DocumentPropertySheets</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUI::DocumentPropertySheets</code> method allows a user interface plug-in to append a new page to a printer device's document property sheet.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemui-driverevent">DriverEvent</a>
</td>
<td align="left" width="63%">
The printer driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winddiui/nf-winddiui-drvdriverevent">DrvDriverEvent</a> function calls a user interface plug-in's <code>IPrintOemUI::DriverEvent</code> method for additional processing of printer driver events.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemui-fontinstallerdlgproc">FontInstallerDlgProc</a>
</td>
<td align="left" width="63%">
A user interface plug-in's <code>IPrintOemUI::FontInstallerDlgProc</code> method replaces the Unidrv font installer's user interface.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfinterrupt-getinfo">GetInfo</a>
</td>
<td align="left" width="63%">
A user interface plug-in's <code>IPrintOemUI::GetInfo</code> method returns identification information.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemui-printerevent">PrinterEvent</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUI::PrinterEvent</code> method allows a user interface plug-in to process printer events.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemui-publishdriverinterface">PublishDriverInterface</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUI::PublishDriverInterface</code> method allows a user interface plug-in to obtain the Unidrv or Pscript5 driver's <b>IPrintOemDriverUI</b>, <b>IPrintCoreUI2</b>, <b>IPrintCoreHelperPS</b>, or <b>IPrintCoreHelperUni</b> interface.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemui-querycolorprofile">QueryColorProfile</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUI::QueryColorProfile</code> method allows a user interface plug-in to specify an ICC profile to use for color management.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemui-updateexternalfonts">UpdateExternalFonts</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUI::UpdateExternalFonts</code> method allows a user interface plug-in to update a printer's <a href="https://docs.microsoft.com/windows-hardware/drivers/print/customized-font-management">Unidrv Font Format Files</a> (.uff file).

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemui-upgradeprinter">UpgradePrinter</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUI::UpgradePrinter</code> method allows a user interface plug-in to upgrade device option values that are stored in the registry.

</td>
</tr>
</table> 

