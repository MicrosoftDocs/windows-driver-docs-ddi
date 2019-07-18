---
UID: NN:dbgeng.IDebugControl
title: IDebugControl (dbgeng.h)
description: IDebugControl interface
old-location: debugger\idebugcontrol.htm
tech.root: debugger
ms.assetid: 6ff5b9ff-d2b8-4ade-8b8b-20284efdf266
ms.date: 05/03/2018
ms.keywords: IDebugControl, IDebugControl interface [Windows Debugging], IDebugControl interface [Windows Debugging],described, IDebugControl_ce0030b2-73a7-49a8-9d21-942922a69184.xml, dbgeng/IDebugControl, debugger.idebugcontrol
ms.topic: interface
f1_keywords:
 - "dbgeng/IDebugControl"
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugControl
- IDebugControl.GetWindbgExtensionApis32
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugControl</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IDebugControl</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugControl</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-addbreakpoint">AddBreakpoint</a>
</td>
<td align="left" width="63%">
Creates a new breakpoint for the current target.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-addengineoptions">AddEngineOptions</a>
</td>
<td align="left" width="63%">
 Turns on some of the debugger engine's options.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-addextension">AddExtension</a>
</td>
<td align="left" width="63%">
Loads an extension library into the debugger engine.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-assemble">Assemble</a>
</td>
<td align="left" width="63%">
Assembles a single processor instruction. The assembled instruction is placed in the target's memory.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-callextension">CallExtension</a>
</td>
<td align="left" width="63%">
Calls a debugger extension.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-closelogfile">CloseLogFile</a>
</td>
<td align="left" width="63%">
Closes the currently-open log file.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-coercevalue">CoerceValue</a>
</td>
<td align="left" width="63%">
Converts a value of one type into a value of another type.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-coercevalues">CoerceValues</a>
</td>
<td align="left" width="63%">
Converts an array of values into an array of values of different types.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539248">ControlledOutput</a>
</td>
<td align="left" width="63%">
Formats a string and sends the result to output callbacks that were registered with some of the engine's clients.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-controlledoutputvalist">ControlledOutputVaList</a>
</td>
<td align="left" width="63%">
Formats a string and sends the result to output callbacks that were registered with some of the engine's clients.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-disassemble">Disassemble</a>
</td>
<td align="left" width="63%">
Disassembles a processor instruction in the target's memory.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-evaluate">Evaluate</a>
</td>
<td align="left" width="63%">
Evaluates an expression, returning the result.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-execute">Execute</a>
</td>
<td align="left" width="63%">
Executes the specified debugger commands.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-executecommandfile">ExecuteCommandFile</a>
</td>
<td align="left" width="63%">
Opens the specified file and executes the debugger commands that are contained within.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getactualprocessortype">GetActualProcessorType</a>
</td>
<td align="left" width="63%">
Returns the processor type of the physical processor of the computer that is running the target.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getbreakpointbyid">GetBreakpointById</a>
</td>
<td align="left" width="63%">
Returns the breakpoint with the specified breakpoint ID.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getbreakpointbyindex">GetBreakpointByIndex</a>
</td>
<td align="left" width="63%">
Returns the breakpoint located at the specified index.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getbreakpointparameters">GetBreakpointParameters</a>
</td>
<td align="left" width="63%">
Returns the parameters of one or more breakpoints.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getcodelevel">GetCodeLevel</a>
</td>
<td align="left" width="63%">
Returns the current code level and is mainly used when stepping through code.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getdebuggeetype">GetDebuggeeType</a>
</td>
<td align="left" width="63%">
Describes the nature of the current target.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getdisassembleeffectiveoffset">GetDisassembleEffectiveOffset</a>
</td>
<td align="left" width="63%">
Returns the address of the last instruction disassembled using Disassemble.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-geteffectiveprocessortype">GetEffectiveProcessorType</a>
</td>
<td align="left" width="63%">
Returns the effective processor type of the processor of the computer that is running the target.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getengineoptions">GetEngineOptions</a>
</td>
<td align="left" width="63%">
Returns the engine's options.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-geteventfiltercommand">GetEventFilterCommand</a>
</td>
<td align="left" width="63%">
Returns the debugger command that the engine will execute when a specified event occurs.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-geteventfiltertext">GetEventFilterText</a>
</td>
<td align="left" width="63%">
Returns a short description of an event for a specific filter.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getexceptionfilterparameters">GetExceptionFilterParameters</a>
</td>
<td align="left" width="63%">
Returns the parameters for exception filters specified by exception codes or by index.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getexceptionfiltersecondcommand">GetExceptionFilterSecondCommand</a>
</td>
<td align="left" width="63%">
Returns the command that will be executed by the debugger engine upon the second chance of a specified exception.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getexecutingprocessortype">GetExecutingProcessorType</a>
</td>
<td align="left" width="63%">
Returns the executing processor type for the processor for which the last event occurred.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getexecutionstatus">GetExecutionStatus</a>
</td>
<td align="left" width="63%">
Returns information about the execution status of the debugger engine.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getextensionbypath">GetExtensionByPath</a>
</td>
<td align="left" width="63%">
Returns the handle for an already loaded extension library.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getextensionfunction">GetExtensionFunction</a>
</td>
<td align="left" width="63%">
Returns a pointer to an extension function from an extension library.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getinterrupt">GetInterrupt</a>
</td>
<td align="left" width="63%">
Checks whether a user interrupt was issued.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getinterrupttimeout">GetInterruptTimeout</a>
</td>
<td align="left" width="63%">
Returns the number of seconds that the engine will wait when requesting a break into the debugger.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getlasteventinformation">GetLastEventInformation</a>
</td>
<td align="left" width="63%">
Returns information about the last event that occurred in a target.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getlogfile">GetLogFile</a>
</td>
<td align="left" width="63%">
Returns the name of the currently open log file.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getlogmask">GetLogMask</a>
</td>
<td align="left" width="63%">
Returns the output mask for the currently open log file.

HRESULT



</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getnearinstruction">GetNearInstruction</a>
</td>
<td align="left" width="63%">
Returns the location of a processor instruction relative to a given location.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getnotifyeventhandle">GetNotifyEventHandle</a>
</td>
<td align="left" width="63%">
Receives the handle of the event that will be signaled after the next exception in a target.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getnumberbreakpoints">GetNumberBreakpoints</a>
</td>
<td align="left" width="63%">
Returns the number of breakpoints for the current process.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getnumbereventfilters">GetNumberEventFilters</a>
</td>
<td align="left" width="63%">
Returns the number of event filters currently used by the engine.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getnumberpossibleexecutingprocessortypes">GetNumberPossibleExecutingProcessorTypes</a>
</td>
<td align="left" width="63%">
Returns the number of processor types that are supported by the computer running the current target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getnumberprocessors">GetNumberProcessors</a>
</td>
<td align="left" width="63%">
Returns the number of processors on the computer running the current target.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getnumbersupportedprocessortypes">GetNumberSupportedProcessorTypes</a>
</td>
<td align="left" width="63%">
Returns the number of processor types supported by the engine.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getpagesize">GetPageSize</a>
</td>
<td align="left" width="63%">
Returns the page size for the effective processor mode.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getpossibleexecutingprocessortypes">GetPossibleExecutingProcessorTypes</a>
</td>
<td align="left" width="63%">
Returns the processor types that are supported by the computer running the current target.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getprocessortypenames">GetProcessorTypeNames</a>
</td>
<td align="left" width="63%">
Returns the full name and abbreviated name of the specified processor type.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getprompttext">GetPromptText</a>
</td>
<td align="left" width="63%">
Returns the standard prompt text that will be prepended to the formatted output specified in the <b>OutputPrompt</b> and <b>OutputPromptVaList</b> methods.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getradix">GetRadix</a>
</td>
<td align="left" width="63%">
Returns the default radix (number base) used by the debugger engine when it evaluates and displays MASM expressions, and when it displays symbol information.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getreturnoffset">GetReturnOffset</a>
</td>
<td align="left" width="63%">
 Returns the return address for the current function.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getspecificfilterargument">GetSpecificFilterArgument</a>
</td>
<td align="left" width="63%">
Returns the value of filter argument for thespecific filters that have an argument.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getspecificfilterparameters">GetSpecificFilterParameters</a>
</td>
<td align="left" width="63%">
Returns the parameters for specific event filters.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getstacktrace">GetStackTrace</a>
</td>
<td align="left" width="63%">
Returns the frames at the top of the specified call stack.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getsupportedprocessortypes">GetSupportedProcessorTypes</a>
</td>
<td align="left" width="63%">
Returns the processor types supported by the debugger engine. 


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getsystemerrorcontrol">GetSystemErrorControl</a>
</td>
<td align="left" width="63%">
Returns the control values for handling system errors.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getsystemversion">GetSystemVersion</a>
</td>
<td align="left" width="63%">
Returns information that identifies the operating system on the computer that is running the current target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-gettextmacro">GetTextMacro</a>
</td>
<td align="left" width="63%">
Returns the value of a fixed-name alias.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>GetWindbgExtensionApis32</b></td>
<td align="left" width="63%">


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getwindbgextensionapis64">GetWindbgExtensionApis64</a>
</td>
<td align="left" width="63%">
returns a structure that facilitates using the WdbgExts API.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol-input">Input</a>
</td>
<td align="left" width="63%">
Requests an input string from the debugger engine.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-ispointer64bit">IsPointer64Bit</a>
</td>
<td align="left" width="63%">
Determines if the effective processor uses 64-bit pointers.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-openlogfile">OpenLogFile</a>
</td>
<td align="left" width="63%">
Opens a log file that will receive output from the client objects.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553183">Output</a>
</td>
<td align="left" width="63%">
Formats a string and sends the result to output callbacks that have been registered with the engine's clients.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-outputcurrentstate">OutputCurrentState</a>
</td>
<td align="left" width="63%">
Prints the current state of the current target to the debugger console.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-outputdisassembly">OutputDisassembly</a>
</td>
<td align="left" width="63%">
Disassembles a processor instruction and sends the disassembly to the output callbacks.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-outputdisassemblylines">OutputDisassemblyLines</a>
</td>
<td align="left" width="63%">
Disassembles several processor instructions and sends the resulting assembly instructions to the output callbacks.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553227">OutputPrompt</a>
</td>
<td align="left" width="63%">
 Formats and sends a user prompt to the output callback objects.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-outputpromptvalist">OutputPromptVaList</a>
</td>
<td align="left" width="63%">
Formats and sends a user prompt to the output callback objects.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-outputstacktrace">OutputStackTrace</a>
</td>
<td align="left" width="63%">
Outputs either the supplied stack frame or the current stack frames.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-outputvalist">OutputVaList</a>
</td>
<td align="left" width="63%">
 Formats a string and sends the result to the output callbacks that are registered with the engine's clients.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-outputversioninformation">OutputVersionInformation</a>
</td>
<td align="left" width="63%">
Prints version information about the debugger engine to the debugger console.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-readbugcheckdata">ReadBugCheckData</a>
</td>
<td align="left" width="63%">
Reads the kernel bug check code and related parameters.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-removebreakpoint">RemoveBreakpoint</a>
</td>
<td align="left" width="63%">
Removes a breakpoint.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-removeengineoptions">RemoveEngineOptions</a>
</td>
<td align="left" width="63%">
Turns off some of the engine's options.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-removeextension">RemoveExtension</a>
</td>
<td align="left" width="63%">
Unloads an extension library.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-returninput">ReturnInput</a>
</td>
<td align="left" width="63%">
This method is used by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebuginputcallbacks">IDebugInputCallbacks</a> objects to send an input string to the engine following a request for input.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-setcodelevel">SetCodeLevel</a>
</td>
<td align="left" width="63%">
Sets the current code level and is mainly used when stepping through code.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-seteffectiveprocessortype">SetEffectiveProcessorType</a>
</td>
<td align="left" width="63%">
Sets the effective processor type of the processor of the computer that is running the target.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-setengineoptions">SetEngineOptions</a>
</td>
<td align="left" width="63%">
Changes the engine's options.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-seteventfiltercommand">SetEventFilterCommand</a>
</td>
<td align="left" width="63%">
Sets a debugger command for the engine to execute when a specified event occurs.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-setexceptionfilterparameters">SetExceptionFilterParameters</a>
</td>
<td align="left" width="63%">
Changes the break status and handling status for some exception filters.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-setexceptionfiltersecondcommand">SetExceptionFilterSecondCommand</a>
</td>
<td align="left" width="63%">
Sets the command that will be executed by the debugger engine on the second chance of a specified exception.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-setexecutionstatus">SetExecutionStatus</a>
</td>
<td align="left" width="63%">
Requests that the debugger engine enter an executable state. Actual execution will not occur until the next time <b>WaitForEvent</b> is called.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-setinterrupt">SetInterrupt</a>
</td>
<td align="left" width="63%">
Registers a user interrupt or breaks into the debugger.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-setinterrupttimeout">SetInterruptTimeout</a>
</td>
<td align="left" width="63%">
Sets the number of seconds that the debugger engine should wait when requesting a break into the debugger.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-setlogmask">SetLogMask</a>
</td>
<td align="left" width="63%">
Sets the output mask for the currently open log file.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-setnotifyeventhandle">SetNotifyEventHandle</a>
</td>
<td align="left" width="63%">
Sets the event that will be signaled after the next exception in a target.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-setradix">SetRadix</a>
</td>
<td align="left" width="63%">
Sets the default radix (number base) used by the debugger engine when it evaluates and displays MASM expressions, and when it displays symbol information.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-setspecificfilterargument">SetSpecificFilterArgument</a>
</td>
<td align="left" width="63%">
Sets the value of filter argument for the specific filters that can have an argument.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-setspecificfilterparameters">SetSpecificFilterParameters</a>
</td>
<td align="left" width="63%">
Changes the break status and handling status for some specific event filters.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-setsystemerrorcontrol">SetSystemErrorControl</a>
</td>
<td align="left" width="63%">
Sets the control values for handling system errors.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-settextmacro">SetTextMacro</a>
</td>
<td align="left" width="63%">
Sets the value of a fixed-name alias.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-waitforevent">WaitForEvent</a>
</td>
<td align="left" width="63%">
Waits for an event that breaks into the debugger engine application.


</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol4">IDebugControl4</a>
 

 

