---
UID: NN:dbgeng.IDebugControl4
title: IDebugControl4
author: windows-driver-content
description: IDebugControl4 interface
old-location: debugger\idebugcontrol4.htm
old-project: Debugger
ms.assetid: 693207c2-70d7-45be-ae22-436555225928
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: debugger.idebugcontrol4, IDebugControl4 interface [Windows Debugging], IDebugControl4 interface [Windows Debugging], described, IDebugControl4, dbgeng/IDebugControl4
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	IDebugControl4
-	IDebugControl4.GetManagedStatus
-	IDebugControl4.GetManagedStatusWide
-	IDebugControl4.ResetManagedStatus
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl4 interface


## -description




## -members

The <b>IDebugControl4</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537859">AddBreakpoint2</a>
</td>
<td align="left" width="63%">
Creates a new breakpoint for the current target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537896">AddExtensionWide</a>
</td>
<td align="left" width="63%">
Loads an extension library into the debugger engine.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff538126">AssembleWide</a>
</td>
<td align="left" width="63%">
Assembles a single processor instruction.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539031">CallExtensionWide</a>
</td>
<td align="left" width="63%">
Calls a debugger extension.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539259">ControlledOutputVaListWide</a>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541951">DisassembleWide</a>
</td>
<td align="left" width="63%">
Disassembles a processor instruction in the target's memory.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543055">EvaluateWide</a>
</td>
<td align="left" width="63%">
Evaluates an expression, returning the result.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543223">ExecuteCommandFileWide</a>
</td>
<td align="left" width="63%">
Opens the specified file and executes the debugger commands that are contained within.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543237">ExecuteWide</a>
</td>
<td align="left" width="63%">
Executes the specified debugger commands.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545631">GetBreakpointById2</a>
</td>
<td align="left" width="63%">
Returns the breakpoint with the specified breakpoint ID.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545645">GetBreakpointByIndex2</a>
</td>
<td align="left" width="63%">
Returns the breakpoint located at the specified index.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545748">GetContextStackTrace</a>
</td>
<td align="left" width="63%">
Returns the frames at the top of the call stack, starting with an arbitrary register context and returning the reconstructed register context for each stack frame.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546615">GetEventFilterCommandWide</a>
</td>
<td align="left" width="63%">
Returns the debugger command that the engine will execute when a specified event occurs.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546624">GetEventFilterTextWide</a>
</td>
<td align="left" width="63%">
Returns a short description of an event for a specific filter.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546635">GetEventIndexDescriptionWide</a>
</td>
<td align="left" width="63%">
Describes the specified event in a static list of events for the current target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/17a61847-78b7-45b8-b02b-3ba4cdba6bff">GetExceptionFilterSecondCommandWide</a>
</td>
<td align="left" width="63%">
Returns the command that will be executed by the debugger engine upon the second chance of a specified exception.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546711">GetExpressionSyntaxNamesWide</a>
</td>
<td align="left" width="63%">
Returns the full and abbreviated names of an expression syntax.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546723">GetExtensionByPathWide</a>
</td>
<td align="left" width="63%">
Returns the handle for an already loaded extension library.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546739">GetExtensionFunctionWide</a>
</td>
<td align="left" width="63%">
Returns a pointer to an extension function from an extension library.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546989">GetLastEventInformationWide</a>
</td>
<td align="left" width="63%">
Returns information about the last event that occurred in a target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547025">GetLogFile2</a>
</td>
<td align="left" width="63%">
Returns the name of the currently open log file.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547034">GetLogFile2Wide</a>
</td>
<td align="left" width="63%">
Returns the name of the currently open log file.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547050">GetLogFileWide</a>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548177">GetProcessorTypeNamesWide</a>
</td>
<td align="left" width="63%">
Returns the full name and abbreviated name of the specified processor type.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548186">GetPromptTextWide</a>
</td>
<td align="left" width="63%">
 Returns the standard prompt text that will be prepended to the formatted output specified in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553227">OutputPrompt</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff553231">OutputPromptVaList</a> methods.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548392">GetSpecificFilterArgumentWide</a>
</td>
<td align="left" width="63%">
Returns the value of filter argument for the specific filters that have an argument.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548431">GetStoredEventInformation</a>
</td>
<td align="left" width="63%">
 Retrieves information about an event of interest available in the current target.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549245">GetSystemVersionString</a>
</td>
<td align="left" width="63%">
Returns a string that describes the target's operating system version.
(ANSI version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549256">GetSystemVersionStringWide</a>
</td>
<td align="left" width="63%">
Returns a string that describes the target's operating system version.
(Unicode version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549258">GetSystemVersionValues</a>
</td>
<td align="left" width="63%">
Returns version number information for the current target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549275">GetTextMacroWide</a>
</td>
<td align="left" width="63%">
Returns the value of a fixed-name alias.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549290">GetTextReplacementWide</a>
</td>
<td align="left" width="63%">
Returns the value of a user-named alias or an automatic alias.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550970">InputWide</a>
</td>
<td align="left" width="63%">
Requests an input string from the debugger engine.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553155">OpenLogFile2</a>
</td>
<td align="left" width="63%">
Opens a log file that will receive output from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539140">client objects</a>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553159">OpenLogFile2Wide</a>
</td>
<td align="left" width="63%">
Opens a log file that will receive output from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539140">client objects</a>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553162">OpenLogFileWide</a>
</td>
<td align="left" width="63%">
Opens a log file that will receive output from the client objects.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553203">OutputContextStackTrace</a>
</td>
<td align="left" width="63%">
Prints the call stack specified by an array of stack frames and corresponding register contexts.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553234">OutputPromptVaListWide</a>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553283">OutputVaListWide</a>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554488">RemoveBreakpoint2</a>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554605">ReturnInputWide</a>
</td>
<td align="left" width="63%">
This method is used by <a href="..\dbgeng\nn-dbgeng-idebuginputcallbacks.md">IDebugInputCallbacks</a> objects to send an input string to the engine following a request for input.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556681">SetEventFilterCommandWide</a>
</td>
<td align="left" width="63%">
Sets a debugger command for the engine to execute when a specified event occurs.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556691">SetExceptionFilterSecondCommandWide</a>
</td>
<td align="left" width="63%">
Sets the command that will be executed by the debugger engine on the second chance of a specified exception.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556700">SetExpressionSyntaxByNameWide</a>
</td>
<td align="left" width="63%">
Sets the syntax that the engine will use to evaluate expressions.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556793">SetSpecificFilterArgumentWide</a>
</td>
<td align="left" width="63%">
Sets the value of filter argument for the specific filters that can have an argument.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556814">SetTextMacroWide</a>
</td>
<td align="left" width="63%">
Sets the value of a fixed-name alias.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556823">SetTextReplacementWide</a>
</td>
<td align="left" width="63%">
Sets the value of a user-named alias.

</td>
</tr>
</table>Creates a new breakpoint for the current target.

Loads an extension library into the debugger engine.

Assembles a single processor instruction.

Calls a debugger extension.

Formats a string and sends the result to output callbacks that were registered with some of the engine's clients.

Formats a string and sends the result to output callbacks that were registered with some of the engine's clients.

Disassembles a processor instruction in the target's memory.

Evaluates an expression, returning the result.

Opens the specified file and executes the debugger commands that are contained within.

Executes the specified debugger commands.

Returns the breakpoint with the specified breakpoint ID.

Returns the breakpoint located at the specified index.

Returns the frames at the top of the call stack, starting with an arbitrary register context and returning the reconstructed register context for each stack frame.


Returns the debugger command that the engine will execute when a specified event occurs.

Returns a short description of an event for a specific filter.

Describes the specified event in a static list of events for the current target.

Returns the command that will be executed by the debugger engine upon the second chance of a specified exception.

Returns the full and abbreviated names of an expression syntax.

Returns the handle for an already loaded extension library.

Returns a pointer to an extension function from an extension library.

Returns information about the last event that occurred in a target.

Returns the name of the currently open log file.

Returns the name of the currently open log file.

Returns the name of the currently open log file.





Returns the full name and abbreviated name of the specified processor type.

 Returns the standard prompt text that will be prepended to the formatted output specified in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553227">OutputPrompt</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff553231">OutputPromptVaList</a> methods.

Returns the value of filter argument for the specific filters that have an argument.

 Retrieves information about an event of interest available in the current target.


Returns a string that describes the target's operating system version.
(ANSI version)

Returns a string that describes the target's operating system version.
(Unicode version)

Returns version number information for the current target.

Returns the value of a fixed-name alias.

Returns the value of a user-named alias or an automatic alias.

Requests an input string from the debugger engine.

Opens a log file that will receive output from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539140">client objects</a>.

Opens a log file that will receive output from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539140">client objects</a>.

Opens a log file that will receive output from the client objects.

Prints the call stack specified by an array of stack frames and corresponding register contexts.


Formats and sends a user prompt to the output callback objects.

 Formats and sends a user prompt to the output callback objects.

Formats a string and sends the result to the output callbacks that are registered with the engine's clients.

 Formats a string and send the result to output callbacks that have been registered with the engine's clients.

Removes a breakpoint.



This method is used by <a href="..\dbgeng\nn-dbgeng-idebuginputcallbacks.md">IDebugInputCallbacks</a> objects to send an input string to the engine following a request for input.

Sets a debugger command for the engine to execute when a specified event occurs.

Sets the command that will be executed by the debugger engine on the second chance of a specified exception.

Sets the syntax that the engine will use to evaluate expressions.

Sets the value of filter argument for the specific filters that can have an argument.

Sets the value of a fixed-name alias.

Sets the value of a user-named alias.

 


## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugControl4 interface%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

