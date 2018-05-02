---
UID: NE:wdtf.__MIDL___MIDL_itf_wdtf_0000_0001_0001
title: "__MIDL___MIDL_itf_wdtf_0000_0001_0001"
author: windows-driver-content
description: The TTraceLevel enumeration defines a set of levels for tracing in WDTF. The meaning on each level depends on registry settings for the ITracer interface.
old-location: dtf\ttracelevel.htm
old-project: dtf
ms.assetid: d1bc1775-cb0f-468e-938b-b3ed95e80b5b
ms.author: windowsdriverdev
ms.date: 4/4/2018
ms.keywords: ITracing_6a4e6447-651b-4e2e-9f45-e1bd14e84682.xml, TTraceLevel, TTraceLevel enumeration [Windows Device Testing Framework], Trace0_Off, Trace1_Low, Trace2_Medium, Trace3_High, Trace4_All, Trace5_Custom, Trace6_Custom, Trace7_Custom, Trace8_Custom, Trace_Default, __MIDL___MIDL_itf_wdtf_0000_0001_0001, dtf.ttracelevel, wdtf/TTraceLevel, wdtf/Trace0_Off, wdtf/Trace1_Low, wdtf/Trace2_Medium, wdtf/Trace3_High, wdtf/Trace4_All, wdtf/Trace5_Custom, wdtf/Trace6_Custom, wdtf/Trace7_Custom, wdtf/Trace8_Custom, wdtf/Trace_Default
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdtf.h
api_name:
-	TTraceLevel
product: Windows
targetos: Windows
req.typenames: TTraceLevel
---

# __MIDL___MIDL_itf_wdtf_0000_0001_0001 enumeration


## -description


The <b>TTraceLevel</b> enumeration defines a set of levels for tracing in WDTF. The meaning on each level depends on registry settings for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539512">ITracer</a> interface.


## -enum-fields




### -field Trace0_Off

Tracing is off.


### -field Trace1_Low

The tracing level is low. Generally, only the top layer of traces and failure and warning information is traced.


### -field Trace2_Medium

The tracing level is medium. This level is the default level. It includes all of the traces in <b>Trace1_Low</b> plus standard traces at all layers of WDTF.


### -field Trace3_High

The tracing level is high. This level includes all of the traces in <b>Trace2_Medium</b> plus noisy traces at all layers of WDTF.


### -field Trace4_All

All tracing is enabled. Currently, this tracing level is the same as <b>Trace3_High</b>.


### -field Trace5_Custom

A custom trace level. Currently, this value is set to <b>Trace0_Off</b>.


### -field Trace6_Custom

A custom trace level. Currently, this value is set to <b>Trace0_Off</b>.


### -field Trace7_Custom

A custom trace level. Currently, this value is set to <b>Trace0_Off</b>.


### -field Trace8_Custom

A custom trace level. Currently, this value is set to <b>Trace0_Off</b>.


### -field Trace_Default

The default tracing level. This level tells the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539512">ITracer</a> interface to look for the actual level in the registry. <b>ITracer</b> will look in the TraceLevel path for the implementation that you called the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539522">ITracing::SetTraceLevel</a> method on. For most implementations, this value is set to <b>Trace2_Medium</b> when you install WDTF.


## -remarks



Use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539522">ITracing::SetTraceLevel</a> method to change the trace level of an instance of a WDTF interface at runtime. For more information about how to change the registry default values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539512">ITracer</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539512">ITracer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539519">ITracing</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539522">ITracing::SetTraceLevel</a>
 

 

