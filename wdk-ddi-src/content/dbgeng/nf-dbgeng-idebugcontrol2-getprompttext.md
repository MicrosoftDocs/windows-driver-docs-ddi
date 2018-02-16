---
UID: NF:dbgeng.IDebugControl2.GetPromptText
title: IDebugControl2::GetPromptText method
author: windows-driver-content
description: The GetPromptText method returns the standard prompt text that will be prepended to the formatted output specified in the OutputPrompt and OutputPromptVaList methods.
old-location: debugger\getprompttext.htm
old-project: debugger
ms.assetid: 8d828cf1-991b-4c2d-882b-de56512a6737
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: dbgeng/IDebugControl::GetPromptText, IDebugControl_1f566e74-8920-43ce-8e5f-3c467ddb8d8a.xml, GetPromptText method [Windows Debugging], IDebugControl2 interface, dbgeng/IDebugControl2::GetPromptText, IDebugControl::GetPromptText, GetPromptText, GetPromptText method [Windows Debugging], IDebugControl interface, dbgeng/IDebugControl3::GetPromptText, IDebugControl2 interface [Windows Debugging], GetPromptText method, IDebugControl2::GetPromptText, IDebugControl3 interface [Windows Debugging], GetPromptText method, IDebugControl3::GetPromptText, IDebugControl interface [Windows Debugging], GetPromptText method, GetPromptText method [Windows Debugging], IDebugControl3 interface, debugger.getprompttext, IDebugControl, GetPromptText method [Windows Debugging], IDebugControl2
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
-	IDebugControl.GetPromptText
-	IDebugControl2.GetPromptText
-	IDebugControl3.GetPromptText
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugControl2::GetPromptText method


## -description


The <b>GetPromptText</b>  method returns the standard prompt text that will be prepended to the formatted output specified in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553227">OutputPrompt</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff553231">OutputPromptVaList</a> methods.


## -syntax


````
HRESULT GetPromptText(
  [out, optional] PSTR   Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG TextSize
);
````


## -parameters




### -param Buffer [out, optional]

Receives the prompt text.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize [in]

Specifies the size, in characters, of the <i>Buffer</i> buffer.


### -param TextSize [out, optional]

Receives the size, in characters, of the prompt text.  If <i>TextSize</i> is <b>NULL</b>, this information is not returned.


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
The method was successful.  However, the prompt text was too large to fit into the <i>Buffer</i> buffer and the text was truncated.

</td>
</tr>
</table>
 




## -remarks



For more information about prompting the user, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560116">Using Input and Output</a>.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553227">OutputPrompt</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553231">OutputPromptVaList</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::GetPromptText method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

