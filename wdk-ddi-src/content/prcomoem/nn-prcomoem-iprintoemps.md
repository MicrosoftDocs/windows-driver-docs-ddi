---
UID: NN:prcomoem.IPrintOemPS
title: IPrintOemPS (prcomoem.h)
description: This section describes the methods defined for the IPrintOemPS COM interface.
old-location: print\iprintoemps_interface.htm
tech.root: print
ms.assetid: 14c545b7-8080-424f-9164-f97ef8a1acc2
ms.date: 04/20/2018
ms.keywords: IPrintOemPS, IPrintOemPS interface [Print Devices], IPrintOemPS interface [Print Devices],described, prcomoem/IPrintOemPS, print.iprintoemps_interface, print_unidrv-pscript_rendering_f48d01c9-e49f-40b6-90ab-6904f0081305.xml
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
- IPrintOemPS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemPS interface


## -description


This section describes the methods defined for the <b>IPrintOemPS</b> COM interface.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintOemPS</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPrintOemPS</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrintOemPS</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemps-command">IPrintOemPS::Command</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemPS::Command</code> method is used by rendering plug-ins for the Microsoft PostScript printer driver, in order to insert PostScript commands into the print job's data stream.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemps-devmode">IPrintOemPS::DevMode</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemPS::DevMode</code> method, provided by rendering plug-ins for Pscript5, performs operations on private <a href="https://docs.microsoft.com/windows/desktop/api/wingdi/ns-wingdi-_devicemodew">DEVMODEW</a> members.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemps-disabledriver">IPrintOemPS::DisableDriver</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemPS::DisableDriver</code> method allows a rendering plug-in for <a href="https://docs.microsoft.com/windows-hardware/drivers/">Pscript</a> to free resources that were allocated by the plug-in's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemps-enabledriver">IPrintOemPS::EnableDriver</a> method.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemps-disablepdev">IPrintOemPS::DisablePDEV</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemPS::DisablePDEV</code> method allows a rendering plug-in for Pscript5 to delete the private PDEV structure that was allocated by its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemps-enablepdev">IPrintOemPS::EnablePDEV</a> method.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemps-enabledriver">IPrintOemPS::EnableDriver</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemPS::EnableDriver</code> method allows a rendering plug-in for <a href="https://docs.microsoft.com/windows-hardware/drivers/">Pscript</a> to hook out some graphics DDI functions.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemps-enablepdev">IPrintOemPS::EnablePDEV</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemPS::EnablePDEV</code> method allows a rendering plug-in for Pscript5 to create its own PDEV structure.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemps-getinfo">IPrintOemPS::GetInfo</a>
</td>
<td align="left" width="63%">
A rendering plug-in's <code>IPrintOemPS::GetInfo</code> method returns identification information.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemps-publishdriverinterface">IPrintOemPS::PublishDriverInterface</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemPS::PublishDriverInterface</code> method allows a rendering plug-in for Pscript5 to obtain the Pscript5 driver's <b>IPrintCorePS2</b>, <b>IPrintOemDriverPS</b>, or <b>IPrintCoreHelperPS</b> interface.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemps-resetpdev">IPrintOemPS::ResetPDEV</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemPS::ResetPDEV</code> method allows a rendering plug-in for Pscript5 to reset its PDEV structure.

</td>
</tr>
</table> 

