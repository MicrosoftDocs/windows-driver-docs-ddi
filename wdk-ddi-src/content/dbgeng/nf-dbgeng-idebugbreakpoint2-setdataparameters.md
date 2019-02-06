---
UID: NF:dbgeng.IDebugBreakpoint2.SetDataParameters
title: IDebugBreakpoint2::SetDataParameters (dbgeng.h)
description: The SetDataParameters method sets the parameters for a processor breakpoint.
old-location: debugger\setdataparameters.htm
tech.root: debugger
ms.assetid: 66878652-be29-479f-8e00-a9d8ab1b0db7
ms.date: 05/03/2018
ms.keywords: ComOther_250724e6-5ae3-4755-87de-3804e4e6f4ed.xml, IDebugBreakpoint interface [Windows Debugging],SetDataParameters method, IDebugBreakpoint2 interface [Windows Debugging],SetDataParameters method, IDebugBreakpoint2.SetDataParameters, IDebugBreakpoint2::SetDataParameters, IDebugBreakpoint::SetDataParameters, SetDataParameters, SetDataParameters method [Windows Debugging], SetDataParameters method [Windows Debugging],IDebugBreakpoint interface, SetDataParameters method [Windows Debugging],IDebugBreakpoint2 interface, dbgeng/IDebugBreakpoint2::SetDataParameters, dbgeng/IDebugBreakpoint::SetDataParameters, debugger.setdataparameters
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugBreakpoint.SetDataParameters
-	IDebugBreakpoint2.SetDataParameters
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugBreakpoint2::SetDataParameters


## -description


The <b>SetDataParameters</b> method sets the parameters for a processor breakpoint.


## -parameters




### -param Size [in]

The size, in bytes, of the memory block whose access triggers the breakpoint.  For more information about restrictions on the value of <i>Size</i> based on the processor type, see <a href="https://msdn.microsoft.com/ed702f01-2a30-4ffb-a804-167cf3b19936">Valid Parameters for Processor Breakpoints</a>.


### -param AccessType [in]

The type of access that triggers the breakpoint. For a list of possible value, see <a href="https://msdn.microsoft.com/ed702f01-2a30-4ffb-a804-167cf3b19936">Valid Parameters for Processor Breakpoints</a>.


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
The breakpoint is not a processor breakpoint.  For more information about the breakpoint type, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj991813">GetType</a>.

</td>
</tr>
</table>
 

This method can also return other error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.




## -remarks



For more information about breakpoint properties, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539284">Controlling Breakpoint Flags and Parameters</a>.



