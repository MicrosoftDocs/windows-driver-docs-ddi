---
UID: NN:prcomoem.IPrintOemDriverUni
title: IPrintOemDriverUni (prcomoem.h)
description: This section describes the methods defined for the IPrintOemDriverUni COM interface.
old-location: print\iprintoemdriveruni_interface.htm
tech.root: print
ms.assetid: efd13e9e-ba25-4d1c-894c-a275374f5266
ms.date: 04/20/2018
ms.keywords: IPrintOemDriverUni, IPrintOemDriverUni interface [Print Devices], IPrintOemDriverUni interface [Print Devices],described, prcomoem/IPrintOemDriverUni, print.iprintoemdriveruni_interface, print_unidrv-pscript_rendering_07d60c45-4913-4cac-b65d-31737752b24f.xml
ms.topic: interface
f1_keywords:
 - "prcomoem/IPrintOemDriverUni"
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
- IPrintOemDriverUni
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemDriverUni interface


## -description


This section describes the methods defined for the IPrintOemDriverUni COM interface. 


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintOemDriverUni</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPrintOemDriverUni</b> also has these types of members:
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
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemdriveruni-drvgetdriversetting">IPrintOemDriverUni::DrvGetDriverSetting</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemDriverUni::DrvGetDriverSetting</code> method is provided by the Unidrv driver so that rendering plug-ins can obtain the current status of printer features and other internal information.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemdriveruni-drvgetgpddata">IPrintOemDriverUni::DrvGetGPDData</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemDriverUni::DrvGetGPDData</code> method is provided by the Unidrv driver so that rendering plug-ins can obtain data defined in a printer's <a href="https://docs.microsoft.com/windows-hardware/drivers/">GPD</a> file.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemdriveruni-drvgetstandardvariable">IPrintOemDriverUni::DrvGetStandardVariable</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemDriverUni::DrvGetStandardVariable</code> method is provided by the Unidrv driver so that rendering plug-ins can obtain the current value of Unidrv's <a href="https://docs.microsoft.com/windows-hardware/drivers/print/standard-variables">standard variables</a>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemdriveruni-drvunitextout">IPrintOemDriverUni::DrvUniTextOut</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemDriverUni::DrvUniTextOut</code> method is provided by the Unidrv driver so that a rendering plug-in using a device-managed drawing surface can easily output text strings.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemdriveruni-drvwriteabortbuf">IPrintOemDriverUni::DrvWriteAbortBuf</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemDriverUni::DrvWriteAbortBuf</code> method is provided by the Unidrv driver to allow an OEM <a href="https://docs.microsoft.com/windows-hardware/drivers/print/rendering-plug-ins">rendering plug-in</a> to send printer clean-up code after a user terminates a print job.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemdriveruni-drvwritespoolbuf">IPrintOemDriverUni::DrvWriteSpoolBuf</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemDriverUni::DrvWriteSpoolBuf</code> method is provided by the Unidrv driver so that a <a href="https://docs.microsoft.com/windows-hardware/drivers/print/rendering-plug-ins">rendering plug-in</a> can send printer data to the spooler.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemdriveruni-drvxmoveto">IPrintOemDriverUni::DrvXMoveTo</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemDriverUni::DrvXMoveTo</code> method is provided by the Unidrv driver so that a <a href="https://docs.microsoft.com/windows-hardware/drivers/print/rendering-plug-ins">rendering plug-in</a> can notify the driver of cursor x-position changes.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemdriveruni-drvymoveto">IPrintOemDriverUni::DrvYMoveTo</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemDriverUni::DrvYMoveTo</code> method is provided by the Unidrv driver so that a <a href="https://docs.microsoft.com/windows-hardware/drivers/print/rendering-plug-ins">rendering plug-in</a> can notify the driver of cursor y-position changes.

</td>
</tr>
</table> 

