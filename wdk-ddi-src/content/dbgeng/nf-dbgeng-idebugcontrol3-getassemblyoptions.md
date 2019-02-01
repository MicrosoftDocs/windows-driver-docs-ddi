---
UID: NF:dbgeng.IDebugControl3.GetAssemblyOptions
title: IDebugControl3::GetAssemblyOptions (dbgeng.h)
description: The GetAssemblyOptions method returns the assembly and disassembly options that affect how the debugger engine assembles and disassembles processor instructions for the target.
old-location: debugger\getassemblyoptions.htm
tech.root: debugger
ms.assetid: 8a3e82e0-4ff3-43ab-954e-a7473de51e5a
ms.date: 05/03/2018
ms.keywords: GetAssemblyOptions, GetAssemblyOptions method [Windows Debugging], GetAssemblyOptions method [Windows Debugging],IDebugControl3 interface, IDebugControl3 interface [Windows Debugging],GetAssemblyOptions method, IDebugControl3.GetAssemblyOptions, IDebugControl3::GetAssemblyOptions, IDebugControl_600ee4dc-0a79-42a9-a394-2ff053874f00.xml, dbgeng/IDebugControl3::GetAssemblyOptions, debugger.getassemblyoptions
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
-	IDebugControl3.GetAssemblyOptions
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl3::GetAssemblyOptions


## -description


The <b>GetAssemblyOptions</b> method returns the assembly and disassembly options that affect how the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a> assembles and disassembles processor instructions for the target.


## -parameters




### -param Options [out]

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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562128">.asm (Change Disassembly Options)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537852">AddAssemblyOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538121">Assemble</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541443">DEBUG_ASMOPT_XXX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541948">Disassemble</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554483">RemoveAssemblyOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556626">SetAssemblyOptions</a>
 

 

