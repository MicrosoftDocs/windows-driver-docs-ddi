---
UID: NN:prcomoem.IPrintOemDriverPS
title: IPrintOemDriverPS
author: windows-driver-content
description: This section describes the methods defined for the IPrintOemDriverPS COM Interface.
old-location: print\iprintoemdriverps_interface.htm
old-project: print
ms.assetid: 39f791e6-aae3-46f6-8195-c165761d0df5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintOemDriverPS, IPrintOemDriverPS interface [Print Devices], IPrintOemDriverPS interface [Print Devices], described, prcomoem/IPrintOemDriverPS, print.iprintoemdriverps_interface, print_unidrv-pscript_rendering_a44b8943-0472-41da-9e5b-2f82d34e1f9a.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	prcomoem.h
api_name:
-	IPrintOemDriverPS
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemDriverPS interface


## -description


This section describes the methods defined for the IPrintOemDriverPS COM Interface.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintOemDriverPS</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IPrintOemDriverPS</b> also has these types of members:
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548556">DrvGetDriverSetting</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemDriverPS::DrvGetDriverSetting</code> method is provided by the Pscript5 driver so that rendering plug-ins can obtain the current status of printer features and other internal information.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548662">DrvWriteSpoolBuf</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemDriverPS::DrvWriteSpoolBuf</code> method is provided by the Pscript5 driver so that <a href="https://msdn.microsoft.com/e55ca083-2790-4929-9e5b-6fce49eb0404">rendering plug-ins</a> can send printer data to the spooler.

</td>
</tr>
</table> 

