---
UID: NS:dbgeng._DEBUG_MODULE_AND_ID
title: _DEBUG_MODULE_AND_ID
author: windows-driver-content
description: The DEBUG_MODULE_AND_ID structure describes a symbol within a module.
old-location: debugger\debug_module_and_id.htm
old-project: debugger
ms.assetid: d65ad0fa-1dd8-42b4-866b-cb2522080cde
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _DEBUG_MODULE_AND_ID, DEBUG_MODULE_AND_ID, *PDEBUG_MODULE_AND_ID
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dbgeng.h
req.include-header: DbgEng.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DEBUG_MODULE_AND_ID
req.alt-loc: DbgEng.h
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
req.typenames: DEBUG_MODULE_AND_ID, *PDEBUG_MODULE_AND_ID
---

# _DEBUG_MODULE_AND_ID structure



## -description
The DEBUG_MODULE_AND_ID structure describes a symbol within a module.



## -syntax

````
typedef struct _DEBUG_MODULE_AND_ID {
  ULONG64 ModuleBase;
  ULONG64 Id;
}  DEBUG_MODULE_AND_ID, *PDEBUG_MODULE_AND_ID;
````


## -struct-fields

### -field ModuleBase

The location in the target's virtual address space of the module's base address.


### -field Id

The symbol ID of the symbol within the module.


## -remarks
