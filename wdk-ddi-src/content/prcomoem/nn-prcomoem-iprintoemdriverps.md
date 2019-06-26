---
UID: NN:prcomoem.IPrintOemDriverPS
title: IPrintOemDriverPS (prcomoem.h)
description: This section describes the methods defined for the IPrintOemDriverPS COM Interface.
old-location: print\iprintoemdriverps_interface.htm
tech.root: print
ms.assetid: 39f791e6-aae3-46f6-8195-c165761d0df5
ms.date: 04/20/2018
ms.keywords: IPrintOemDriverPS, IPrintOemDriverPS interface [Print Devices], IPrintOemDriverPS interface [Print Devices],described, prcomoem/IPrintOemDriverPS, print.iprintoemdriverps_interface, print_unidrv-pscript_rendering_a44b8943-0472-41da-9e5b-2f82d34e1f9a.xml
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
- IPrintOemDriverPS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemDriverPS interface


## -description


This section describes the methods defined for the IPrintOemDriverPS COM Interface.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintOemDriverPS</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPrintOemDriverPS</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrintOemDriverPS</b> interface has these methods.
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
The <code>IPrintOemDriverPS::DrvGetDriverSetting</code> method is provided by the Pscript5 driver so that rendering plug-ins can obtain the current status of printer features and other internal information.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printoem/nc-printoem-pfn_drvwritespoolbuf">DrvWriteSpoolBuf</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemDriverPS::DrvWriteSpoolBuf</code> method is provided by the Pscript5 driver so that <a href="https://docs.microsoft.com/windows-hardware/drivers/print/rendering-plug-ins">rendering plug-ins</a> can send printer data to the spooler.

</td>
</tr>
</table> 

