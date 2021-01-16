---
UID: NN:wdtf.ITracing
title: ITracing (wdtf.h)
description: The ITracing interface sets an object's TTraceLevel value. This interface is a base interface for most of the WDTF interfaces.
old-location: dtf\itracing.htm
tech.root: dtf
ms.date: 04/04/2018
keywords: ["ITracing interface"]
ms.keywords: ITracing, ITracing interface [Windows Device Testing Framework], ITracing interface [Windows Device Testing Framework],described, ITracing_b58b1d4d-7a2b-4162-ad9c-54439afd7b4a.xml, dtf.itracing, wdtf/ITracing
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
targetos: Windows
req.typenames: 
f1_keywords:
 - ITracing
 - wdtf/ITracing
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WDTF.tlb
api_name:
 - ITracing
---

# ITracing interface


## -description

The <b>ITracing</b>interface sets an object's <a href="/windows-hardware/drivers/ddi/index">TTraceLevel</a> value. This interface is a base interface for most of the WDTF interfaces.

## -inheritance

The <b>ITracing</b> interface inherits from the <a href="/windows/win32/api/oaidl/nn-oaidl-idispatch">IDispatch</a> interface.

<b>ITracing</b> also has these types of members:
<ul>
<li>Methods</li>
</ul>

## -remarks

Because the <a href="/windows-hardware/drivers/ddi/wdtf/nn-wdtf-iaction">IAction</a> interface inherits from the <b>ITracing</b> interface, all WDTF plug-ins will support <b>ITracing</b>. All of the <a href="/windows-hardware/drivers/ddi/index">WDTF core interfaces</a> should also support <b>ITracing</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdtf/nn-wdtf-iaction">IAction</a>



<a href="/windows-hardware/drivers/ddi/index">ITracing</a>



<a href="/windows-hardware/drivers/ddi/index">TTraceLevel</a>

