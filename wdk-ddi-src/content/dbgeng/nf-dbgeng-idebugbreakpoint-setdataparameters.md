---
UID: NF:dbgeng.IDebugBreakpoint.SetDataParameters
title: IDebugBreakpoint::SetDataParameters (dbgeng.h)
description: The SetDataParameters method sets the parameters for a processor breakpoint.
old-location: debugger\setdataparameters.htm
tech.root: debugger
ms.assetid: 66878652-be29-479f-8e00-a9d8ab1b0db7
ms.date: 05/03/2018
ms.keywords: ComOther_250724e6-5ae3-4755-87de-3804e4e6f4ed.xml, IDebugBreakpoint interface [Windows Debugging],SetDataParameters method, IDebugBreakpoint.SetDataParameters, IDebugBreakpoint2 interface [Windows Debugging],SetDataParameters method, IDebugBreakpoint2::SetDataParameters, IDebugBreakpoint::SetDataParameters, SetDataParameters, SetDataParameters method [Windows Debugging], SetDataParameters method [Windows Debugging],IDebugBreakpoint interface, SetDataParameters method [Windows Debugging],IDebugBreakpoint2 interface, dbgeng/IDebugBreakpoint2::SetDataParameters, dbgeng/IDebugBreakpoint::SetDataParameters, debugger.setdataparameters
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugBreakpoint.SetDataParameters"
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
- dbgeng.h
api_name:
- IDebugBreakpoint.SetDataParameters
- IDebugBreakpoint2.SetDataParameters
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugBreakpoint::SetDataParameters


## -description


The <b>SetDataParameters</b> method sets the parameters for a processor breakpoint.


## -parameters




### -param Size [in]

The size, in bytes, of the memory block whose access triggers the breakpoint.  For more information about restrictions on the value of <i>Size</i> based on the processor type, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/controlling-breakpoint-flags-and-parameters">Valid Parameters for Processor Breakpoints</a>.


### -param AccessType [in]

The type of access that triggers the breakpoint. For a list of possible value, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/controlling-breakpoint-flags-and-parameters">Valid Parameters for Processor Breakpoints</a>.


## -returns



<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
The breakpoint is not a processor breakpoint.  For more information about the breakpoint type, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfaentrytags-gettype">GetType</a>.

</td>
</tr>
</table>
 

This method can also return other error values.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a>.




## -remarks



For more information about breakpoint properties, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/controlling-breakpoint-flags-and-parameters">Controlling Breakpoint Flags and Parameters</a>.



