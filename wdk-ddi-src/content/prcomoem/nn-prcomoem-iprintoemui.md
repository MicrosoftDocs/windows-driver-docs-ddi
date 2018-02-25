---
UID: NN:prcomoem.IPrintOemUI
title: IPrintOemUI
author: windows-driver-content
description: This section describes the methods defined for the IPrintOemUI COM interface.
old-location: print\iprintoemui_interface.htm
old-project: print
ms.assetid: 0ef635dd-9598-4356-94fc-7e5237df9bd9
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IPrintOemUI, IPrintOemUI interface [Print Devices], IPrintOemUI interface [Print Devices], described, prcomoem/IPrintOemUI, print.iprintoemui_interface, print_unidrv-pscript_ui_d2e42772-2604-4ef1-a667-70139ac8a62a.xml
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
-	IPrintOemUI
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemUI interface


## -description


This section describes the methods defined for the <b>IPrintOemUI</b> COM interface.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintOemUI</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IPrintOemUI</b> also has these types of members:
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
<a href="https://msdn.microsoft.com/6218913c-d11c-4646-a292-5f8740097d58">CommonUIProp</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUI::CommonUIProp</code> method allows a user interface plug-in to modify an existing printer property sheet page.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/a3d3e986-41ab-489a-a930-b10e9989553f">DeviceCapabilities</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUI::DeviceCapabilities</code> method enables a user interface plug-in to specify customized device capabilities.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/7d782f53-2409-416d-a3be-dad932c440a1">DevicePropertySheets</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUI::DevicePropertySheets</code> method allows a user interface plug-in to append a new page to a printer device's printer property sheet.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/decc76c4-1973-41c5-9091-6dc5b9ccd30d">DevMode</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUI::DevMode</code> method, provided by user interface plug-ins, performs operations on the plug-in's private DEVMODEW members.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/a8c7eb0d-792f-4a6c-af47-bb4558feb790">DocumentPropertySheets</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUI::DocumentPropertySheets</code> method allows a user interface plug-in to append a new page to a printer device's document property sheet.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/aacddaea-3a6f-4018-92ac-fe4aa2ddabd3">DriverEvent</a>
</td>
<td align="left" width="63%">
The printer driver's <a href="..\winddiui\nf-winddiui-drvdriverevent.md">DrvDriverEvent</a> function calls a user interface plug-in's <code>IPrintOemUI::DriverEvent</code> method for additional processing of printer driver events.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/6f63d48d-7c2f-4531-b6db-fd4fdcfbce27">FontInstallerDlgProc</a>
</td>
<td align="left" width="63%">
A user interface plug-in's <code>IPrintOemUI::FontInstallerDlgProc</code> method replaces the Unidrv font installer's user interface.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451309">GetInfo</a>
</td>
<td align="left" width="63%">
A user interface plug-in's <code>IPrintOemUI::GetInfo</code> method returns identification information.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/214ea4d8-3bf9-4248-8bfa-7180635769be">PrinterEvent</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUI::PrinterEvent</code> method allows a user interface plug-in to process printer events.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/4c2053ec-c6b3-4584-b689-dc887610c57e">PublishDriverInterface</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUI::PublishDriverInterface</code> method allows a user interface plug-in to obtain the Unidrv or Pscript5 driver's <b>IPrintOemDriverUI</b>, <b>IPrintCoreUI2</b>, <b>IPrintCoreHelperPS</b>, or <b>IPrintCoreHelperUni</b> interface.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/ce1131f9-4b9c-4f20-afc9-514ccbc7ecf7">QueryColorProfile</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUI::QueryColorProfile</code> method allows a user interface plug-in to specify an ICC profile to use for color management.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/5c501305-fa5f-4466-9a9a-83f072d904b3">UpdateExternalFonts</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUI::UpdateExternalFonts</code> method allows a user interface plug-in to update a printer's <a href="https://msdn.microsoft.com/6e643703-ace1-4660-990c-3a9ca735829d">Unidrv Font Format Files</a> (.uff file).

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/405f0000-c239-4f2c-83ad-5d35441a5df2">UpgradePrinter</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUI::UpgradePrinter</code> method allows a user interface plug-in to upgrade device option values that are stored in the registry.

</td>
</tr>
</table> 

