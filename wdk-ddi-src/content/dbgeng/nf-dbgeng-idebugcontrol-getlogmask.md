---
UID: NF:dbgeng.IDebugControl.GetLogMask
title: IDebugControl::GetLogMask method
author: windows-driver-content
description: The GetLogMask method returns the output mask for the currently open log file.
old-location: debugger\getlogmask.htm
old-project: debugger
ms.assetid: 32d36b6d-9887-43ac-9314-fc682705131e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetLogMask method [Windows Debugging], GetLogMask method [Windows Debugging], IDebugControl interface, GetLogMask method [Windows Debugging], IDebugControl2 interface, GetLogMask method [Windows Debugging], IDebugControl3 interface, GetLogMask,IDebugControl.GetLogMask, IDebugControl, IDebugControl interface [Windows Debugging], GetLogMask method, IDebugControl2 interface [Windows Debugging], GetLogMask method, IDebugControl2::GetLogMask, IDebugControl3 interface [Windows Debugging], GetLogMask method, IDebugControl3::GetLogMask, IDebugControl::GetLogMask, IDebugControl_a3ef306a-5134-49c7-b589-65a4afaa90ac.xml, dbgeng/IDebugControl2::GetLogMask, dbgeng/IDebugControl3::GetLogMask, dbgeng/IDebugControl::GetLogMask, debugger.getlogmask
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
-	IDebugControl.GetLogMask
-	IDebugControl2.GetLogMask
-	IDebugControl3.GetLogMask
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl::GetLogMask method


## -description


The <b>GetLogMask</b> method returns the output mask for the currently open log file.


## -syntax


````
HRESULT GetLogMask(
  [out] PULONG Mask
);
````


## -parameters




### -param Mask [out]

Receives the output mask for the log file.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff541518">DEBUG_OUTPUT_XXX</a> for details about how to interpret this value.


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
</table>
 




## -remarks



For more information about log files, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560116">Using Input and Output</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556734">SetLogMask</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553155">OpenLogFile2</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::GetLogMask method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

