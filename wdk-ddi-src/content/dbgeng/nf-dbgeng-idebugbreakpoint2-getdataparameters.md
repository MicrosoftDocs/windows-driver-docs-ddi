---
UID: NF:dbgeng.IDebugBreakpoint2.GetDataParameters
title: IDebugBreakpoint2::GetDataParameters (dbgeng.h)
description: The GetDataParameters method returns the parameters for a processor breakpoint.
old-location: debugger\getdataparameters.htm
tech.root: debugger
ms.assetid: e281c67a-df97-464e-9996-b15c18172dc4
ms.date: 05/03/2018
keywords: ["IDebugBreakpoint2::GetDataParameters"]
ms.keywords: ComOther_297fe316-4a1a-476b-a804-056bb56b6e77.xml, GetDataParameters, GetDataParameters method [Windows Debugging], GetDataParameters method [Windows Debugging],IDebugBreakpoint interface, GetDataParameters method [Windows Debugging],IDebugBreakpoint2 interface, IDebugBreakpoint interface [Windows Debugging],GetDataParameters method, IDebugBreakpoint2 interface [Windows Debugging],GetDataParameters method, IDebugBreakpoint2.GetDataParameters, IDebugBreakpoint2::GetDataParameters, IDebugBreakpoint::GetDataParameters, dbgeng/IDebugBreakpoint2::GetDataParameters, dbgeng/IDebugBreakpoint::GetDataParameters, debugger.getdataparameters
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IDebugBreakpoint2::GetDataParameters
 - dbgeng/IDebugBreakpoint2::GetDataParameters
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugBreakpoint.GetDataParameters
 - IDebugBreakpoint2.GetDataParameters
---

# IDebugBreakpoint2::GetDataParameters


## -description

The <b>GetDataParameters</b> method returns the parameters for a processor breakpoint.

## -parameters

### -param Size 

[out]
The size, in bytes, of the memory block whose access triggers the breakpoint.  For more information about restrictions on the value of <i>Size</i> based on the processor type, see <a href="/windows-hardware/drivers/debugger/controlling-breakpoint-flags-and-parameters">Valid Parameters for Processor Breakpoints</a>.

### -param AccessType 

[out]
The type of access that triggers the breakpoint.  For a list of possible values, see <a href="/windows-hardware/drivers/debugger/controlling-breakpoint-flags-and-parameters">Valid Parameters for Processor Breakpoints</a>.

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
The breakpoint is not a processor breakpoint.  For more information about the breakpoint type, see <a href="/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfaentrytags-gettype">GetType</a>.

</td>
</tr>
</table>
 

This method can also return other error values.  For more information, see <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a>.

## -remarks

The <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-getparameters">GetParameters</a> method also returns the information that is returned in <i>Size</i> and <i>AccessType</i>.

For more information about breakpoint properties, see <a href="/windows-hardware/drivers/debugger/controlling-breakpoint-flags-and-parameters">Controlling Breakpoint Flags and Parameters</a>.