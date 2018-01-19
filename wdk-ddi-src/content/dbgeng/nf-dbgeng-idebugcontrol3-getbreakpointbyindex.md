---
UID: NF:dbgeng.IDebugControl3.GetBreakpointByIndex
title: IDebugControl3::GetBreakpointByIndex method
author: windows-driver-content
description: The GetBreakpointByIndex method returns the breakpoint located at the specified index.
old-location: debugger\getbreakpointbyindex.htm
old-project: debugger
ms.assetid: 9389536e-30c3-4651-bb1e-2c75741694b2
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugControl3, IDebugControl3::GetBreakpointByIndex, GetBreakpointByIndex
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
req.alt-api: IDebugControl.GetBreakpointByIndex,IDebugControl2.GetBreakpointByIndex,IDebugControl3.GetBreakpointByIndex
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

# IDebugControl3::GetBreakpointByIndex method



## -description
The <b>GetBreakpointByIndex</b>  method returns the breakpoint located at the specified index.



## -syntax

````
HRESULT GetBreakpointByIndex(
  [in]  ULONG             Index,
  [out] PDEBUG_BREAKPOINT *Bp
);
````


## -parameters

### -param Index [in]

Specifies the zero-based index of the breakpoint to return.  This is specific to the current process.  The value of <i>Index</i> should be between zero and the total number of breakpoints minus one. The total number of breakpoints can be determined by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff547880">GetNumberBreakpoints</a>.


### -param Bp [out]

Receives the returned breakpoint.


## -returns
This method can also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>No breakpoint was found with the given index, or the breakpoint with the given index is private.

 


## -remarks
The index and returned breakpoint are specific to the current process.  The same index will return a different breakpoint if the current process is changed.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547880">GetNumberBreakpoints</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::GetBreakpointByIndex method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

