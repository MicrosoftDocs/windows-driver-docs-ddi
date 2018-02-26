---
UID: NN:prcomoem.IPrintOemUni3
title: IPrintOemUni3
author: windows-driver-content
description: This section describes the methods defined for the IPrintOemUni3 COM interface.
old-location: print\iprintoemuni3_interface.htm
old-project: print
ms.assetid: cf5705fb-8420-4eec-99d4-d56f192da581
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IPrintOemUni3, IPrintOemUni3 interface [Print Devices], IPrintOemUni3 interface [Print Devices], described, prcomoem/IPrintOemUni3, print.iprintoemuni3_interface, print_unidrv-pscript_rendering_631f975d-1d52-4db8-8e90-71cdb99f4ef1.xml
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
-	IPrintOemUni3
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemUni3 interface


## -description


This section describes the methods defined for the <b>IPrintOemUni3</b> COM interface.

The <b>IPrintOemUni3</b> COM interface includes its own methods as well as those that belong to <a href="..\prcomoem\nn-prcomoem-iprintoemuni.md">IPrintOemUni</a> COM interface and the <a href="..\prcomoem\nn-prcomoem-iprintoemuni2.md">IPrintOemUni2</a> COM interface.

The <b>IPrintOemUni3</b> COM interface is available in Windows Vista and later.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintOemUni3</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IPrintOemUni3</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrintOemUni3</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/7604a6df-c73a-4114-916f-1e777a323731">DownloadPattern</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni3::DownloadPattern</code> method downloads a pattern to a printer.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/a1de8e8f-eca1-4630-b689-585027184a08">GetImplementedMethod</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni3::GetImplementedMethod</code> method is used by Unidrv to determine which <b>IPrintOemUni</b> interface methods a rendering plug-in has implemented.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/bb7d7248-9520-4bc8-8483-b05b78608fc7">GetPDEVAdjustment</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni3::GetPDEVAdjustment</code> method enables a plug-in to override specific <a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">PDEV</a> settings.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/e75fdfa5-2b25-4d89-b3ef-40cb445f874f">SetBandSize</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUni3::SetBandSize</code> method can be used with Unidrv-supported printers to specify the desired band size on the printed output.

</td>
</tr>
</table> 

