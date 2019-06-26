---
UID: NN:dbgeng.IDebugControl4
title: IDebugControl4 (dbgeng.h)
description: IDebugControl4 interface
old-location: debugger\idebugcontrol4.htm
tech.root: debugger
ms.assetid: 693207c2-70d7-45be-ae22-436555225928
ms.date: 05/03/2018
ms.keywords: IDebugControl4, IDebugControl4 interface [Windows Debugging], IDebugControl4 interface [Windows Debugging],described, dbgeng/IDebugControl4, debugger.idebugcontrol4
ms.topic: interface
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
- IDebugControl4
- IDebugControl4.GetManagedStatus
- IDebugControl4.GetManagedStatusWide
- IDebugControl4.ResetManagedStatus
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl4 interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugControl4</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>. <b>IDebugControl4</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugControl4</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-addbreakpoint2">AddBreakpoint2</a>
</td>
<td align="left" width="63%">
Creates a new breakpoint for the current target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-addextensionwide">AddExtensionWide</a>
</td>
<td align="left" width="63%">
Loads an extension library into the debugger engine.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-assemblewide">AssembleWide</a>
</td>
<td align="left" width="63%">
Assembles a single processor instruction.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-callextensionwide">CallExtensionWide</a>
</td>
<td align="left" width="63%">
Calls a debugger extension.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-controlledoutputvalistwide">ControlledOutputVaListWide</a>
</td>
<td align="left" width="63%">
Formats a string and sends the result to output callbacks that were registered with some of the engine's clients.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539266">ControlledOutputWide</a>
</td>
<td align="left" width="63%">
Formats a string and sends the result to output callbacks that were registered with some of the engine's clients.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-disassemblewide">DisassembleWide</a>
</td>
<td align="left" width="63%">
Disassembles a processor instruction in the target's memory.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-evaluatewide">EvaluateWide</a>
</td>
<td align="left" width="63%">
Evaluates an expression, returning the result.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-executecommandfilewide">ExecuteCommandFileWide</a>
</td>
<td align="left" width="63%">
Opens the specified file and executes the debugger commands that are contained within.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-executewide">ExecuteWide</a>
</td>
<td align="left" width="63%">
Executes the specified debugger commands.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-getbreakpointbyid2">GetBreakpointById2</a>
</td>
<td align="left" width="63%">
Returns the breakpoint with the specified breakpoint ID.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-getbreakpointbyindex2">GetBreakpointByIndex2</a>
</td>
<td align="left" width="63%">
Returns the breakpoint located at the specified index.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-getcontextstacktrace">GetContextStackTrace</a>
</td>
<td align="left" width="63%">
Returns the frames at the top of the call stack, starting with an arbitrary register context and returning the reconstructed register context for each stack frame.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-geteventfiltercommandwide">GetEventFilterCommandWide</a>
</td>
<td align="left" width="63%">
Returns the debugger command that the engine will execute when a specified event occurs.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-geteventfiltertextwide">GetEventFilterTextWide</a>
</td>
<td align="left" width="63%">
Returns a short description of an event for a specific filter.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-geteventindexdescriptionwide">GetEventIndexDescriptionWide</a>
</td>
<td align="left" width="63%">
Describes the specified event in a static list of events for the current target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-getexceptionfiltersecondcommand">GetExceptionFilterSecondCommandWide</a>
</td>
<td align="left" width="63%">
Returns the command that will be executed by the debugger engine upon the second chance of a specified exception.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-getexpressionsyntaxnameswide">GetExpressionSyntaxNamesWide</a>
</td>
<td align="left" width="63%">
Returns the full and abbreviated names of an expression syntax.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-getextensionbypathwide">GetExtensionByPathWide</a>
</td>
<td align="left" width="63%">
Returns the handle for an already loaded extension library.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-getextensionfunctionwide">GetExtensionFunctionWide</a>
</td>
<td align="left" width="63%">
Returns a pointer to an extension function from an extension library.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-getlasteventinformationwide">GetLastEventInformationWide</a>
</td>
<td align="left" width="63%">
Returns information about the last event that occurred in a target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-getlogfile2">GetLogFile2</a>
</td>
<td align="left" width="63%">
Returns the name of the currently open log file.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-getlogfile2wide">GetLogFile2Wide</a>
</td>
<td align="left" width="63%">
Returns the name of the currently open log file.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-getlogfilewide">GetLogFileWide</a>
</td>
<td align="left" width="63%">
Returns the name of the currently open log file.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>GetManagedStatus</b></td>
<td align="left" width="63%">


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>GetManagedStatusWide</b></td>
<td align="left" width="63%">


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-getprocessortypenameswide">GetProcessorTypeNamesWide</a>
</td>
<td align="left" width="63%">
Returns the full name and abbreviated name of the specified processor type.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-getprompttextwide">GetPromptTextWide</a>
</td>
<td align="left" width="63%">
 Returns the standard prompt text that will be prepended to the formatted output specified in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553227">OutputPrompt</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-outputpromptvalist">OutputPromptVaList</a> methods.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-getspecificfilterargumentwide">GetSpecificFilterArgumentWide</a>
</td>
<td align="left" width="63%">
Returns the value of filter argument for the specific filters that have an argument.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-getstoredeventinformation">GetStoredEventInformation</a>
</td>
<td align="left" width="63%">
 Retrieves information about an event of interest available in the current target.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-getsystemversionstring">GetSystemVersionString</a>
</td>
<td align="left" width="63%">
Returns a string that describes the target's operating system version.
(ANSI version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-getsystemversionstringwide">GetSystemVersionStringWide</a>
</td>
<td align="left" width="63%">
Returns a string that describes the target's operating system version.
(Unicode version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-getsystemversionvalues">GetSystemVersionValues</a>
</td>
<td align="left" width="63%">
Returns version number information for the current target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-gettextmacrowide">GetTextMacroWide</a>
</td>
<td align="left" width="63%">
Returns the value of a fixed-name alias.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-gettextreplacementwide">GetTextReplacementWide</a>
</td>
<td align="left" width="63%">
Returns the value of a user-named alias or an automatic alias.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-inputwide">InputWide</a>
</td>
<td align="left" width="63%">
Requests an input string from the debugger engine.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-openlogfile2">OpenLogFile2</a>
</td>
<td align="left" width="63%">
Opens a log file that will receive output from the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/client-objects">client objects</a>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-openlogfile2wide">OpenLogFile2Wide</a>
</td>
<td align="left" width="63%">
Opens a log file that will receive output from the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/client-objects">client objects</a>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-openlogfilewide">OpenLogFileWide</a>
</td>
<td align="left" width="63%">
Opens a log file that will receive output from the client objects.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-outputcontextstacktrace">OutputContextStackTrace</a>
</td>
<td align="left" width="63%">
Prints the call stack specified by an array of stack frames and corresponding register contexts.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-outputpromptvalistwide">OutputPromptVaListWide</a>
</td>
<td align="left" width="63%">
Formats and sends a user prompt to the output callback objects.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553240">OutputPromptWide</a>
</td>
<td align="left" width="63%">
 Formats and sends a user prompt to the output callback objects.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-outputvalistwide">OutputVaListWide</a>
</td>
<td align="left" width="63%">
Formats a string and sends the result to the output callbacks that are registered with the engine's clients.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553294">OutputWide</a>
</td>
<td align="left" width="63%">
 Formats a string and send the result to output callbacks that have been registered with the engine's clients.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-removebreakpoint2">RemoveBreakpoint2</a>
</td>
<td align="left" width="63%">
Removes a breakpoint.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>ResetManagedStatus</b></td>
<td align="left" width="63%">


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-returninputwide">ReturnInputWide</a>
</td>
<td align="left" width="63%">
This method is used by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebuginputcallbacks">IDebugInputCallbacks</a> objects to send an input string to the engine following a request for input.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-seteventfiltercommandwide">SetEventFilterCommandWide</a>
</td>
<td align="left" width="63%">
Sets a debugger command for the engine to execute when a specified event occurs.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-setexceptionfiltersecondcommandwide">SetExceptionFilterSecondCommandWide</a>
</td>
<td align="left" width="63%">
Sets the command that will be executed by the debugger engine on the second chance of a specified exception.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-setexpressionsyntaxbynamewide">SetExpressionSyntaxByNameWide</a>
</td>
<td align="left" width="63%">
Sets the syntax that the engine will use to evaluate expressions.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-setspecificfilterargumentwide">SetSpecificFilterArgumentWide</a>
</td>
<td align="left" width="63%">
Sets the value of filter argument for the specific filters that can have an argument.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-settextmacrowide">SetTextMacroWide</a>
</td>
<td align="left" width="63%">
Sets the value of a fixed-name alias.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-settextreplacementwide">SetTextReplacementWide</a>
</td>
<td align="left" width="63%">
Sets the value of a user-named alias.

</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>
 

 

