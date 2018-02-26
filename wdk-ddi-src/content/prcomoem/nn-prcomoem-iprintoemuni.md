---
UID: NN:prcomoem.IPrintOemUni
title: IPrintOemUni
author: windows-driver-content
description: This section describes the methods defined for the IPrintOemUni COM interface.
old-location: print\iprintoemuni_interface.htm
old-project: print
ms.assetid: 097366a0-2ded-435c-9b63-2b736b716032
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IPrintOemUni, IPrintOemUni interface [Print Devices], IPrintOemUni interface [Print Devices], described, prcomoem/IPrintOemUni, print.iprintoemuni_interface, print_unidrv-pscript_rendering_e715c57a-f4a8-4dde-894b-a19761ea0755.xml
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
-	IPrintOemUni
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemUni interface


## -description


This section describes the methods defined for the IPrintOemUni COM interface.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintOemUni</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IPrintOemUni</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrintOemUni</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/e1708017-a546-4770-8ad1-7052b3d4e264">CommandCallback</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::CommandCallback</code> method is used to provide dynamically generated printer commands for Unidrv-supported printers.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/02524493-3842-462e-86f6-2ab35998c65e">Compression</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::Compression</code> method can be used with Unidrv-supported printers to provide a customized bitmap compression method.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/df6bde70-ba14-411b-88a1-b45f2e2756ef">DevMode</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::DevMode</code> method, provided by rendering plug-ins for Unidrv, performs operations on private <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> members.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/a92d8c2e-52b5-4941-b49e-42e067e56e91">DisableDriver</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemuNI::DisableDriver</code> method allows a rendering plug-in for <a href="https://msdn.microsoft.com/0a51fa2b-3d09-4a5f-9fff-40604877a414">Unidrv</a> to free resources that were allocated by the plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554248">IPrintOemUni::EnableDriver</a> method.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/bdceeb23-5d4a-4a1c-98b2-014a4126ca5f">DisablePDEV</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::DisablePDEV</code> method allows a rendering plug-in for <a href="https://msdn.microsoft.com/0a51fa2b-3d09-4a5f-9fff-40604877a414">Unidrv</a> to delete the private PDEV structure that was allocated by its <a href="https://msdn.microsoft.com/library/windows/hardware/ff554249">IPrintOemUni::EnablePDEV</a> method.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/1ce7ebaa-759e-418a-af07-e530b1102567">DownloadCharGlyph</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::DownloadCharGlyph</code> method enables a rendering plug-in for Unidrv to send a character glyph for a specified soft font to the printer.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/3d660d04-2872-44e6-ab76-719f5262bdd8">DownloadFontHeader</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::DownloadFontHeader</code> method allows a rendering plug-in for <a href="https://msdn.microsoft.com/0a51fa2b-3d09-4a5f-9fff-40604877a414">Unidrv</a> to send a font's header information to a printer.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/b62e6752-0804-41c4-84f4-49ad145acaf3">DriverDMS</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::DriverDMS</code> method allows a rendering plug-in for <a href="https://msdn.microsoft.com/0a51fa2b-3d09-4a5f-9fff-40604877a414">Unidrv</a> to indicate that it uses a device-managed drawing surface.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/7d7cd1de-569a-4083-8d4c-e073645941e6">EnableDriver</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::EnableDriver</code> method allows a rendering plug-in for <a href="https://msdn.microsoft.com/0a51fa2b-3d09-4a5f-9fff-40604877a414">Unidrv</a> to hook out some graphics DDI functions.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/93028b21-7995-42cd-af14-97e74ae75092">EnablePDEV</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::EnablePDEV</code> method allows a rendering plug-in for <a href="https://msdn.microsoft.com/0a51fa2b-3d09-4a5f-9fff-40604877a414">Unidrv</a> to create its own PDEV structure.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/a1651745-08f0-44f2-bb9f-825d6497db42">FilterGraphics</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::FilterGraphics</code> method can be used with Unidrv-supported printers to modify scan line data and send it to the spooler.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/bc2a00ea-214a-435a-86fa-d694188d0245">GetImplementedMethod</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::GetImplementedMethod</code> method is used by Unidrv to determine which <b>IPrintOemUni</b> interface methods a rendering plug-in has implemented.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451309">GetInfo</a>
</td>
<td align="left" width="63%">
A rendering plug-in's <code>IPrintOemUni::GetInfo</code> method returns identification information.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/1b899492-f4a7-4c13-9e19-0f086b2b6b47">HalftonePattern</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::HalftonePattern</code> method can be used with Unidrv-supported printers to create or modify a halftone pattern before it is used in a halftoning operation.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/201450cb-cda6-4dd3-93ee-056d1627b00d">ImageProcessing</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::ImageProcessing</code> method can be used with Unidrv-supported printers to modify image bitmap data, in order to perform color formatting or halftoning. The method can return the modified bitmap to Unidrv or send it directly to the print spooler.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/bdf9c43d-d747-40e8-86ba-976f3f6a19d6">MemoryUsage</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::MemoryUsage</code> method can be used with Unidrv-supported printers to specify the amount of memory required for use by a rendering plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554261">IPrintOemUni::ImageProcessing</a> method.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/73518253-d65a-40ab-8735-44e92fbbed57">OutputCharStr</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::OutputCharStr</code> method enables a rendering plug-in to control the printing of font glyphs.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/72bfa383-a7f2-4aa6-a45c-564928705e42">PublishDriverInterface</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::PublishDriverInterface</code> method allows a rendering plug-in for Unidrv to obtain the Unidrv driver's <b>IPrintOemDriverUni</b> or <b>IPrintCoreHelperUni</b> interface.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/7398a265-56e0-4b40-bfbb-0d72e7309efc">ResetPDEV</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::ResetPDEV</code> method allows a rendering plug-in for Unidrv to reset its PDEV structure.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/b90a94d1-c6f3-483c-b5fc-edfee27094ab">SendFontCmd</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::SendFontCmd</code> method enables a rendering plug-in to modify a printer's font selection command and then send it to the printer.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/2c144eb7-6279-490a-813c-6c0ae995c6ad">TextOutAsBitmap</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::TextOutAsBitmap</code> method allows a rendering plug-in to create a bitmap image of a text string, in case a downloadable font is not available.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/bf8c2baf-eaca-4d0e-a6d6-dba67b2f85db">TTDownloadMethod</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::TTDownloadMethod</code> method enables a rendering plug-in to indicate the format that Unidrv should use for a specified TrueType soft font.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/0df8c555-4298-47e7-a6a7-43f101620e04">TTYGetInfo</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::TTYGetInfo</code> method enables a rendering plug-in to supply Unidrv with information relevant to text-only printers.

</td>
</tr>
</table> 

