---
UID: NF:dbgeng.IDebugControl3.AddAssemblyOptions
title: IDebugControl3::AddAssemblyOptions method
author: windows-driver-content
description: The AddAssemblyOptions method turns on some of the assembly and disassembly options.
old-location: debugger\addassemblyoptions.htm
old-project: debugger
ms.assetid: 9274c3eb-a5c0-43a9-a9d4-541482ddace1
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., 3, :, A, AddAssemblyOptions method [Windows Debugging], AddAssemblyOptions method [Windows Debugging], IDebugControl3 interface, AddAssemblyOptions,IDebugControl3.AddAssemblyOptions, C, D, I, IDebugControl3, IDebugControl3 interface [Windows Debugging], AddAssemblyOptions method, IDebugControl3::AddAssemblyOptions, IDebugControl_9cacf343-5c88-4a06-8f68-7c94b15419b8.xml, O, b, d, dbgeng/IDebugControl3::AddAssemblyOptions, debugger.addassemblyoptions, e, g, i, l, m, n, o, p, r, s, t, u, y"
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
-	IDebugControl3.AddAssemblyOptions
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl3::AddAssemblyOptions method


## -description


The <b>AddAssemblyOptions</b> method turns on some of the assembly and disassembly options.


## -syntax


````
HRESULT AddAssemblyOptions(
  [in] ULONG Options
);
````


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

<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538121">Assemble</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554483">RemoveAssemblyOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541443">DEBUG_ASMOPT_XXX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541948">Disassemble</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545605">GetAssemblyOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562128">.asm (Change Disassembly Options)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556626">SetAssemblyOptions</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl3::AddAssemblyOptions method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

