---
UID: NF:dbgeng.IDebugControl4.GetEventFilterCommandWide
title: IDebugControl4::GetEventFilterCommandWide method
author: windows-driver-content
description: The GetEventFilterCommandWide method returns the debugger command that the engine will execute when a specified event occurs.
old-location: debugger\geteventfiltercommandwide.htm
old-project: debugger
ms.assetid: a565627a-4a70-4255-9a88-c39a3db11d25
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetEventFilterCommandWide method [Windows Debugging], GetEventFilterCommandWide method [Windows Debugging], IDebugControl4 interface, GetEventFilterCommandWide,IDebugControl4.GetEventFilterCommandWide, IDebugControl4, IDebugControl4 interface [Windows Debugging], GetEventFilterCommandWide method, IDebugControl4::GetEventFilterCommandWide, dbgeng/IDebugControl4::GetEventFilterCommandWide, debugger.geteventfiltercommandwide
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
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl4::GetEventFilterCommandWide method


## -description


The <b>GetEventFilterCommandWide</b>  method returns the debugger command that the engine will execute when a specified event occurs.


## -syntax


````
HRESULT GetEventFilterCommandWide(
  [in]            ULONG  Index,
  [out, optional] PWSTR  Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG CommandSize
);
````


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

<a href="..\dbgeng\nn-dbgeng-idebugcontrol4.md">IDebugControl4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556678">SetEventFilterCommand</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546653">GetExceptionFilterSecondCommand</a>



<a href="https://msdn.microsoft.com/fdb5059f-e7d9-4e14-aa3d-030e72c30732">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl4::GetEventFilterCommandWide method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

