---
UID: NS:dbgeng._DEBUG_MODULE_AND_ID
title: _DEBUG_MODULE_AND_ID (dbgeng.h)
description: The DEBUG_MODULE_AND_ID structure describes a symbol within a module.
old-location: debugger\debug_module_and_id.htm
tech.root: debugger
ms.assetid: d65ad0fa-1dd8-42b4-866b-cb2522080cde
ms.date: 05/03/2018
keywords: ["DEBUG_MODULE_AND_ID structure"]
ms.keywords: "*PDEBUG_MODULE_AND_ID, DEBUG_MODULE_AND_ID, DEBUG_MODULE_AND_ID structure [Windows Debugging], PDEBUG_MODULE_AND_ID, PDEBUG_MODULE_AND_ID structure pointer [Windows Debugging], Structures_d53c2a34-f855-45a0-918b-0a8dfb936828.xml, _DEBUG_MODULE_AND_ID, dbgeng/DEBUG_MODULE_AND_ID, dbgeng/PDEBUG_MODULE_AND_ID, debugger.debug_module_and_id"
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
targetos: Windows
req.typenames: DEBUG_MODULE_AND_ID, *PDEBUG_MODULE_AND_ID
f1_keywords:
 - _DEBUG_MODULE_AND_ID
 - dbgeng/_DEBUG_MODULE_AND_ID
 - PDEBUG_MODULE_AND_ID
 - dbgeng/PDEBUG_MODULE_AND_ID
 - DEBUG_MODULE_AND_ID
 - dbgeng/DEBUG_MODULE_AND_ID
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - DbgEng.h
api_name:
 - DEBUG_MODULE_AND_ID
---

# _DEBUG_MODULE_AND_ID structure


## -description

The DEBUG_MODULE_AND_ID structure describes a symbol within a module.

## -struct-fields

### -field ModuleBase

The location in the target's virtual address space of the module's base address.

### -field Id

The symbol ID of the symbol within the module.

