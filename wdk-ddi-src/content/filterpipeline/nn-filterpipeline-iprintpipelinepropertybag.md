---
UID: NN:filterpipeline.IPrintPipelinePropertyBag
title: IPrintPipelinePropertyBag
author: windows-driver-content
description: The IPrintPipelinePropertyBag interface is implemented by the PrintFilterPipelineSvc service and is made available to filters through methods in the IPrintPipelineFilter interface. IprintPipelinePropertyBag inherits from the IUnknown interface.
old-location: print\iprintpipelinepropertybag.htm
old-project: print
ms.assetid: 3997291f-0af3-4fa8-8d36-20ff36551f42
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
req.alt-api: IPrintPipelinePropertyBag
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

# IPrintPipelinePropertyBag interface



## -description
The <code>IPrintPipelinePropertyBag</code> interface is implemented by the PrintFilterPipelineSvc service and is made available to filters through methods in the <a href="..\filterpipeline\nn-filterpipeline-iprintpipelinefilter.md">IPrintPipelineFilter</a> interface. <code>IprintPipelinePropertyBag</code> inherits from the <b>IUnknown</b> interface.

The properties of the property bag are described in <a href="https://msdn.microsoft.com/library/windows/hardware/ff561066">Print Pipeline Property Bag</a>.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintPipelinePropertyBag</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IPrintPipelinePropertyBag</b> also has these types of members:

The <b>IPrintPipelinePropertyBag</b> interface has these methods.

The <code>AddProperty</code> method adds a property to a property bag.

The <code>DeleteProperty</code> method deletes a property from a property bag.

The <code>GetProperty</code> method gets a property from a property bag.

 


## -members
The <b>IPrintPipelinePropertyBag</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554325">IPrintPipelinePropertyBag::AddProperty</a>
</td>
<td align="left" width="63%">
The <code>AddProperty</code> method adds a property to a property bag.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554327">IPrintPipelinePropertyBag::DeleteProperty</a>
</td>
<td align="left" width="63%">
The <code>DeleteProperty</code> method deletes a property from a property bag.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554331">IPrintPipelinePropertyBag::GetProperty</a>
</td>
<td align="left" width="63%">
The <code>GetProperty</code> method gets a property from a property bag.

</td>
</tr>
</table>The <code>AddProperty</code> method adds a property to a property bag.

The <code>DeleteProperty</code> method deletes a property from a property bag.

The <code>GetProperty</code> method gets a property from a property bag.

 


## -remarks
