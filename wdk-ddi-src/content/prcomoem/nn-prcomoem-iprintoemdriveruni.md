---
UID: NN:prcomoem.IPrintOemDriverUni
title: IPrintOemDriverUni
author: windows-driver-content
description: This section describes the methods defined for the IPrintOemDriverUni COM interface.
old-location: print\iprintoemdriveruni_interface.htm
old-project: print
ms.assetid: efd13e9e-ba25-4d1c-894c-a275374f5266
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: IPrintOemDriverUni, IPrintOemDriverUni interface [Print Devices], IPrintOemDriverUni interface [Print Devices],described, prcomoem/IPrintOemDriverUni, print.iprintoemdriveruni_interface, print_unidrv-pscript_rendering_07d60c45-4913-4cac-b65d-31737752b24f.xml
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
-	IPrintOemDriverUni
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemDriverUni interface


## -description


This section describes the methods defined for the IPrintOemDriverUni COM interface. 


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintOemDriverUni</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IPrintOemDriverUni</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrintOemDriverUni</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553126">IPrintOemDriverUni::DrvGetDriverSetting</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemDriverUni::DrvGetDriverSetting</code> method is provided by the Unidrv driver so that rendering plug-ins can obtain the current status of printer features and other internal information.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553128">IPrintOemDriverUni::DrvGetGPDData</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemDriverUni::DrvGetGPDData</code> method is provided by the Unidrv driver so that rendering plug-ins can obtain data defined in a printer's <a href="https://msdn.microsoft.com/f67c673d-c6f0-49f0-850a-d8b00e99ddd4">GPD</a> file.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553129">IPrintOemDriverUni::DrvGetStandardVariable</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemDriverUni::DrvGetStandardVariable</code> method is provided by the Unidrv driver so that rendering plug-ins can obtain the current value of Unidrv's <a href="https://msdn.microsoft.com/d3f85c0f-7387-4301-8b1e-904471aed4b0">standard variables</a>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553132">IPrintOemDriverUni::DrvUniTextOut</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemDriverUni::DrvUniTextOut</code> method is provided by the Unidrv driver so that a rendering plug-in using a device-managed drawing surface can easily output text strings.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553135">IPrintOemDriverUni::DrvWriteAbortBuf</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemDriverUni::DrvWriteAbortBuf</code> method is provided by the Unidrv driver to allow an OEM <a href="https://msdn.microsoft.com/e55ca083-2790-4929-9e5b-6fce49eb0404">rendering plug-in</a> to send printer clean-up code after a user terminates a print job.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553138">IPrintOemDriverUni::DrvWriteSpoolBuf</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemDriverUni::DrvWriteSpoolBuf</code> method is provided by the Unidrv driver so that a <a href="https://msdn.microsoft.com/e55ca083-2790-4929-9e5b-6fce49eb0404">rendering plug-in</a> can send printer data to the spooler.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553141">IPrintOemDriverUni::DrvXMoveTo</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemDriverUni::DrvXMoveTo</code> method is provided by the Unidrv driver so that a <a href="https://msdn.microsoft.com/e55ca083-2790-4929-9e5b-6fce49eb0404">rendering plug-in</a> can notify the driver of cursor x-position changes.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553144">IPrintOemDriverUni::DrvYMoveTo</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemDriverUni::DrvYMoveTo</code> method is provided by the Unidrv driver so that a <a href="https://msdn.microsoft.com/e55ca083-2790-4929-9e5b-6fce49eb0404">rendering plug-in</a> can notify the driver of cursor y-position changes.

</td>
</tr>
</table> 

