---
UID: NF:wdtf.ITracer.GetBits
title: ITracer::GetBits (wdtf.h)
description: The GetBits method returns the set of tracing flags for a coclass as a bit mask, given a specified TTraceLevel value and the CLSID of the coclass.
old-location: dtf\itracer_getbits_method.htm
tech.root: dtf
ms.assetid: d5c4f28a-63c0-4b9e-9994-de4589ea96c9
ms.date: 04/04/2018
keywords: ["ITracer::GetBits"]
ms.keywords: GetBits, GetBits method [Windows Device Testing Framework], GetBits method [Windows Device Testing Framework],ITracer interface, ITracer interface [Windows Device Testing Framework],GetBits method, ITracer.GetBits, ITracer::GetBits, ITracer_80af4d1b-1fed-4775-83c6-4b7bee53b4a0.xml, dtf.itracer_getbits_method, wdtf/ITracer::GetBits
f1_keywords:
 - "wdtf/ITracer.GetBits"
req.header: wdtf.h
req.include-header: 
req.target-type: Desktop
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
- wdtf.h
api_name:
- ITracer.GetBits
product:
- Windows
targetos: Windows
req.typenames: 
---

# ITracer::GetBits


## -description


The <b>GetBits</b> method returns the set of tracing flags for a coclass as a bit mask, given a specified <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">TTraceLevel</a> value and the CLSID of the coclass.


## -parameters




### -param ClassID [in]

The CLSID of the co-class of the object that is requesting the tracing bit mask. This parameter causes the interface's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">TraceLevel Path</a> to be defined as HKCR\CLSID\<<i>ClassID</i>>.


### -param Level [in]

The tracing level that is requested. A value of <b>Trace_Default</b> indicates that <b>GetBits</b> will search the interface's TraceLevel Path for the default level. TraceLevel Path is specified by using either <i>ClassID</i> or <i>pszTraceLevelPath</i>. .


### -param pBits [out, retval]

The returned set of flags as a bit mask.


## -returns



<b>GetBits</b> returns a standard <b>HRESULT</b> value.




## -remarks



The <b>GetBits</b> method is intended for low-level WDTF usage. If you want to change the trace level of an object at runtime, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">ITracing</a>.

If no default trace level exists, this method fails.

If <b>GetBits</b> fails for any reason, the caller is expected to silently continue to use the tracing bit mask of its creator.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">ITracer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">ITracing</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">TTraceLevel</a>
 

 

