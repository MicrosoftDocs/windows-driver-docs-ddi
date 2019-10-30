---
UID: NN:prcomoem.IPrintOemUni
title: IPrintOemUni (prcomoem.h)
description: This section describes the methods defined for the IPrintOemUni COM interface.
old-location: print\iprintoemuni_interface.htm
tech.root: print
ms.assetid: 097366a0-2ded-435c-9b63-2b736b716032
ms.date: 04/20/2018
ms.keywords: IPrintOemUni, IPrintOemUni interface [Print Devices], IPrintOemUni interface [Print Devices],described, prcomoem/IPrintOemUni, print.iprintoemuni_interface, print_unidrv-pscript_rendering_e715c57a-f4a8-4dde-894b-a19761ea0755.xml
ms.topic: interface
f1_keywords:
 - "prcomoem/IPrintOemUni"
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
- IPrintOemUni
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUni interface


## -description


This section describes the methods defined for the IPrintOemUni COM interface.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintOemUni</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPrintOemUni</b> also has these types of members:
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
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-commandcallback">CommandCallback</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::CommandCallback</code> method is used to provide dynamically generated printer commands for Unidrv-supported printers.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-compression">Compression</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::Compression</code> method can be used with Unidrv-supported printers to provide a customized bitmap compression method.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-devmode">DevMode</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::DevMode</code> method, provided by rendering plug-ins for Unidrv, performs operations on private <a href="https://docs.microsoft.com/windows/desktop/api/wingdi/ns-wingdi-_devicemodew">DEVMODEW</a> members.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-disabledriver">DisableDriver</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemuNI::DisableDriver</code> method allows a rendering plug-in for <a href="https://docs.microsoft.com/windows-hardware/drivers/">Unidrv</a> to free resources that were allocated by the plug-in's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-enabledriver">IPrintOemUni::EnableDriver</a> method.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-disablepdev">DisablePDEV</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::DisablePDEV</code> method allows a rendering plug-in for <a href="https://docs.microsoft.com/windows-hardware/drivers/">Unidrv</a> to delete the private PDEV structure that was allocated by its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-enablepdev">IPrintOemUni::EnablePDEV</a> method.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-downloadcharglyph">DownloadCharGlyph</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::DownloadCharGlyph</code> method enables a rendering plug-in for Unidrv to send a character glyph for a specified soft font to the printer.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-downloadfontheader">DownloadFontHeader</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::DownloadFontHeader</code> method allows a rendering plug-in for <a href="https://docs.microsoft.com/windows-hardware/drivers/">Unidrv</a> to send a font's header information to a printer.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-driverdms">DriverDMS</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::DriverDMS</code> method allows a rendering plug-in for <a href="https://docs.microsoft.com/windows-hardware/drivers/">Unidrv</a> to indicate that it uses a device-managed drawing surface.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-enabledriver">EnableDriver</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::EnableDriver</code> method allows a rendering plug-in for <a href="https://docs.microsoft.com/windows-hardware/drivers/">Unidrv</a> to hook out some graphics DDI functions.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-enablepdev">EnablePDEV</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::EnablePDEV</code> method allows a rendering plug-in for <a href="https://docs.microsoft.com/windows-hardware/drivers/">Unidrv</a> to create its own PDEV structure.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-filtergraphics">FilterGraphics</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::FilterGraphics</code> method can be used with Unidrv-supported printers to modify scan line data and send it to the spooler.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-getimplementedmethod">GetImplementedMethod</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::GetImplementedMethod</code> method is used by Unidrv to determine which <b>IPrintOemUni</b> interface methods a rendering plug-in has implemented.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfinterrupt-getinfo">GetInfo</a>
</td>
<td align="left" width="63%">
A rendering plug-in's <code>IPrintOemUni::GetInfo</code> method returns identification information.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-halftonepattern">HalftonePattern</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::HalftonePattern</code> method can be used with Unidrv-supported printers to create or modify a halftone pattern before it is used in a halftoning operation.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-imageprocessing">ImageProcessing</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::ImageProcessing</code> method can be used with Unidrv-supported printers to modify image bitmap data, in order to perform color formatting or halftoning. The method can return the modified bitmap to Unidrv or send it directly to the print spooler.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-memoryusage">MemoryUsage</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::MemoryUsage</code> method can be used with Unidrv-supported printers to specify the amount of memory required for use by a rendering plug-in's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-imageprocessing">IPrintOemUni::ImageProcessing</a> method.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-outputcharstr">OutputCharStr</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::OutputCharStr</code> method enables a rendering plug-in to control the printing of font glyphs.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-publishdriverinterface">PublishDriverInterface</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::PublishDriverInterface</code> method allows a rendering plug-in for Unidrv to obtain the Unidrv driver's <b>IPrintOemDriverUni</b> or <b>IPrintCoreHelperUni</b> interface.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-resetpdev">ResetPDEV</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::ResetPDEV</code> method allows a rendering plug-in for Unidrv to reset its PDEV structure.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-sendfontcmd">SendFontCmd</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::SendFontCmd</code> method enables a rendering plug-in to modify a printer's font selection command and then send it to the printer.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-textoutasbitmap">TextOutAsBitmap</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::TextOutAsBitmap</code> method allows a rendering plug-in to create a bitmap image of a text string, in case a downloadable font is not available.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-ttdownloadmethod">TTDownloadMethod</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::TTDownloadMethod</code> method enables a rendering plug-in to indicate the format that Unidrv should use for a specified TrueType soft font.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-ttygetinfo">TTYGetInfo</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni::TTYGetInfo</code> method enables a rendering plug-in to supply Unidrv with information relevant to text-only printers.

</td>
</tr>
</table> 

