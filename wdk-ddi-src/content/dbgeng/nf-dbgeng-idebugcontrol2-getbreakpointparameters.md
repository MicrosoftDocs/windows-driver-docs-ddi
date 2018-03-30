---
UID: NF:dbgeng.IDebugControl2.GetBreakpointParameters
title: IDebugControl2::GetBreakpointParameters method
author: windows-driver-content
description: The GetBreakpointParameters method returns the parameters of one or more breakpoints.
old-location: debugger\getbreakpointparameters.htm
old-project: debugger
ms.assetid: c4426dfa-7c14-4ef0-8660-855ee24ed7fe
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetBreakpointParameters method [Windows Debugging], GetBreakpointParameters method [Windows Debugging], IDebugControl interface, GetBreakpointParameters method [Windows Debugging], IDebugControl2 interface, GetBreakpointParameters method [Windows Debugging], IDebugControl3 interface, GetBreakpointParameters,IDebugControl2.GetBreakpointParameters, IDebugControl interface [Windows Debugging], GetBreakpointParameters method, IDebugControl2, IDebugControl2 interface [Windows Debugging], GetBreakpointParameters method, IDebugControl2::GetBreakpointParameters, IDebugControl3 interface [Windows Debugging], GetBreakpointParameters method, IDebugControl3::GetBreakpointParameters, IDebugControl::GetBreakpointParameters, IDebugControl_7b2d9423-82db-4274-a1f7-eebcda92e6c3.xml, dbgeng/IDebugControl2::GetBreakpointParameters, dbgeng/IDebugControl3::GetBreakpointParameters, dbgeng/IDebugControl::GetBreakpointParameters, debugger.getbreakpointparameters
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h, Dbgeng.h, Dbgeng.h
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
-	IDebugControl.GetBreakpointParameters
-	IDebugControl2.GetBreakpointParameters
-	IDebugControl3.GetBreakpointParameters
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl2::GetBreakpointParameters method


## -description


The <b>GetBreakpointParameters</b> method returns the parameters of one or more <a href="https://msdn.microsoft.com/library/windows/hardware/ff538928">breakpoints</a>.


## -parameters




### -param Count [in]

Specifies the number of breakpoints whose parameters are being requested.


### -param Ids [in, optional]

Specifies an array containing the IDs of the breakpoints whose parameters are being requested.  The number of items in this array must be equal to the value specified in <i>Count</i>.  If <i>Ids</i> is <b>NULL</b>, <i>Start</i> is used instead.


### -param Start [in]

Specifies the beginning index of the breakpoints whose parameters are being requested.  The parameters for breakpoints with indices <i>Start</i> through <i>Start</i> plus <i>Count</i> minus one will be returned.  <i>Start</i> is used only if <i>Ids</i> is <b>NULL</b>.


### -param Params [out]

Receives the parameters for the specified breakpoints. The size of this array is equal to the value of <i>Count</i>.  For details on the structure returned, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541459">DEBUG_BREAKPOINT_PARAMETERS</a>.


## -returns



This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful. However, the parameters for some of the breakpoints were not returned.  The parameters that were not returned have their <b>Id</b> field set to DEBUG_ANY_ID.

</td>
</tr>
</table>
 




## -remarks



Some of the parameters might not be returned.  This happens if either a breakpoint could not be found or a breakpoint is private (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546791">GetFlags</a>).




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545617">GetBreakpointById</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545639">GetBreakpointByIndex</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548095">GetParameters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::GetBreakpointParameters method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
