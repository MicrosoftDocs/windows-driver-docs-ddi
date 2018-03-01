---
UID: NF:dbgeng.IDebugBreakpoint.GetDataParameters
title: IDebugBreakpoint::GetDataParameters method
author: windows-driver-content
description: The GetDataParameters method returns the parameters for a processor breakpoint.
old-location: debugger\getdataparameters.htm
old-project: debugger
ms.assetid: e281c67a-df97-464e-9996-b15c18172dc4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: ComOther_297fe316-4a1a-476b-a804-056bb56b6e77.xml, GetDataParameters method [Windows Debugging], GetDataParameters method [Windows Debugging], IDebugBreakpoint interface, GetDataParameters method [Windows Debugging], IDebugBreakpoint2 interface, GetDataParameters,IDebugBreakpoint.GetDataParameters, IDebugBreakpoint, IDebugBreakpoint interface [Windows Debugging], GetDataParameters method, IDebugBreakpoint2 interface [Windows Debugging], GetDataParameters method, IDebugBreakpoint2::GetDataParameters, IDebugBreakpoint::GetDataParameters, dbgeng/IDebugBreakpoint2::GetDataParameters, dbgeng/IDebugBreakpoint::GetDataParameters, debugger.getdataparameters
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: dbgeng.h
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
-	IDebugBreakpoint.GetDataParameters
-	IDebugBreakpoint2.GetDataParameters
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugBreakpoint::GetDataParameters method


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

The size, in bytes, of the memory block whose access triggers the breakpoint.  For more information about restrictions on the value of <i>Size</i> based on the processor type, see <a href="https://msdn.microsoft.com/ed702f01-2a30-4ffb-a804-167cf3b19936">Valid Parameters for Processor Breakpoints</a>.


### -param AccessType [out]

The type of access that triggers the breakpoint.  For a list of possible values, see <a href="https://msdn.microsoft.com/ed702f01-2a30-4ffb-a804-167cf3b19936">Valid Parameters for Processor Breakpoints</a>.


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



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff548095">GetParameters</a> method also returns the information that is returned in <i>Size</i> and <i>AccessType</i>.

For more information about breakpoint properties, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539284">Controlling Breakpoint Flags and Parameters</a>.



