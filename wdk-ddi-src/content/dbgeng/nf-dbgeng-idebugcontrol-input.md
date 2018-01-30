---
UID: NF:dbgeng.IDebugControl.Input
title: IDebugControl::Input method
author: windows-driver-content
description: The Input method requests an input string from the debugger engine.
old-location: debugger\input.htm
old-project: debugger
ms.assetid: 8a37bce1-762b-4a08-a677-ed2e484c1bba
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: debugger.input, IDebugControl interface [Windows Debugging], Input method, dbgeng/IDebugControl::Input, IDebugControl_10615761-d032-439f-955b-220def3835a9.xml, IDebugControl::Input, Input method [Windows Debugging], IDebugControl, Input, Input method [Windows Debugging], IDebugControl interface
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
-	Dbgeng.h
apiname:
-	IDebugControl.Input
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl::Input method


## -description


The <b>Input</b>  method requests an input string from the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a>.


## -syntax


````
HRESULT Input(
  [out]           PSTR   Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG InputSize
);
````


## -parameters




### -param Buffer [out]

Receives the input string from the engine.


### -param BufferSize [in]

Specifies the size, in characters, of the buffer that <i>Buffer</i> specifies.


### -param InputSize [out, optional]

Receives the number of characters returned in <i>Buffer</i>.  If <i>InputSize</i> is <b>NULL</b>, this information is not returned.


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
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful. However, the buffer was not big enough to hold the whole input string and it was truncated.

</td>
</tr>
</table> 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.



## -remarks


For an overview of input in the debugger engine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550971">Input and Output</a>.



## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550970">InputWide</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::Input method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

