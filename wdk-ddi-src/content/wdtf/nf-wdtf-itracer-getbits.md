---
UID: NF:wdtf.ITracer.GetBits
title: ITracer::GetBits method
author: windows-driver-content
description: The GetBits method returns the set of tracing flags for a coclass as a bit mask, given a specified TTraceLevel value and the CLSID of the coclass.
old-location: dtf\itracer_getbits_method.htm
old-project: dtf
ms.assetid: d5c4f28a-63c0-4b9e-9994-de4589ea96c9
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetBits method [Windows Device Testing Framework], GetBits method [Windows Device Testing Framework], ITracer interface, GetBits,ITracer.GetBits, ITracer, ITracer interface [Windows Device Testing Framework], GetBits method, ITracer::GetBits, ITracer_80af4d1b-1fed-4775-83c6-4b7bee53b4a0.xml, dtf.itracer_getbits_method, wdtf/ITracer::GetBits
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	wdtf.h
api_name:
-	ITracer.GetBits
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# ITracer::GetBits method


## -description


The <b>GetBits</b> method returns the set of tracing flags for a coclass as a bit mask, given a specified <a href="..\wdtf\ne-wdtf-__midl___midl_itf_wdtf_0000_0001_0001.md">TTraceLevel</a> value and the CLSID of the coclass.


## -syntax


````
HRESULT GetBits(
  [in]          CLSID       ClassID,
  [in]          TTraceLevel Level,
  [out, retval] DWORD       *pBits
);
````


## -parameters




### -param ClassID [in]

The CLSID of the co-class of the object that is requesting the tracing bit mask. This parameter causes the interface's <a href="https://msdn.microsoft.com/410fd5b5-cce0-47fe-92c1-5bbd9374a176">TraceLevel Path</a> to be defined as HKCR\CLSID\&lt;<i>ClassID</i>&gt;.


### -param Level [in]

The tracing level that is requested. A value of <b>Trace_Default</b> indicates that <b>GetBits</b> will search the interface's TraceLevel Path for the default level. TraceLevel Path is specified by using either <i>ClassID</i> or <i>pszTraceLevelPath</i>. .


### -param pBits [out, retval]

The returned set of flags as a bit mask.


## -returns



<b>GetBits</b> returns a standard <b>HRESULT</b> value.




## -remarks



The <b>GetBits</b> method is intended for low-level WDTF usage. If you want to change the trace level of an object at runtime, see <a href="..\wdtf\nn-wdtf-itracing.md">ITracing</a>.

If no default trace level exists, this method fails.

If <b>GetBits</b> fails for any reason, the caller is expected to silently continue to use the tracing bit mask of its creator.




## -see-also

<a href="..\wdtf\ne-wdtf-__midl___midl_itf_wdtf_0000_0001_0001.md">TTraceLevel</a>



<a href="..\wdtf\nn-wdtf-itracer.md">ITracer</a>



<a href="..\wdtf\nn-wdtf-itracing.md">ITracing</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20ITracer::GetBits method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

