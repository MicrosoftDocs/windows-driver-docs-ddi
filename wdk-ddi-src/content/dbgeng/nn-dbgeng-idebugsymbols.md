---
UID: NN:dbgeng.IDebugSymbols
title: IDebugSymbols (dbgeng.h)
description: IDebugSymbols interface
old-location: debugger\idebugsymbols.htm
tech.root: debugger
ms.assetid: 8040db26-0405-4dd3-87c5-b89d812549b5
ms.date: 05/03/2018
ms.keywords: IDebugSymbols, IDebugSymbols interface [Windows Debugging], IDebugSymbols interface [Windows Debugging],described, IDebugSymbols_4046a7ad-b8ed-4a10-991e-f7d63f9e35d0.xml, dbgeng/IDebugSymbols, debugger.idebugsymbols
ms.topic: interface
f1_keywords:
 - "dbgeng/IDebugSymbols"
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
- IDebugSymbols
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugSymbols</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IDebugSymbols</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugSymbols</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-addsymboloptions">AddSymbolOptions</a>
</td>
<td align="left" width="63%">
Turns on some of the engine's global symbol options.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-appendimagepath">AppendImagePath</a>
</td>
<td align="left" width="63%">
Appends directories to the executable image path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-appendsourcepath">AppendSourcePath</a>
</td>
<td align="left" width="63%">
Appends directories to the source path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-appendsymbolpath">AppendSymbolPath</a>
</td>
<td align="left" width="63%">
Appends directories to the symbol path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-createsymbolgroup">CreateSymbolGroup</a>
</td>
<td align="left" width="63%">
Creates a new symbol group.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-endsymbolmatch">EndSymbolMatch</a>
</td>
<td align="left" width="63%">
Releases the resources used by a symbol search.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-findsourcefile">FindSourceFile</a>
</td>
<td align="left" width="63%">
Searches the source path for a specified source file.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols-getfieldoffset">GetFieldOffset</a>
</td>
<td align="left" width="63%">
Returns the offset of a field from the base address of an instance of a type.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getimagepath">GetImagePath</a>
</td>
<td align="left" width="63%">
Returns the executable image path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getlinebyoffset">GetLineByOffset</a>
</td>
<td align="left" width="63%">
Returns the source filename and the line number within the source file of an instruction in the target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getmodulebyindex">GetModuleByIndex</a>
</td>
<td align="left" width="63%">
Returns the location of the module with the specified index.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getmodulebymodulename">GetModuleByModuleName</a>
</td>
<td align="left" width="63%">
Searches through the target's modules for one with the specified name.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getmodulebyoffset">GetModuleByOffset</a>
</td>
<td align="left" width="63%">
 Searches through the target's modules for one whose memory allocation includes the specified location.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getmodulenames">GetModuleNames</a>
</td>
<td align="left" width="63%">
Returns the names of the specified module.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getmoduleparameters">GetModuleParameters</a>
</td>
<td align="left" width="63%">
Returns parameters for modules in the target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getnamebyoffset">GetNameByOffset</a>
</td>
<td align="left" width="63%">
Returns the name of the symbol at the specified location in the target's virtual address space.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getnearnamebyoffset">GetNearNameByOffset</a>
</td>
<td align="left" width="63%">
Returns the name of a symbol that is located near the specified location.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getnextsymbolmatch">GetNextSymbolMatch</a>
</td>
<td align="left" width="63%">
Returns the next symbol found in a symbol search.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getnumbermodules">GetNumberModules</a>
</td>
<td align="left" width="63%">
Returns the number of modules in the current process's module list.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getoffsetbyline">GetOffsetByLine</a>
</td>
<td align="left" width="63%">
Returns the location of the instruction that corresponds to a specified line in the source code.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getoffsetbyname">GetOffsetByName</a>
</td>
<td align="left" width="63%">
Returns the location of a symbol identified by name.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getoffsettypeid">GetOffsetTypeId</a>
</td>
<td align="left" width="63%">
Returns the type ID of the symbol closest to the specified memory location.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getscope">GetScope</a>
</td>
<td align="left" width="63%">
Returns information about the current scope.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getscopesymbolgroup">GetScopeSymbolGroup</a>
</td>
<td align="left" width="63%">
Returns a symbol group containing the symbols in the current target's scope.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getsourcefilelineoffsets">GetSourceFileLineOffsets</a>
</td>
<td align="left" width="63%">
Maps each line in a source file to a location in the target's memory.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getsourcepath">GetSourcePath</a>
</td>
<td align="left" width="63%">
Returns the source path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getsourcepathelement">GetSourcePathElement</a>
</td>
<td align="left" width="63%">
Returns an element from the source path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getsymbolmodule">GetSymbolModule</a>
</td>
<td align="left" width="63%">
Returns the base address of module which contains the specified symbol.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getsymboloptions">GetSymbolOptions</a>
</td>
<td align="left" width="63%">
Returns the engine's global symbol options.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getsymbolpath">GetSymbolPath</a>
</td>
<td align="left" width="63%">
Returns the symbol path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getsymboltypeid">GetSymbolTypeId</a>
</td>
<td align="left" width="63%">
Returns the type ID and module of the specified symbol.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-gettypeid">GetTypeId</a>
</td>
<td align="left" width="63%">
Looks up the specified type and return its type ID.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-gettypename">GetTypeName</a>
</td>
<td align="left" width="63%">
Returns the name of the type symbol specified by its type ID and module.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-gettypesize">GetTypeSize</a>
</td>
<td align="left" width="63%">
Returns the number of bytes of memory an instance of the specified type requires.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-outputtypeddataphysical">OutputTypedDataPhysical</a>
</td>
<td align="left" width="63%">
Formats the contents of a variable in the target computer's physical memory, and then sends this to the output callbacks.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-outputtypeddatavirtual">OutputTypedDataVirtual</a>
</td>
<td align="left" width="63%">
Formats the contents of a variable in the target's virtual memory, and then sends this to the output callbacks.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-readtypeddataphysical">ReadTypedDataPhysical</a>
</td>
<td align="left" width="63%">
Reads the value of a variable from the target computer's physical memory.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-readtypeddatavirtual">ReadTypedDataVirtual</a>
</td>
<td align="left" width="63%">
Reads the value of a variable in the target's virtual memory.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-reload">Reload</a>
</td>
<td align="left" width="63%">
Deletes the engine's symbol information for the specified module and reload these symbols as needed.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-removesymboloptions">RemoveSymbolOptions</a>
</td>
<td align="left" width="63%">
Turns off some of the engine's global symbol options.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-resetscope">ResetScope</a>
</td>
<td align="left" width="63%">
Resets the current scope to the default scope of the current thread.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-setimagepath">SetImagePath</a>
</td>
<td align="left" width="63%">
Sets the executable image path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-setscope">SetScope</a>
</td>
<td align="left" width="63%">
Sets the current scope.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-setsourcepath">SetSourcePath</a>
</td>
<td align="left" width="63%">
Sets the source path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-setsymboloptions">SetSymbolOptions</a>
</td>
<td align="left" width="63%">
Changes the engine's global symbol options.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-setsymbolpath">SetSymbolPath</a>
</td>
<td align="left" width="63%">
Sets the symbol path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-startsymbolmatch">StartSymbolMatch</a>
</td>
<td align="left" width="63%">
Initializes a search for symbols whose names match a given pattern.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-writetypeddataphysical">WriteTypedDataPhysical</a>
</td>
<td align="left" width="63%">
Writes the value of a variable in the target computer's physical memory.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-writetypeddatavirtual">WriteTypedDataVirtual</a>
</td>
<td align="left" width="63%">
Writes data to the target's virtual address space.

</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugsymbols2">IDebugSymbols2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>
 

 

