---
UID: NF:dbgeng.IDebugControl3.GetAssemblyOptions
title: IDebugControl3::GetAssemblyOptions method
author: windows-driver-content
description: The GetAssemblyOptions method returns the assembly and disassembly options that affect how the debugger engine assembles and disassembles processor instructions for the target.
old-location: debugger\getassemblyoptions.htm
old-project: debugger
ms.assetid: 8a3e82e0-4ff3-43ab-954e-a7473de51e5a
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugControl3, dbgeng/IDebugControl3::GetAssemblyOptions, debugger.getassemblyoptions, GetAssemblyOptions method [Windows Debugging], IDebugControl3 interface, GetAssemblyOptions method [Windows Debugging], IDebugControl_600ee4dc-0a79-42a9-a394-2ff053874f00.xml, IDebugControl3 interface [Windows Debugging], GetAssemblyOptions method, IDebugControl3::GetAssemblyOptions, GetAssemblyOptions
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
-	IDebugControl3.GetAssemblyOptions
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl3::GetAssemblyOptions method


## -description


The <b>GetAssemblyOptions</b> method returns the assembly and disassembly options that affect how the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a> assembles and disassembles processor instructions for the target.


## -syntax


````
HRESULT GetAssemblyOptions(
  [out] PULONG Options
);
````


## -parameters




#### - Options [out]

Receives a bit-set that contains the assembly and disassembly options.  For a description of these options, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541443">DEBUG_ASMOPT_XXX</a>.


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


For more information about using assembly with the debugger engine API, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff538127">Assembling and Disassembling Instructions</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff538121">Assemble</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556626">SetAssemblyOptions</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541443">DEBUG_ASMOPT_XXX</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff562128">.asm (Change Disassembly Options)</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541948">Disassemble</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554483">RemoveAssemblyOptions</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537852">AddAssemblyOptions</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl3::GetAssemblyOptions method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

