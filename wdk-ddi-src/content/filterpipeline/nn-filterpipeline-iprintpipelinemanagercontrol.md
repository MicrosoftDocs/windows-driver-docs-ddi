---
UID: NN:filterpipeline.IPrintPipelineManagerControl
title: IPrintPipelineManagerControl
author: windows-driver-content
description: The IPrintPipelineManagerControl interface is passed to each filter in the IPrintPipelineFilter::InitializeFilter method.
old-location: print\iprintpipelinemanagercontrol.htm
old-project: print
ms.assetid: 82efbe8d-0928-4550-9de1-a806a00791eb
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IXpsPartIterator, IXpsPartIterator::Reset, Reset
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
req.alt-api: IPrintPipelineManagerControl
req.alt-loc: filterpipeline.h
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
req.typenames: EXpsFontRestriction
---

# IPrintPipelineManagerControl interface



## -description
The <code>IPrintPipelineManagerControl</code> interface is passed to each filter in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554291">IPrintPipelineFilter::InitializeFilter</a> method. Filters use this interface to:

Request shutdown in low-memory situations.

Report when the filters are finished processing.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintPipelineManagerControl</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IPrintPipelineManagerControl</b> also has these types of members:

The <b>IPrintPipelineManagerControl</b> interface has these methods.

The <code>FilterFinished</code> method reports that a filter is finished processing.

The <code>RequestShutdown</code> method requests that a pipeline be shut down.

 


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
</table>The <code>FilterFinished</code> method reports that a filter is finished processing.

The <code>RequestShutdown</code> method requests that a pipeline be shut down.

 


## -remarks
