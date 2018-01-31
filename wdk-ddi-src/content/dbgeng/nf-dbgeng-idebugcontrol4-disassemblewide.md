---
UID: NF:dbgeng.IDebugControl4.DisassembleWide
title: IDebugControl4::DisassembleWide method
author: windows-driver-content
description: The DisassembleWide method disassembles a processor instruction in the target's memory.
old-location: debugger\disassemblewide.htm
old-project: debugger
ms.assetid: 7df1f9e5-dac2-490b-9eed-28f8bc4e677a
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: debugger.disassemblewide, dbgeng/IDebugControl4::DisassembleWide, DisassembleWide, IDebugControl4 interface [Windows Debugging], DisassembleWide method, DisassembleWide method [Windows Debugging], IDebugControl4 interface, IDebugControl4, IDebugControl4::DisassembleWide, DisassembleWide method [Windows Debugging]
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
-	IDebugControl4.DisassembleWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl4::DisassembleWide method


## -description


The <b>DisassembleWide</b>  method disassembles a processor instruction in the target's memory.


## -syntax


````
HRESULT DisassembleWide(
  [in]            ULONG64  Offset,
  [in]            ULONG    Flags,
  [out, optional] PWSTR    Buffer,
  [in]            ULONG    BufferSize,
  [out, optional] PULONG   DisassemblySize,
  [out]           PULONG64 EndOffset
);
````


## -parameters




#### - Offset [in]

Specifies the location in the target's memory of the instruction to disassemble.


#### - Flags [in]

Specifies the bit-flags that affect the behavior of this method.  Currently the only flag that can be set is DEBUG_DISASM_EFFECTIVE_ADDRESS; when set, the engine will compute the effective address from the current register information and display it.


#### - Buffer [out, optional]

Receives the disassembled instruction.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


#### - BufferSize [in]

Specifies the size, in characters, of the <i>Buffer</i> buffer.


#### - DisassemblySize [out, optional]

Receives the size, in characters, of the disassembled instruction.  If <i>DisassemblySize</i> is <b>NULL</b>, this information is not returned.


#### - EndOffset [out]

Receives the location in the target's memory of the instruction following the disassembled instruction.


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
The method was successful.  However, <i>Buffer</i> was too small to hold the disassembled instruction and the instruction was truncated to fit.

</td>
</tr>
</table> 



## -remarks


The assembly language depends on the effective processor type of the target system.  For information about the assembly language, see the processor documentation.

The disassembly options--returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff545605">GetAssemblyOptions</a>--affect the operation of this method.

For an overview of using assembly in debugger applications, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540661">Debugging in Assembly Mode</a>.  For more information about using assembly with the debugger engine API, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff538127">Assembling and Disassembling Instructions</a>.



## -see-also

<a href="https://msdn.microsoft.com/933a308c-61d1-4ca4-89c1-5749ba1b41c1">u (Unassemble)</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff538121">Assemble</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol4.md">IDebugControl4</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545605">GetAssemblyOptions</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl4::DisassembleWide method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

