---
UID: NN:dbgeng.IDebugSymbols
title: IDebugSymbols
author: windows-driver-content
description: IDebugSymbols interface
old-location: debugger\idebugsymbols.htm
old-project: debugger
ms.assetid: 8040db26-0405-4dd3-87c5-b89d812549b5
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugSymbols, IDebugSymbols interface [Windows Debugging], IDebugSymbols interface [Windows Debugging], described, IDebugSymbols_4046a7ad-b8ed-4a10-991e-f7d63f9e35d0.xml, dbgeng/IDebugSymbols, debugger.idebugsymbols
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugSymbols
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugSymbols</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IDebugSymbols</b> also has these types of members:
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537930">AddSymbolOptions</a>
</td>
<td align="left" width="63%">
Turns on some of the engine's global symbol options.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff538092">AppendImagePath</a>
</td>
<td align="left" width="63%">
Appends directories to the executable image path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff538102">AppendSourcePath</a>
</td>
<td align="left" width="63%">
Appends directories to the source path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff538110">AppendSymbolPath</a>
</td>
<td align="left" width="63%">
Appends directories to the symbol path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540093">CreateSymbolGroup</a>
</td>
<td align="left" width="63%">
Creates a new symbol group.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543008">EndSymbolMatch</a>
</td>
<td align="left" width="63%">
Releases the resources used by a symbol search.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545423">FindSourceFile</a>
</td>
<td align="left" width="63%">
Searches the source path for a specified source file.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546758">GetFieldOffset</a>
</td>
<td align="left" width="63%">
Returns the offset of a field from the base address of an instance of a type.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546851">GetImagePath</a>
</td>
<td align="left" width="63%">
Returns the executable image path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546995">GetLineByOffset</a>
</td>
<td align="left" width="63%">
Returns the source filename and the line number within the source file of an instruction in the target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547080">GetModuleByIndex</a>
</td>
<td align="left" width="63%">
Returns the location of the module with the specified index.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547095">GetModuleByModuleName</a>
</td>
<td align="left" width="63%">
Searches through the target's modules for one with the specified name.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547132">GetModuleByOffset</a>
</td>
<td align="left" width="63%">
 Searches through the target's modules for one whose memory allocation includes the specified location.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547146">GetModuleNames</a>
</td>
<td align="left" width="63%">
Returns the names of the specified module.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547161">GetModuleParameters</a>
</td>
<td align="left" width="63%">
Returns parameters for modules in the target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547183">GetNameByOffset</a>
</td>
<td align="left" width="63%">
Returns the name of the symbol at the specified location in the target's virtual address space.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547204">GetNearNameByOffset</a>
</td>
<td align="left" width="63%">
Returns the name of a symbol that is located near the specified location.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547856">GetNextSymbolMatch</a>
</td>
<td align="left" width="63%">
Returns the next symbol found in a symbol search.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547927">GetNumberModules</a>
</td>
<td align="left" width="63%">
Returns the number of modules in the current process's module list.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548022">GetOffsetByLine</a>
</td>
<td align="left" width="63%">
Returns the location of the instruction that corresponds to a specified line in the source code.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548035">GetOffsetByName</a>
</td>
<td align="left" width="63%">
Returns the location of a symbol identified by name.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548062">GetOffsetTypeId</a>
</td>
<td align="left" width="63%">
Returns the type ID of the symbol closest to the specified memory location.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548270">GetScope</a>
</td>
<td align="left" width="63%">
Returns information about the current scope.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548280">GetScopeSymbolGroup</a>
</td>
<td align="left" width="63%">
Returns a symbol group containing the symbols in the current target's scope.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548339">GetSourceFileLineOffsets</a>
</td>
<td align="left" width="63%">
Maps each line in a source file to a location in the target's memory.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548358">GetSourcePath</a>
</td>
<td align="left" width="63%">
Returns the source path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548367">GetSourcePathElement</a>
</td>
<td align="left" width="63%">
Returns an element from the source path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549112">GetSymbolModule</a>
</td>
<td align="left" width="63%">
Returns the base address of module which contains the specified symbol.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549139">GetSymbolOptions</a>
</td>
<td align="left" width="63%">
Returns the engine's global symbol options.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549155">GetSymbolPath</a>
</td>
<td align="left" width="63%">
Returns the symbol path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549173">GetSymbolTypeId</a>
</td>
<td align="left" width="63%">
Returns the type ID and module of the specified symbol.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549376">GetTypeId</a>
</td>
<td align="left" width="63%">
Looks up the specified type and return its type ID.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549408">GetTypeName</a>
</td>
<td align="left" width="63%">
Returns the name of the type symbol specified by its type ID and module.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549457">GetTypeSize</a>
</td>
<td align="left" width="63%">
Returns the number of bytes of memory an instance of the specified type requires.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553269">OutputTypedDataPhysical</a>
</td>
<td align="left" width="63%">
Formats the contents of a variable in the target computer's physical memory, and then sends this to the output callbacks.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553274">OutputTypedDataVirtual</a>
</td>
<td align="left" width="63%">
Formats the contents of a variable in the target's virtual memory, and then sends this to the output callbacks.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554344">ReadTypedDataPhysical</a>
</td>
<td align="left" width="63%">
Reads the value of a variable from the target computer's physical memory.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554345">ReadTypedDataVirtual</a>
</td>
<td align="left" width="63%">
Reads the value of a variable in the target's virtual memory.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554379">Reload</a>
</td>
<td align="left" width="63%">
Deletes the engine's symbol information for the specified module and reload these symbols as needed.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554535">RemoveSymbolOptions</a>
</td>
<td align="left" width="63%">
Turns off some of the engine's global symbol options.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554577">ResetScope</a>
</td>
<td align="left" width="63%">
Resets the current scope to the default scope of the current thread.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556708">SetImagePath</a>
</td>
<td align="left" width="63%">
Sets the executable image path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556773">SetScope</a>
</td>
<td align="left" width="63%">
Sets the current scope.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556781">SetSourcePath</a>
</td>
<td align="left" width="63%">
Sets the source path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556798">SetSymbolOptions</a>
</td>
<td align="left" width="63%">
Changes the engine's global symbol options.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556802">SetSymbolPath</a>
</td>
<td align="left" width="63%">
Sets the symbol path.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558815">StartSymbolMatch</a>
</td>
<td align="left" width="63%">
Initializes a search for symbols whose names match a given pattern.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561463">WriteTypedDataPhysical</a>
</td>
<td align="left" width="63%">
Writes the value of a variable in the target computer's physical memory.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561466">WriteTypedDataVirtual</a>
</td>
<td align="left" width="63%">
Writes data to the target's virtual address space.

</td>
</tr>
</table> 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550864">IDebugSymbols2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols interface%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
