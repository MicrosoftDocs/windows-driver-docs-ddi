---
UID: NS:dbgeng._DEBUG_MODULE_PARAMETERS
title: _DEBUG_MODULE_PARAMETERS (dbgeng.h)
description: The DEBUG_MODULE_PARAMETERS structure contains most of the parameters for describing a module.
old-location: debugger\debug_module_parameters.htm
tech.root: debugger
ms.assetid: 3f10997f-263f-4d1b-ab0a-d44201aaaf37
ms.date: 05/03/2018
ms.keywords: "*PDEBUG_MODULE_PARAMETERS, DEBUG_MODULE_PARAMETERS, DEBUG_MODULE_PARAMETERS structure [Windows Debugging], PDEBUG_MODULE_PARAMETERS, PDEBUG_MODULE_PARAMETERS structure pointer [Windows Debugging], Structures_6e7366d2-9f49-4b7e-a277-d788808e4c40.xml, _DEBUG_MODULE_PARAMETERS, dbgeng/DEBUG_MODULE_PARAMETERS, dbgeng/PDEBUG_MODULE_PARAMETERS, debugger.debug_module_parameters"
ms.topic: struct
f1_keywords:
 - "dbgeng/DEBUG_MODULE_PARAMETERS"
req.header: dbgeng.h
req.include-header: DbgEng.h
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
- HeaderDef
api_location:
- DbgEng.h
api_name:
- DEBUG_MODULE_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: DEBUG_MODULE_PARAMETERS, *PDEBUG_MODULE_PARAMETERS
---

# _DEBUG_MODULE_PARAMETERS structure


## -description


The DEBUG_MODULE_PARAMETERS structure contains most of the parameters for describing a module.


## -struct-fields




### -field Base

The location in the target's virtual address space of the module's base.  If the value of <b>Base</b> is DEBUG_INVALID_OFFSET, the structure is invalid.


### -field Size

The size, in bytes, of the memory range that is occupied by the module.


### -field TimeDateStamp

The date and time stamp of the module's executable file.  This is the number of seconds elapsed since midnight (00:00:00), January 1, 1970 Coordinated Universal Time (UTC) as stored in the image file header.


### -field Checksum

The checksum of the image.  This value can be zero.


### -field Flags

A bit-set that contains the module's flags.  The bit-flags that can be present are as follows. 

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_MODULE_UNLOADED

</td>
<td>
The module was unloaded.

</td>
</tr>
<tr>
<td>
DEBUG_MODULE_USER_MODE

</td>
<td>
The module  is a user-mode module.

</td>
</tr>
<tr>
<td>
DEBUG_MODULE_SYM_BAD_CHECKSUM

</td>
<td>
The checksum in the symbol file did not match the checksum for the module image.

</td>
</tr>
</table>
 


### -field SymbolType

The type of symbols that are loaded for the module.  This member can have one of the following values.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_SYMTYPE_NONE

</td>
<td>
No symbols are loaded.

</td>
</tr>
<tr>
<td>
DEBUG_SYMTYPE_COFF

</td>
<td>
The symbols are in common object file format (COFF).

</td>
</tr>
<tr>
<td>
DEBUG_SYMTYPE_CODEVIEW

</td>
<td>
The symbols are in Microsoft CodeView format. 

</td>
</tr>
<tr>
<td>
DEBUG_SYMTYPE_PDB

</td>
<td>
Symbols in PDB format have been loaded through the pre-Debug Interface Access (DIA) interface.

</td>
</tr>
<tr>
<td>
DEBUG_SYMTYPE_EXPORT

</td>
<td>
No actual symbol files were found; symbol information was extracted from the binary file's export table.

</td>
</tr>
<tr>
<td>
DEBUG_SYMTYPE_DEFERRED

</td>
<td>
The module was loaded, but the engine has deferred its loading of the symbols.

</td>
</tr>
<tr>
<td>
DEBUG_SYMTYPE_SYM

</td>
<td>
Symbols in SYM format have been loaded.

</td>
</tr>
<tr>
<td>
DEBUG_SYMTYPE_DIA

</td>
<td>
Symbols in PDB format have been loaded through the DIA interface. 

</td>
</tr>
</table>
 


### -field ImageNameSize

The size of the file name for the module. The size is measured in characters, including the terminator.


### -field ModuleNameSize

The size of the module name of the module. The size is measured in characters, including the terminator.


### -field LoadedImageNameSize

The size of the loaded image name for the module. The size is measured in characters, including the terminator.


### -field SymbolFileNameSize

The size of the symbol file name for the module. The size is measured in characters, including the terminator.


### -field MappedImageNameSize

The size of the mapped image name of the module. The size is measured in characters, including the terminator.


### -field Reserved

Reserved for system use.


## -remarks



This structure is returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getmoduleparameters">GetModuleParameters</a>.

To locate the different names for the module, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getmodulenamestring">GetModuleNameString</a>.

For more information about modules, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/modules">Modules</a>.  For details about the different names for the module, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getmodulenamestring">GetModuleNameString</a>.



