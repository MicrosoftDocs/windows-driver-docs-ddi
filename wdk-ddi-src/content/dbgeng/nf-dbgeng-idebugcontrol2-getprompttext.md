---
UID: NF:dbgeng.IDebugControl2.GetPromptText
title: IDebugControl2::GetPromptText
description: The GetPromptText method returns the standard prompt text that will be prepended to the formatted output specified in the OutputPrompt and OutputPromptVaList methods.
old-location: debugger\getprompttext.htm
tech.root: debugger
ms.assetid: 8d828cf1-991b-4c2d-882b-de56512a6737
ms.date: 05/03/2018
ms.keywords: GetPromptText, GetPromptText method [Windows Debugging], GetPromptText method [Windows Debugging],IDebugControl interface, GetPromptText method [Windows Debugging],IDebugControl2 interface, GetPromptText method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetPromptText method, IDebugControl2 interface [Windows Debugging],GetPromptText method, IDebugControl2.GetPromptText, IDebugControl2::GetPromptText, IDebugControl3 interface [Windows Debugging],GetPromptText method, IDebugControl3::GetPromptText, IDebugControl::GetPromptText, IDebugControl_1f566e74-8920-43ce-8e5f-3c467ddb8d8a.xml, dbgeng/IDebugControl2::GetPromptText, dbgeng/IDebugControl3::GetPromptText, dbgeng/IDebugControl::GetPromptText, debugger.getprompttext
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
-	IDebugControl.GetPromptText
-	IDebugControl2.GetPromptText
-	IDebugControl3.GetPromptText
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl2::GetPromptText


## -description


The <b>GetPromptText</b>  method returns the standard prompt text that will be prepended to the formatted output specified in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553227">OutputPrompt</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff553231">OutputPromptVaList</a> methods.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553227">OutputPrompt</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553231">OutputPromptVaList</a>
 

 

