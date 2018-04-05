---
UID: NN:filterpipeline.IPrintPipelineManagerControl
title: IPrintPipelineManagerControl
author: windows-driver-content
description: The IPrintPipelineManagerControl interface is passed to each filter in the IPrintPipelineFilter::InitializeFilter method.
old-location: print\iprintpipelinemanagercontrol.htm
old-project: print
ms.assetid: 82efbe8d-0928-4550-9de1-a806a00791eb
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintPipelineManagerControl, IPrintPipelineManagerControl interface [Print Devices], IPrintPipelineManagerControl interface [Print Devices], described, filterpipeline/IPrintPipelineManagerControl, filterpipeline_5b9732d1-6a75-4059-84fa-1bbbdeb70eb3.xml, print.iprintpipelinemanagercontrol
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: filterpipeline.h
req.include-header: Filterpipeline.h
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
-	filterpipeline.h
api_name:
-	IPrintPipelineManagerControl
product:
- Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IPrintPipelineManagerControl interface


## -description


The <code>IPrintPipelineManagerControl</code> interface is passed to each filter in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554291">IPrintPipelineFilter::InitializeFilter</a> method. Filters use this interface to:
<ul>
<li>
Request shutdown in low-memory situations.

</li>
<li>
Report when the filters are finished processing.

</li>
</ul>

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintPipelineManagerControl</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IPrintPipelineManagerControl</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrintPipelineManagerControl</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554306">IPrintPipelineManagerControl::FilterFinished</a>
</td>
<td align="left" width="63%">
The <code>FilterFinished</code> method reports that a filter is finished processing.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554308">IPrintPipelineManagerControl::RequestShutdown</a>
</td>
<td align="left" width="63%">
The <code>RequestShutdown</code> method requests that a pipeline be shut down.

</td>
</tr>
</table> 

