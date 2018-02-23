---
UID: NN:prcomoem.IPrintOemPS
title: IPrintOemPS
author: windows-driver-content
description: This section describes the methods defined for the IPrintOemPS COM interface.
old-location: print\iprintoemps_interface.htm
old-project: print
ms.assetid: 14c545b7-8080-424f-9164-f97ef8a1acc2
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: print.iprintoemps_interface, IPrintOemPS interface [Print Devices], IPrintOemPS interface [Print Devices], described, IPrintOemPS, prcomoem/IPrintOemPS, print_unidrv-pscript_rendering_f48d01c9-e49f-40b6-90ab-6904f0081305.xml
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
-	IPrintOemPS
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemPS interface


## -description


This section describes the methods defined for the <b>IPrintOemPS</b> COM interface.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintOemPS</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IPrintOemPS</b> also has these types of members:
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553199">IPrintOemPS::Command</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemPS::Command</code> method is used by rendering plug-ins for the Microsoft PostScript printer driver, in order to insert PostScript commands into the print job's data stream.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553205">IPrintOemPS::DevMode</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemPS::DevMode</code> method, provided by rendering plug-ins for Pscript5, performs operations on private <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> members.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553207">IPrintOemPS::DisableDriver</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemPS::DisableDriver</code> method allows a rendering plug-in for <a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">Pscript</a> to free resources that were allocated by the plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff553212">IPrintOemPS::EnableDriver</a> method.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553209">IPrintOemPS::DisablePDEV</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemPS::DisablePDEV</code> method allows a rendering plug-in for Pscript5 to delete the private PDEV structure that was allocated by its <a href="https://msdn.microsoft.com/library/windows/hardware/ff553215">IPrintOemPS::EnablePDEV</a> method.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553212">IPrintOemPS::EnableDriver</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemPS::EnableDriver</code> method allows a rendering plug-in for <a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">Pscript</a> to hook out some graphics DDI functions.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553215">IPrintOemPS::EnablePDEV</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemPS::EnablePDEV</code> method allows a rendering plug-in for Pscript5 to create its own PDEV structure.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553221">IPrintOemPS::GetInfo</a>
</td>
<td align="left" width="63%">
A rendering plug-in's <code>IPrintOemPS::GetInfo</code> method returns identification information.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553228">IPrintOemPS::PublishDriverInterface</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemPS::PublishDriverInterface</code> method allows a rendering plug-in for Pscript5 to obtain the Pscript5 driver's <b>IPrintCorePS2</b>, <b>IPrintOemDriverPS</b>, or <b>IPrintCoreHelperPS</b> interface.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553233">IPrintOemPS::ResetPDEV</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemPS::ResetPDEV</code> method allows a rendering plug-in for Pscript5 to reset its PDEV structure.

</td>
</tr>
</table> 

