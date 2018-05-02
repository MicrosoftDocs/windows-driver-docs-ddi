---
UID: NN:filterpipeline.IPrintPipelineFilter
title: IPrintPipelineFilter
author: windows-driver-content
description: The methods in the IPrintPipelineFilter interface are called for initialization and shutdown. A filter must implement these methods.
old-location: print\iprintpipelinefilter.htm
old-project: print
ms.assetid: e8841091-1d62-4770-aa85-993b49efbd48
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: IPrintPipelineFilter, IPrintPipelineFilter interface [Print Devices], IPrintPipelineFilter interface [Print Devices],described, filterpipeline/IPrintPipelineFilter, filterpipeline_67beec81-fbba-43d2-af2f-ddbc32c68fce.xml, print.iprintpipelinefilter
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
-	IPrintPipelineFilter
product: Windows
targetos: Windows
req.typenames: 
---

# IPrintPipelineFilter interface


## -description


The methods in the <code>IPrintPipelineFilter</code> interface are called for initialization and shutdown. A filter must implement these methods.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintPipelineFilter</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IPrintPipelineFilter</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrintPipelineFilter</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554291">IPrintPipelineFilter::InitializeFilter</a>
</td>
<td align="left" width="63%">
The <code>InitializeFilter</code> method initializes a filter.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554295">IPrintPipelineFilter::ShutdownOperation</a>
</td>
<td align="left" width="63%">
The Pipeline Manager uses the <code>ShutdownOperation</code> method to shut down a filter if the print job is canceled or an error occurs.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554301">IPrintPipelineFilter::StartOperation</a>
</td>
<td align="left" width="63%">
The <code>StartOperation</code> method starts the operation of a filter. The filter reads, processes, and writes data in this method.

</td>
</tr>
</table> 

