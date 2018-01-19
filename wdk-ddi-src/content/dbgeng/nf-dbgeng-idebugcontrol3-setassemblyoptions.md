---
UID: NF:dbgeng.IDebugControl3.SetAssemblyOptions
title: IDebugControl3::SetAssemblyOptions method
author: windows-driver-content
description: The SetAssemblyOptions method sets the assembly and disassembly options that affect how the debugger engine assembles and disassembles processor instructions for the target.
old-location: debugger\setassemblyoptions.htm
old-project: debugger
ms.assetid: ec86ac71-212c-4edd-94c6-bab1cb5fa660
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugControl3, IDebugControl3::SetAssemblyOptions, SetAssemblyOptions
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
req.alt-api: IDebugControl3.SetAssemblyOptions
req.alt-loc: dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugControl3::SetAssemblyOptions method



## -description
The <b>SetAssemblyOptions</b> method sets the assembly and disassembly options that affect how the <a href="debugger.introduction#debugger_engine#debugger_engine">debugger engine</a> assembles and disassembles processor instructions for the target.



## -syntax

````
HRESULT SetAssemblyOptions(
  [in] ULONG Options
);
````


## -parameters

### -param Options [in]

Specifies the new assembly and disassembly options to be used by the <a href="debugger.introduction#debugger_engine#debugger_engine">debugger engine</a>.  <i>Options</i> is a bit-set; it will replace the existing assembly and disassembly options.  For possible values, see Remarks.  DEBUG_ASMOPT_DEFAULT can be used to set the default options.


## -returns
This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
For more information about using assembly with the debugger engine API, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff538127">Assembling and Disassembling Instructions</a>.

The assembly and disassembly options affect how the debugger engine assembles and disassembles processor instructions for the target.

The options are represented by a bitset with the following bit flags.

<b>DEBUG_ASMOPT_VERBOSE</b>

When this bit is set, additional information is included in the disassembly.

This is equivalent to the <b>verbose</b> option in the <b>.asm</b> command.

<b>DEBUG_ASMOPT_NO_CODE_BYTES</b>

When this bit is set, the raw bytes for an instruction are not included in the disassembly.

This is equivalent to the <b>no_code_bytes</b> option in the <b>.asm</b> command.

<b>DEBUG_ASMOPT_IGNORE_OUTPUT_WIDTH</b>

When this bit is set, the debugger ignores the width of the output display when formatting instructions during disassembly.

This is equivalent to the <b>ignore_output_width</b> option in the <b>.asm</b> command.

<b>DEBUG_ASMOPT_SOURCE_LINE_NUMBER</b>

When this bit is set, each line of the disassembly output is prefixed with the line number of the source code provided by symbol information.

This is equivalent to the <b>source_line</b> option in the <b>.asm</b> command.

Additionally, the value DEBUG_ASMOPT_DEFAULT represents the default set of assembly and disassembly options.  This means that all the options in the preceding table are turned off. 


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545605">GetAssemblyOptions</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537852">AddAssemblyOptions</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554483">RemoveAssemblyOptions</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff538121">Assemble</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541948">Disassemble</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562128">.asm (Change Disassembly Options)</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl3::SetAssemblyOptions method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

