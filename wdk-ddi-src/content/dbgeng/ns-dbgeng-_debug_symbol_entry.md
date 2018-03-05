---
UID: NS:dbgeng._DEBUG_SYMBOL_ENTRY
title: "_DEBUG_SYMBOL_ENTRY"
author: windows-driver-content
description: The DEBUG_SYMBOL_ENTRY structure describes a symbol in a symbol group.
old-location: debugger\debug_symbol_entry.htm
old-project: debugger
ms.assetid: 31ffab25-ec34-42ff-bdde-c98fef003bfc
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PDEBUG_SYMBOL_ENTRY, DEBUG_SYMBOL_ENTRY, DEBUG_SYMBOL_ENTRY structure [Windows Debugging], PDEBUG_SYMBOL_ENTRY, PDEBUG_SYMBOL_ENTRY structure pointer [Windows Debugging], Structures_5673550e-274a-429f-9a31-88e401bca68e.xml, _DEBUG_SYMBOL_ENTRY, dbgeng/DEBUG_SYMBOL_ENTRY, dbgeng/PDEBUG_SYMBOL_ENTRY, debugger.debug_symbol_entry"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dbgeng.h
req.include-header: DbgEng.h, DbgHelp.h, DbgHelp.h
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
-	HeaderDef
api_location:
-	DbgEng.h
api_name:
-	DEBUG_SYMBOL_ENTRY
product: Windows
targetos: Windows
req.typenames: DEBUG_SYMBOL_ENTRY, *PDEBUG_SYMBOL_ENTRY
---

# _DEBUG_SYMBOL_ENTRY structure


## -description


The DEBUG_SYMBOL_ENTRY structure describes a symbol in a symbol group.


## -syntax


````
typedef struct _DEBUG_SYMBOL_ENTRY {
  ULONG64 ModuleBase;
  ULONG64 Offset;
  ULONG64 Id;
  ULONG64 Arg64;
  ULONG   Size;
  ULONG   Flags;
  ULONG   TypeId;
  ULONG   NameSize;
  ULONG   Token;
  ULONG   Tag;
  ULONG   Arg32;
  ULONG   Reserved;
}  DEBUG_SYMBOL_ENTRY, *PDEBUG_SYMBOL_ENTRY;
````


## -struct-fields




### -field ModuleBase

The base address of the module in the target's virtual address space.


### -field Offset

The location of the symbol in the target's virtual address space.


### -field Id

The symbol ID of the symbol.  If the symbol ID is not known, <b>Id</b> is DEBUG_INVALID_OFFSET.


### -field Arg64

The interpretation of <b>Arg64</b> depends on the type of the symbol.  If the value is not known, <b>Arg64</b> is zero.


### -field Size

The size, in bytes, of the symbol's value.  This might not be known or might not completely represent all of the data for a symbol.  For example, a function's code might be split among multiple regions and the size only describes one region.


### -field Flags

Symbol entry flags.  Currently, no flags are defined.


### -field TypeId

The type ID of the symbol.


### -field NameSize

The size, in characters, of the symbol's name.  If the size is not known, <b>NameSize</b> is zero.


### -field Token

The managed token of the symbol.  If the token value is not known or the symbol does not have a token, <b>Token</b> is zero.


### -field Tag

The symbol tag for the type of the symbol.  This is a value from the <b>SymTagEnum</b> enumeration.


### -field Arg32

The interpretation of <b>Arg32</b> depends on the type of the symbol.  Currently, the value of <b>Arg32</b> is the register that holds the value or a pointer to the value of the symbol. If the symbol is not held in a register, or the register is not known, <b>Arg32</b> is zero.


### -field Reserved

Set to zero.


## -see-also

<a href="https://msdn.microsoft.com/ee8ea970-04ee-4bf5-9e81-7d5baf0eac0d">IdebugSymbolGroup2::GetSymbolEntryInformation</a>



<a href="https://msdn.microsoft.com/02fe418f-1793-4585-9891-1274a4ddba74">IdebugSymbols3::GetSymbolEntryInformation</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20DEBUG_SYMBOL_ENTRY structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

