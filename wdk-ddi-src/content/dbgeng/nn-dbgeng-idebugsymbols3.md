---
UID: NN:dbgeng.IDebugSymbols3
title: IDebugSymbols3 (dbgeng.h)
description: IDebugSymbols3 interface
old-location: debugger\idebugsymbols3.htm
tech.root: debugger
ms.assetid: 3fce9384-93f3-4d81-b6ae-bda7a94da24a
ms.date: 05/03/2018
ms.keywords: IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], IDebugSymbols3 interface [Windows Debugging],described, dbgeng/IDebugSymbols3, debugger.idebugsymbols3
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
- IDebugSymbols3
- IDebugSymbols3.IsManagedModule
- IDebugSymbols3.SetScopeFromJitDebugInfo
- IDebugSymbols3.GetSymbolEntryByToken
- IDebugSymbols3.GetSymbolEntryOffsetRegions
- IDebugSymbols3.GetSymbolEntryBySymbolEntry
- IDebugSymbols3.GetSourceEntriesByOffset
- IDebugSymbols3.GetSourceEntryString
- IDebugSymbols3.GetSourceEntryStringWide
- IDebugSymbols3.GetSourceEntryOffsetRegions
- IDebugSymbols3.GetSourceEntryBySourceEntry
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3 interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugSymbols3</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugsymbols2">IDebugSymbols2</a>. <b>IDebugSymbols3</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugSymbols3</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-addsyntheticmodule">AddSyntheticModule</a>
</td>
<td align="left" width="63%">
Adds a synthetic module to the module list the debugger maintains for the current process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-addsyntheticmodulewide">AddSyntheticModuleWide</a>
</td>
<td align="left" width="63%">
Adds a synthetic module to the module list the debugger maintains for the current process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-addsyntheticsymbol">AddSyntheticSymbol</a>
</td>
<td align="left" width="63%">
Adds a synthetic symbol to a module in the current process. (ANSI version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-addsyntheticsymbolwide">AddSyntheticSymbolWide</a>
</td>
<td align="left" width="63%">
Adds a synthetic symbol to a module in the current process.
(Unicode version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-appendimagepathwide">AppendImagePathWide</a>
</td>
<td align="left" width="63%">
Appends directories to the executable image path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-appendsourcepathwide">AppendSourcePathWide</a>
</td>
<td align="left" width="63%">
Appends directories to the source path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-appendsymbolpathwide">AppendSymbolPathWide</a>
</td>
<td align="left" width="63%">
Appends directories to the symbol path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-createsymbolgroup2">CreateSymbolGroup2</a>
</td>
<td align="left" width="63%">
Creates a new symbol group.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-findsourcefilewide">FindSourceFileWide</a>
</td>
<td align="left" width="63%">
Searches the source path for a specified source file.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getconstantnamewide">GetConstantNameWide</a>
</td>
<td align="left" width="63%">
Returns the name of the specified constant.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getcurrentscopeframeindex">GetCurrentScopeFrameIndex</a>
</td>
<td align="left" width="63%">
Returns the index of the current stack frame in the call stack.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getfieldnamewide">GetFieldNameWide</a>
</td>
<td align="left" width="63%">
Returns the name of a field within a structure.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getfieldoffsetwide">GetFieldOffsetWide</a>
</td>
<td align="left" width="63%">
Returns the offset of a field from the base address of an instance of a type.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getfieldtypeandoffset">GetFieldTypeAndOffset</a>
</td>
<td align="left" width="63%">
Returns the type of a field and its offset within a container. (ANSI version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getfieldtypeandoffsetwide">GetFieldTypeAndOffsetWide</a>
</td>
<td align="left" width="63%">
Returns the type of a field and its offset within a container. (Unicode version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getfunctionentrybyoffset">GetFunctionEntryByOffset</a>
</td>
<td align="left" width="63%">
Returns the function entry information for a function.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getimagepathwide">GetImagePathWide</a>
</td>
<td align="left" width="63%">
Returns the executable image path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getlinebyoffsetwide">GetLineByOffsetWide</a>
</td>
<td align="left" width="63%">
Returns the source filename and the line number within the source file of an instruction in the target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getmodulebymodulename2">GetModuleByModuleName2</a>
</td>
<td align="left" width="63%">
Searches through the process's modules for one with the specified name.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getmodulebymodulename2wide">GetModuleByModuleName2Wide</a>
</td>
<td align="left" width="63%">
Searches through the process's modules for one with the specified name.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getmodulebymodulenamewide">GetModuleByModuleNameWide</a>
</td>
<td align="left" width="63%">
Searches through the target's modules for one with the specified name.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getmodulebyoffset2">GetModuleByOffset2</a>
</td>
<td align="left" width="63%">
Searches through the process's modules for one whose memory allocation includes the specified location.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getmodulenamestringwide">GetModuleNameStringWide</a>
</td>
<td align="left" width="63%">
Returns the name of the specified module.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getmoduleversioninformationwide">GetModuleVersionInformationWide</a>
</td>
<td align="left" width="63%">
Returns version information for the specified module.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getnamebyoffsetwide">GetNameByOffsetWide</a>
</td>
<td align="left" width="63%">
Returns the name of the symbol at the specified location in the target's virtual address space.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getnearnamebyoffsetwide">GetNearNameByOffsetWide</a>
</td>
<td align="left" width="63%">
Returns the name of a symbol that is located near the specified location.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getnextsymbolmatchwide">GetNextSymbolMatchWide</a>
</td>
<td align="left" width="63%">
Returns the next symbol found in a symbol search.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getoffsetbylinewide">GetOffsetByLineWide</a>
</td>
<td align="left" width="63%">
Returns the location of the instruction that corresponds to a specified line in the source code.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getoffsetbynamewide">GetOffsetByNameWide</a>
</td>
<td align="left" width="63%">
Returns the location of a symbol identified by name.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getscopesymbolgroup2">GetScopeSymbolGroup2</a>
</td>
<td align="left" width="63%">
Returns a symbol group containing the symbols in the current target's scope.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getsourceentriesbyline">GetSourceEntriesByLine</a>
</td>
<td align="left" width="63%">
Queries symbol information and returns locations in the target's memory that correspond to lines in a source file. (ANSI version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getsourceentriesbylinewide">GetSourceEntriesByLineWide</a>
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
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getsourcefilelineoffsetswide">GetSourceFileLineOffsetsWide</a>
</td>
<td align="left" width="63%">
Maps each line in a source file to a location in the target's memory.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getsourcepathelementwide">GetSourcePathElementWide</a>
</td>
<td align="left" width="63%">
Returns an element from the source path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getsourcepathwide">GetSourcePathWide</a>
</td>
<td align="left" width="63%">
Returns the source path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getsymbolentriesbyname">GetSymbolEntriesByName</a>
</td>
<td align="left" width="63%">
Returns the symbols whose names match a given pattern. (ANSI version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getsymbolentriesbynamewide">GetSymbolEntriesByNameWide</a>
</td>
<td align="left" width="63%">
Returns the symbols whose names match a given pattern.
(Unicode version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getsymbolentriesbyoffset">GetSymbolEntriesByOffset</a>
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
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getsymbolentryinformation">GetSymbolEntryInformation</a>
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
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getsymbolentrystring">GetSymbolEntryString</a>
</td>
<td align="left" width="63%">
Returns string information for the specified symbol. (ANSI version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getsymbolentrystringwide">GetSymbolEntryStringWide</a>
</td>
<td align="left" width="63%">
Returns string information for the specified symbol.
(Unicode version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getsymbolmodulewide">GetSymbolModuleWide</a>
</td>
<td align="left" width="63%">
Returns the base address of module which contains the specified symbol.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getsymbolpathwide">GetSymbolPathWide</a>
</td>
<td align="left" width="63%">
Returns the symbol path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getsymboltypeidwide">GetSymbolTypeIdWide</a>
</td>
<td align="left" width="63%">
Returns the type ID and module of the specified symbol.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-gettypeidwide">GetTypeIdWide</a>
</td>
<td align="left" width="63%">
Looks up the specified type and return its type ID.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-gettypenamewide">GetTypeNameWide</a>
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
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-outputsymbolbyoffset">OutputSymbolByOffset</a>
</td>
<td align="left" width="63%">
Looks up a symbol by address and prints the symbol name and other symbol information to the debugger console.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-reloadwide">ReloadWide</a>
</td>
<td align="left" width="63%">
Deletes the engine's symbol information for the specified module and reload these symbols as needed.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-removesyntheticmodule">RemoveSyntheticModule</a>
</td>
<td align="left" width="63%">
Removes a synthetic module from the module list the debugger maintains for the current process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-removesyntheticsymbol">RemoveSyntheticSymbol</a>
</td>
<td align="left" width="63%">
Removes a synthetic symbol from a module in the current process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-setimagepathwide">SetImagePathWide</a>
</td>
<td align="left" width="63%">
Sets the executable image path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-setscopeframebyindex">SetScopeFrameByIndex</a>
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
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-setscopefromstoredevent">SetScopeFromStoredEvent</a>
</td>
<td align="left" width="63%">
Sets the current scope to the scope of the stored event.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-setsourcepathwide">SetSourcePathWide</a>
</td>
<td align="left" width="63%">
Sets the source path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-setsymbolpathwide">SetSymbolPathWide</a>
</td>
<td align="left" width="63%">
Sets the symbol path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-startsymbolmatchwide">StartSymbolMatchWide</a>
</td>
<td align="left" width="63%">
Initializes a search for symbols whose names match a given pattern.

</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugsymbols">IDebugSymbols</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugsymbols2">IDebugSymbols2</a>
 

 

