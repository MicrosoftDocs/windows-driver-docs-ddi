---
UID: NF:dbgeng.IDebugBreakpoint2.GetDataParameters
title: IDebugBreakpoint2::GetDataParameters method
author: windows-driver-content
description: The GetDataParameters method returns the parameters for a processor breakpoint.
old-location: debugger\getdataparameters.htm
old-project: debugger
ms.assetid: e281c67a-df97-464e-9996-b15c18172dc4
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugBreakpoint2, IDebugBreakpoint2::GetDataParameters, GetDataParameters
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugBreakpoint.GetDataParameters,IDebugBreakpoint2.GetDataParameters
req.alt-loc: dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugBreakpoint2::GetDataParameters method



## -description
The <b>GetDataParameters</b> method returns the parameters for a processor breakpoint.



## -syntax

````
HRESULT GetDataParameters(
  [out] PULONG Size,
  [out] PULONG AccessType
);
````


## -parameters

### -param Size [out]

The size, in bytes, of the memory block whose access triggers the breakpoint.  For more information about restrictions on the value of <i>Size</i> based on the processor type, see <a href="debugger.controlling_breakpoint_flags_and_parameters#valid_parameters_for_processor_breakpoints#valid_parameters_for_processor_breakpoints">Valid Parameters for Processor Breakpoints</a>.


### -param AccessType [out]

The type of access that triggers the breakpoint.  For a list of possible values, see <a href="debugger.controlling_breakpoint_flags_and_parameters#valid_parameters_for_processor_breakpoints#valid_parameters_for_processor_breakpoints">Valid Parameters for Processor Breakpoints</a>.


## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>The breakpoint is not a processor breakpoint.  For more information about the breakpoint type, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj991813">GetType</a>.

 

This method can also return other error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.


## -remarks
The <a href="https://msdn.microsoft.com/library/windows/hardware/ff548095">GetParameters</a> method also returns the information that is returned in <i>Size</i> and <i>AccessType</i>.

For more information about breakpoint properties, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539284">Controlling Breakpoint Flags and Parameters</a>.</p>