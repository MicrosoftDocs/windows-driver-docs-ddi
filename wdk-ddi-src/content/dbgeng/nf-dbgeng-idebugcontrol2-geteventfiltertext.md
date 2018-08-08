---
UID: NF:dbgeng.IDebugControl2.GetEventFilterText
title: IDebugControl2::GetEventFilterText
author: windows-driver-content
description: The GetEventFilterText method returns a short description of an event for a specific filter.
old-location: debugger\geteventfiltertext.htm
tech.root: debugger
ms.assetid: d311a030-e24c-427c-8a52-0c67d4fac653
ms.author: windowsdriverdev
ms.date: 5/3/2018
ms.keywords: GetEventFilterText, GetEventFilterText method [Windows Debugging], GetEventFilterText method [Windows Debugging],IDebugControl interface, GetEventFilterText method [Windows Debugging],IDebugControl2 interface, GetEventFilterText method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetEventFilterText method, IDebugControl2 interface [Windows Debugging],GetEventFilterText method, IDebugControl2.GetEventFilterText, IDebugControl2::GetEventFilterText, IDebugControl3 interface [Windows Debugging],GetEventFilterText method, IDebugControl3::GetEventFilterText, IDebugControl::GetEventFilterText, IDebugControl_61936aac-8fe2-4f18-86aa-cba1404d845f.xml, dbgeng/IDebugControl2::GetEventFilterText, dbgeng/IDebugControl3::GetEventFilterText, dbgeng/IDebugControl::GetEventFilterText, debugger.geteventfiltertext
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
-	IDebugControl.GetEventFilterText
-	IDebugControl2.GetEventFilterText
-	IDebugControl3.GetEventFilterText
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl2::GetEventFilterText


## -description


The <b>GetEventFilterText</b>  method returns a short description of an event for a specific filter.


## -parameters




### -param Index [in]

Specifies the index of the event filter whose description will be returned.  Only the specific filters have a description attached to them; <i>Index</i> must refer to a specific filter.


### -param Buffer [out, optional]

Receives the description of the specific filter.


### -param BufferSize [in]

Specifies the size, in characters, of the buffer that <i>Buffer</i> specifies.


### -param TextSize [out, optional]

Receives the size of the event description.  If <i>TextSize</i> is <b>NULL</b>, this information is not returned.


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
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
<i>Index</i> did not refer to a specific filter.  This can occur if <i>Index</i> refers to an arbitrary exception filter.

</td>
</tr>
</table>
 




## -remarks



For more information about <a href="https://msdn.microsoft.com/library/windows/hardware/ff543071">event filters</a>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543071">Event Filters</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548398">GetSpecificFilterParameters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>



<a href="https://msdn.microsoft.com/fdb5059f-e7d9-4e14-aa3d-030e72c30732">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>
 

 

