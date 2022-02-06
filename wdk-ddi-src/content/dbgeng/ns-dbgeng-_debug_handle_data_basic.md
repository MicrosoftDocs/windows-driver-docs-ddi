---
UID: NS:dbgeng._DEBUG_HANDLE_DATA_BASIC
title: _DEBUG_HANDLE_DATA_BASIC (dbgeng.h)
description: The DEBUG_HANDLE_DATA_BASIC structure contains handle-related information about a system object.
old-location: debugger\debug_handle_data_basic.htm
tech.root: debugger
ms.date: 02/06/2022
keywords: ["DEBUG_HANDLE_DATA_BASIC structure"]
ms.keywords: "*PDEBUG_HANDLE_DATA_BASIC, DEBUG_HANDLE_DATA_BASIC, DEBUG_HANDLE_DATA_BASIC structure [Windows Debugging], PDEBUG_HANDLE_DATA_BASIC, PDEBUG_HANDLE_DATA_BASIC structure pointer [Windows Debugging], Structures_e4fb66c0-8e88-4f35-a103-0cc0f7cc1bfd.xml, _DEBUG_HANDLE_DATA_BASIC, dbgeng/DEBUG_HANDLE_DATA_BASIC, dbgeng/PDEBUG_HANDLE_DATA_BASIC, debugger.debug_handle_data_basic"
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
req.typenames: DEBUG_HANDLE_DATA_BASIC, *PDEBUG_HANDLE_DATA_BASIC
f1_keywords:
 - _DEBUG_HANDLE_DATA_BASIC
 - dbgeng/_DEBUG_HANDLE_DATA_BASIC
 - PDEBUG_HANDLE_DATA_BASIC
 - dbgeng/PDEBUG_HANDLE_DATA_BASIC
 - DEBUG_HANDLE_DATA_BASIC
 - dbgeng/DEBUG_HANDLE_DATA_BASIC
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - DbgEng.h
api_name:
 - _DEBUG_HANDLE_DATA_BASIC
 - PDEBUG_HANDLE_DATA_BASIC
 - DEBUG_HANDLE_DATA_BASIC
---

# _DEBUG_HANDLE_DATA_BASIC structure


## -description

The DEBUG_HANDLE_DATA_BASIC structure contains handle-related information about a system object.

## -struct-fields

### -field TypeNameSize

The size, in characters, of the object-type name. This size includes the space for the '\0' terminating character. 

### -field ObjectNameSize

The size, in characters, of the object's name. This size includes the space for the '\0' terminating character. 

### -field Attributes

A bit-set that contains the handle's attributes.  For possible values, see "Handle" in the Windows Driver Kit (WDK).

### -field GrantedAccess

A bit-set that specifies the access mask for the object that is represented by the handle.  For details, see ACCESS_MASK in the Platform SDK documentation.

### -field HandleCount

The number of handle references for the object.

### -field PointerCount

The number of pointer references for the object.

