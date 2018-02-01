---
UID: NF:dbgeng.IDebugControl3.SetLogMask
title: IDebugControl3::SetLogMask method
author: windows-driver-content
description: The SetLogMask method sets the output mask for the currently open log file.
old-location: debugger\setlogmask.htm
old-project: debugger
ms.assetid: 86c4e5ec-e893-4b1e-b397-6c51351df46c
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: SetLogMask method [Windows Debugging], IDebugControl interface, SetLogMask method [Windows Debugging], IDebugControl2 interface, dbgeng/IDebugControl3::SetLogMask, IDebugControl::SetLogMask, IDebugControl2 interface [Windows Debugging], SetLogMask method, SetLogMask method [Windows Debugging], IDebugControl3 interface, IDebugControl3, debugger.setlogmask, IDebugControl interface [Windows Debugging], SetLogMask method, IDebugControl_b1c44a2b-d2fd-407b-8994-00f5e53af10d.xml, SetLogMask method [Windows Debugging], dbgeng/IDebugControl::SetLogMask, IDebugControl3::SetLogMask, dbgeng/IDebugControl2::SetLogMask, IDebugControl2::SetLogMask, IDebugControl3 interface [Windows Debugging], SetLogMask method, SetLogMask
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugControl.SetLogMask
-	IDebugControl2.SetLogMask
-	IDebugControl3.SetLogMask
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl3::SetLogMask method


## -description


The <b>SetLogMask</b> method sets the output mask for the currently open log file.


## -syntax


````
HRESULT SetLogMask(
  [in] ULONG Mask
);
````


## -parameters




### -param Mask [in]

Specifies the new output mask for the log file.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff541518">DEBUG_OUTPUT_XXX</a> for details about this value.


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



## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547066">GetLogMask</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553155">OpenLogFile2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::SetLogMask method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

