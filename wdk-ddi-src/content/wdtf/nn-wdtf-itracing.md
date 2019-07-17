---
UID: NN:wdtf.ITracing
title: ITracing (wdtf.h)
description: The ITracing interface sets an object's TTraceLevel value. This interface is a base interface for most of the WDTF interfaces.
old-location: dtf\itracing.htm
tech.root: dtf
ms.assetid: 919f6ba4-ff8d-4836-b522-90c22a9221ea
ms.date: 04/04/2018
ms.keywords: ITracing, ITracing interface [Windows Device Testing Framework], ITracing interface [Windows Device Testing Framework],described, ITracing_b58b1d4d-7a2b-4162-ad9c-54439afd7b4a.xml, dtf.itracing, wdtf/ITracing
ms.topic: interface
f1_keywords:
 - "wdtf/ITracing"
req.header: wdtf.h
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
req.type-library: WDTF.tlb
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WDTF.tlb
api_name:
- ITracing
- ITracing.SetTraceLevel
product:
- Windows
targetos: Windows
req.typenames: 
---

# ITracing interface


## -description


The <b>ITracing </b>interface sets an object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">TTraceLevel</a> value. This interface is a base interface for most of the WDTF interfaces.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">ITracing</b> interface inherits from the <a href="ebbff4bc-36b2-4861-9efa-ffa45e013eb5">IDispatch</a> interface. <b>ITracing</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>ITracing</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>SetTraceLevel</b></td>
<td align="left" width="63%">
Sets the tracing level for an object.

</td>
</tr>
</table> 


## -remarks



Because the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nn-wdtf-iaction">IAction</a> interface inherits from the <b>ITracing</b> interface, all WDTF plug-ins will support <b>ITracing</b>. All of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">WDTF core interfaces</a> should also support <b>ITracing</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nn-wdtf-iaction">IAction</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">ITracing</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">TTraceLevel</a>
 

 

