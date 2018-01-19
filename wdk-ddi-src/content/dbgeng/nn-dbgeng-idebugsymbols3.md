---
UID: NN:dbgeng.IDebugSymbols3
title: IDebugSymbols3
author: windows-driver-content
description: IDebugSymbols3 interface
old-location: debugger\idebugsymbols3.htm
old-project: debugger
ms.assetid: 3fce9384-93f3-4d81-b6ae-bda7a94da24a
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSystemObjects4, IDebugSystemObjects4::SetImplicitThreadDataOffset, SetImplicitThreadDataOffset
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
req.alt-api: IDebugSymbols3,IDebugSymbols3.IsManagedModule,IDebugSymbols3.SetScopeFromJitDebugInfo,IDebugSymbols3.GetSymbolEntryByToken,IDebugSymbols3.GetSymbolEntryOffsetRegions,IDebugSymbols3.GetSymbolEntryBySymbolEntry,IDebugSymbols3.GetSourceEntriesByOffset,IDebugSymbols3.GetSourceEntryString,IDebugSymbols3.GetSourceEntryStringWide,IDebugSymbols3.GetSourceEntryOffsetRegions,IDebugSymbols3.GetSourceEntryBySourceEntry
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

# IDebugSymbols3 interface



## -description

## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugSymbols3</b> interface inherits from <a href="..\dbgeng\nn-dbgeng-idebugsymbols2.md">IDebugSymbols2</a>. <b>IDebugSymbols3</b> also has these types of members:

The <b>IDebugSymbols3</b> interface has these methods.

Adds a synthetic module to the module list the debugger maintains for the current process.

Adds a synthetic module to the module list the debugger maintains for the current process.

Adds a synthetic symbol to a module in the current process. (ANSI version)

Adds a synthetic symbol to a module in the current process.
(Unicode version)

Appends directories to the executable image path.

Appends directories to the source path.

Appends directories to the symbol path.

Creates a new symbol group.

Searches the source path for a specified source file.

Returns the name of the specified constant.

Returns the index of the current stack frame in the call stack.

Returns the name of a field within a structure.

Returns the offset of a field from the base address of an instance of a type.

Returns the type of a field and its offset within a container. (ANSI version)

Returns the type of a field and its offset within a container. (Unicode version)

Returns the function entry information for a function.

Returns the executable image path.

Returns the source filename and the line number within the source file of an instruction in the target.

Searches through the process's modules for one with the specified name.

Searches through the process's modules for one with the specified name.

Searches through the target's modules for one with the specified name.

Searches through the process's modules for one whose memory allocation includes the specified location.

Returns the name of the specified module.

Returns version information for the specified module.

Returns the name of the symbol at the specified location in the target's virtual address space.

Returns the name of a symbol that is located near the specified location.

Returns the next symbol found in a symbol search.

Returns the location of the instruction that corresponds to a specified line in the source code.

Returns the location of a symbol identified by name.


Returns a symbol group containing the symbols in the current target's scope.

Queries symbol information and returns locations in the target's memory that correspond to lines in a source file. (ANSI version)

Queries symbol information and returns locations in the target's memory that correspond to lines in a source file. (Unicode version)











Maps each line in a source file to a location in the target's memory.

Returns an element from the source path.

Returns the source path.

Returns the symbols whose names match a given pattern. (ANSI version)

Returns the symbols whose names match a given pattern.
(Unicode version)

Returns the symbols which are located at a specified address.





Returns the symbol entry information for a symbol.



Returns string information for the specified symbol. (ANSI version)

Returns string information for the specified symbol.
(Unicode version)

Returns the base address of module which contains the specified symbol.

Returns the symbol path.

Returns the type ID and module of the specified symbol.

Looks up the specified type and return its type ID.

Returns the name of the type symbol specified by its type ID and module.



Looks up a symbol by address and prints the symbol name and other symbol information to the debugger console.

Deletes the engine's symbol information for the specified module and reload these symbols as needed.

Removes a synthetic module from the module list the debugger maintains for the current process.

Removes a synthetic symbol from a module in the current process.

Sets the executable image path.

Sets the current scope to the scope of one of the frames on the call stack.



Sets the current scope to the scope of the stored event.

Sets the source path.

Sets the symbol path.

Initializes a search for symbols whose names match a given pattern.

 


## -members
The <b>IDebugSymbols3</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537937">AddSyntheticModule</a>
</td>
<td align="left" width="63%">
Adds a synthetic module to the module list the debugger maintains for the current process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537940">AddSyntheticModuleWide</a>
</td>
<td align="left" width="63%">
Adds a synthetic module to the module list the debugger maintains for the current process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537943">AddSyntheticSymbol</a>
</td>
<td align="left" width="63%">
Adds a synthetic symbol to a module in the current process. (ANSI version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537946">AddSyntheticSymbolWide</a>
</td>
<td align="left" width="63%">
Adds a synthetic symbol to a module in the current process.
(Unicode version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff538094">AppendImagePathWide</a>
</td>
<td align="left" width="63%">
Appends directories to the executable image path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff538107">AppendSourcePathWide</a>
</td>
<td align="left" width="63%">
Appends directories to the source path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff538113">AppendSymbolPathWide</a>
</td>
<td align="left" width="63%">
Appends directories to the symbol path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540096">CreateSymbolGroup2</a>
</td>
<td align="left" width="63%">
Creates a new symbol group.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545445">FindSourceFileWide</a>
</td>
<td align="left" width="63%">
Searches the source path for a specified source file.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545723">GetConstantNameWide</a>
</td>
<td align="left" width="63%">
Returns the name of the specified constant.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545862">GetCurrentScopeFrameIndex</a>
</td>
<td align="left" width="63%">
Returns the index of the current stack frame in the call stack.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546753">GetFieldNameWide</a>
</td>
<td align="left" width="63%">
Returns the name of a field within a structure.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546767">GetFieldOffsetWide</a>
</td>
<td align="left" width="63%">
Returns the offset of a field from the base address of an instance of a type.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546771">GetFieldTypeAndOffset</a>
</td>
<td align="left" width="63%">
Returns the type of a field and its offset within a container. (ANSI version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546775">GetFieldTypeAndOffsetWide</a>
</td>
<td align="left" width="63%">
Returns the type of a field and its offset within a container. (Unicode version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546817">GetFunctionEntryByOffset</a>
</td>
<td align="left" width="63%">
Returns the function entry information for a function.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546857">GetImagePathWide</a>
</td>
<td align="left" width="63%">
Returns the executable image path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547008">GetLineByOffsetWide</a>
</td>
<td align="left" width="63%">
Returns the source filename and the line number within the source file of an instruction in the target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547102">GetModuleByModuleName2</a>
</td>
<td align="left" width="63%">
Searches through the process's modules for one with the specified name.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547116">GetModuleByModuleName2Wide</a>
</td>
<td align="left" width="63%">
Searches through the process's modules for one with the specified name.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547126">GetModuleByModuleNameWide</a>
</td>
<td align="left" width="63%">
Searches through the target's modules for one with the specified name.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547138">GetModuleByOffset2</a>
</td>
<td align="left" width="63%">
Searches through the process's modules for one whose memory allocation includes the specified location.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547154">GetModuleNameStringWide</a>
</td>
<td align="left" width="63%">
Returns the name of the specified module.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547177">GetModuleVersionInformationWide</a>
</td>
<td align="left" width="63%">
Returns version information for the specified module.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547186">GetNameByOffsetWide</a>
</td>
<td align="left" width="63%">
Returns the name of the symbol at the specified location in the target's virtual address space.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547837">GetNearNameByOffsetWide</a>
</td>
<td align="left" width="63%">
Returns the name of a symbol that is located near the specified location.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547859">GetNextSymbolMatchWide</a>
</td>
<td align="left" width="63%">
Returns the next symbol found in a symbol search.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548026">GetOffsetByLineWide</a>
</td>
<td align="left" width="63%">
Returns the location of the instruction that corresponds to a specified line in the source code.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548042">GetOffsetByNameWide</a>
</td>
<td align="left" width="63%">
Returns the location of a symbol identified by name.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548287">GetScopeSymbolGroup2</a>
</td>
<td align="left" width="63%">
Returns a symbol group containing the symbols in the current target's scope.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548305">GetSourceEntriesByLine</a>
</td>
<td align="left" width="63%">
Queries symbol information and returns locations in the target's memory that correspond to lines in a source file. (ANSI version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548312">GetSourceEntriesByLineWide</a>
</td>
<td align="left" width="63%">
Queries symbol information and returns locations in the target's memory that correspond to lines in a source file. (Unicode version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>GetSourceEntriesByOffset</b></td>
<td align="left" width="63%">


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>GetSourceEntryBySourceEntry</b></td>
<td align="left" width="63%">


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>GetSourceEntryOffsetRegions</b></td>
<td align="left" width="63%">


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>GetSourceEntryString</b></td>
<td align="left" width="63%">


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>GetSourceEntryStringWide</b></td>
<td align="left" width="63%">


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548346">GetSourceFileLineOffsetsWide</a>
</td>
<td align="left" width="63%">
Maps each line in a source file to a location in the target's memory.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548375">GetSourcePathElementWide</a>
</td>
<td align="left" width="63%">
Returns an element from the source path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548381">GetSourcePathWide</a>
</td>
<td align="left" width="63%">
Returns the source path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548458">GetSymbolEntriesByName</a>
</td>
<td align="left" width="63%">
Returns the symbols whose names match a given pattern. (ANSI version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548463">GetSymbolEntriesByNameWide</a>
</td>
<td align="left" width="63%">
Returns the symbols whose names match a given pattern.
(Unicode version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548476">GetSymbolEntriesByOffset</a>
</td>
<td align="left" width="63%">
Returns the symbols which are located at a specified address.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>GetSymbolEntryBySymbolEntry</b></td>
<td align="left" width="63%">


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>GetSymbolEntryByToken</b></td>
<td align="left" width="63%">


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548484">GetSymbolEntryInformation</a>
</td>
<td align="left" width="63%">
Returns the symbol entry information for a symbol.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>GetSymbolEntryOffsetRegions</b></td>
<td align="left" width="63%">


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548491">GetSymbolEntryString</a>
</td>
<td align="left" width="63%">
Returns string information for the specified symbol. (ANSI version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548496">GetSymbolEntryStringWide</a>
</td>
<td align="left" width="63%">
Returns string information for the specified symbol.
(Unicode version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549119">GetSymbolModuleWide</a>
</td>
<td align="left" width="63%">
Returns the base address of module which contains the specified symbol.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549161">GetSymbolPathWide</a>
</td>
<td align="left" width="63%">
Returns the symbol path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549182">GetSymbolTypeIdWide</a>
</td>
<td align="left" width="63%">
Returns the type ID and module of the specified symbol.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549387">GetTypeIdWide</a>
</td>
<td align="left" width="63%">
Looks up the specified type and return its type ID.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549419">GetTypeNameWide</a>
</td>
<td align="left" width="63%">
Returns the name of the type symbol specified by its type ID and module.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>IsManagedModule</b></td>
<td align="left" width="63%">


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553258">OutputSymbolByOffset</a>
</td>
<td align="left" width="63%">
Looks up a symbol by address and prints the symbol name and other symbol information to the debugger console.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554384">ReloadWide</a>
</td>
<td align="left" width="63%">
Deletes the engine's symbol information for the specified module and reload these symbols as needed.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554536">RemoveSyntheticModule</a>
</td>
<td align="left" width="63%">
Removes a synthetic module from the module list the debugger maintains for the current process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554542">RemoveSyntheticSymbol</a>
</td>
<td align="left" width="63%">
Removes a synthetic symbol from a module in the current process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556710">SetImagePathWide</a>
</td>
<td align="left" width="63%">
Sets the executable image path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556774">SetScopeFrameByIndex</a>
</td>
<td align="left" width="63%">
Sets the current scope to the scope of one of the frames on the call stack.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>SetScopeFromJitDebugInfo</b></td>
<td align="left" width="63%">


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556778">SetScopeFromStoredEvent</a>
</td>
<td align="left" width="63%">
Sets the current scope to the scope of the stored event.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556788">SetSourcePathWide</a>
</td>
<td align="left" width="63%">
Sets the source path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556804">SetSymbolPathWide</a>
</td>
<td align="left" width="63%">
Sets the symbol path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558816">StartSymbolMatchWide</a>
</td>
<td align="left" width="63%">
Initializes a search for symbols whose names match a given pattern.

</td>
</tr>
</table>Adds a synthetic module to the module list the debugger maintains for the current process.

Adds a synthetic module to the module list the debugger maintains for the current process.

Adds a synthetic symbol to a module in the current process. (ANSI version)

Adds a synthetic symbol to a module in the current process.
(Unicode version)

Appends directories to the executable image path.

Appends directories to the source path.

Appends directories to the symbol path.

Creates a new symbol group.

Searches the source path for a specified source file.

Returns the name of the specified constant.

Returns the index of the current stack frame in the call stack.

Returns the name of a field within a structure.

Returns the offset of a field from the base address of an instance of a type.

Returns the type of a field and its offset within a container. (ANSI version)

Returns the type of a field and its offset within a container. (Unicode version)

Returns the function entry information for a function.

Returns the executable image path.

Returns the source filename and the line number within the source file of an instruction in the target.

Searches through the process's modules for one with the specified name.

Searches through the process's modules for one with the specified name.

Searches through the target's modules for one with the specified name.

Searches through the process's modules for one whose memory allocation includes the specified location.

Returns the name of the specified module.

Returns version information for the specified module.

Returns the name of the symbol at the specified location in the target's virtual address space.

Returns the name of a symbol that is located near the specified location.

Returns the next symbol found in a symbol search.

Returns the location of the instruction that corresponds to a specified line in the source code.

Returns the location of a symbol identified by name.


Returns a symbol group containing the symbols in the current target's scope.

Queries symbol information and returns locations in the target's memory that correspond to lines in a source file. (ANSI version)

Queries symbol information and returns locations in the target's memory that correspond to lines in a source file. (Unicode version)











Maps each line in a source file to a location in the target's memory.

Returns an element from the source path.

Returns the source path.

Returns the symbols whose names match a given pattern. (ANSI version)

Returns the symbols whose names match a given pattern.
(Unicode version)

Returns the symbols which are located at a specified address.





Returns the symbol entry information for a symbol.



Returns string information for the specified symbol. (ANSI version)

Returns string information for the specified symbol.
(Unicode version)

Returns the base address of module which contains the specified symbol.

Returns the symbol path.

Returns the type ID and module of the specified symbol.

Looks up the specified type and return its type ID.

Returns the name of the type symbol specified by its type ID and module.



Looks up a symbol by address and prints the symbol name and other symbol information to the debugger console.

Deletes the engine's symbol information for the specified module and reload these symbols as needed.

Removes a synthetic module from the module list the debugger maintains for the current process.

Removes a synthetic symbol from a module in the current process.

Sets the executable image path.

Sets the current scope to the scope of one of the frames on the call stack.



Sets the current scope to the scope of the stored event.

Sets the source path.

Sets the symbol path.

Initializes a search for symbols whose names match a given pattern.

 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbols.md">IDebugSymbols</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbols2.md">IDebugSymbols2</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3 interface%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

