---
UID: NF:dbgeng.IDebugControl4.GetEventFilterCommandWide
title: IDebugControl4::GetEventFilterCommandWide
author: windows-driver-content
description: The GetEventFilterCommandWide method returns the debugger command that the engine will execute when a specified event occurs.
old-location: debugger\geteventfiltercommandwide.htm
old-project: debugger
ms.assetid: a565627a-4a70-4255-9a88-c39a3db11d25
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: GetEventFilterCommandWide, GetEventFilterCommandWide method [Windows Debugging], GetEventFilterCommandWide method [Windows Debugging],IDebugControl4 interface, IDebugControl4 interface [Windows Debugging],GetEventFilterCommandWide method, IDebugControl4.GetEventFilterCommandWide, IDebugControl4::GetEventFilterCommandWide, dbgeng/IDebugControl4::GetEventFilterCommandWide, debugger.geteventfiltercommandwide
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
-	IDebugControl4.GetEventFilterCommandWide
product: Windows
targetos: Windows
req.typenames: 
---

# IDebugControl4::GetEventFilterCommandWide


## -description


The <b>GetEventFilterCommandWide</b>  method returns the debugger command that the engine will execute when a specified event occurs.


## -parameters




### -param Index [in]

Specifies the index of the event filter.  <i>Index</i> can take any value between zero and one less than the total number of event filters returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff547899">GetNumberEventFilters</a> (inclusive).  For more information about the index of the filters, see Index and Exception Code.


### -param Buffer [out, optional]

Receives the debugger command that the engine will execute when the event occurs.


### -param BufferSize [in]

Specifies the size, in characters, of the buffer that <i>Buffer</i> specifies.


### -param CommandSize [out, optional]

Receives the size in characters of the command.  If <i>CommandSize</i> is <b>NULL</b>, this information is not returned.


## -returns



This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
</table>
 




## -remarks



For more information about event filters, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543071">Event Filters</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546653">GetExceptionFilterSecondCommand</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550526">IDebugControl4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556678">SetEventFilterCommand</a>



<a href="https://msdn.microsoft.com/fdb5059f-e7d9-4e14-aa3d-030e72c30732">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>
 

 

