---
UID: NF:dbgeng.IDebugControl3.AddAssemblyOptions
title: IDebugControl3::AddAssemblyOptions
author: windows-driver-content
description: The AddAssemblyOptions method turns on some of the assembly and disassembly options.
old-location: debugger\addassemblyoptions.htm
old-project: debugger
ms.assetid: 9274c3eb-a5c0-43a9-a9d4-541482ddace1
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: AddAssemblyOptions, AddAssemblyOptions method [Windows Debugging], AddAssemblyOptions method [Windows Debugging],IDebugControl3 interface, IDebugControl3 interface [Windows Debugging],AddAssemblyOptions method, IDebugControl3.AddAssemblyOptions, IDebugControl3::AddAssemblyOptions, IDebugControl_9cacf343-5c88-4a06-8f68-7c94b15419b8.xml, dbgeng/IDebugControl3::AddAssemblyOptions, debugger.addassemblyoptions
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
-	Dbgeng.h
api_name:
-	IDebugControl3.AddAssemblyOptions
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl3::AddAssemblyOptions


## -description


The <b>AddAssemblyOptions</b> method turns on some of the assembly and disassembly options.


## -parameters




### -param Options [in]

Specifies the assembly and disassembly options to turn on.  <i>Options</i> is a bit-set that will be combined with the existing engine options using the bitwise OR operator.  For a description of the options, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541443">DEBUG_ASMOPT_XXX</a>.


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
</table>
 

These methods can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.




## -remarks



For more information about using assembly with the <a href="https://msdn.microsoft.com/e4d53375-c82e-493b-9ccb-444c211fbc79">debugger engine API</a>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff538127">Assembling and Disassembling Instructions</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562128">.asm (Change Disassembly Options)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538121">Assemble</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541443">DEBUG_ASMOPT_XXX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541948">Disassemble</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545605">GetAssemblyOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554483">RemoveAssemblyOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556626">SetAssemblyOptions</a>
 

 

