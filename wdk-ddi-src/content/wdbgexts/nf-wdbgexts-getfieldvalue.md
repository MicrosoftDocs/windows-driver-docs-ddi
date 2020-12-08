---
UID: NF:wdbgexts.GetFieldValue
title: GetFieldValue macro (wdbgexts.h)
description: The GetFieldValue macro is a thin wrapper around the GetFieldData function. It is provided as a convenience for reading the value of a member in a structure.
old-location: debugger\getfieldvalue.htm
tech.root: debugger
ms.date: 11/13/2018
keywords: ["GetFieldValue macro"]
ms.keywords: GetFieldValue, GetFieldValue function [Windows Debugging], WdbgExts_Ref_68aca028-5d92-48a3-845d-f9eb480a2c40.xml, debugger.getfieldvalue, wdbgexts/GetFieldValue
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
req.target-type: Desktop
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
req.typenames: 
f1_keywords:
 - GetFieldValue
 - wdbgexts/GetFieldValue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdbgexts.h
api_name:
 - GetFieldValue
---

# GetFieldValue macro


## -description

The <b>GetFieldValue</b> macro is a thin wrapper around the <a href="/windows-hardware/drivers/ddi/wdbgexts/nf-wdbgexts-getfielddata">GetFieldData</a> function.  It is provided as a convenience for reading the value of a member in a structure.

## -parameters

### -param Addr

Specifies the address of the structure in the target's memory.

### -param Type

Specifies the name of the type of the structure.  This can be qualified with a module name, for example, <b>mymodule!mystruct</b>.

### -param Field

Specifies the name of the member in the structure.  Submembers can be specified by using a period-separated path, for example, "myfield.mysubfield".

### -param OutValue

Specifies the object into which the member's value is read.

## -returns

If the function succeeds, the return value is zero. Otherwise, the return value is one of the *IG_DUMP_SYMBOL_INFO* error code.

## -remarks

The parameters provided to this macro are the same as those provided to the <b>GetFieldData</b> function except that instead of providing a pointer to a buffer and its size, the variable to hold the returned value can be provided directly.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdbgexts/nf-wdbgexts-getfielddata">GetFieldData</a>
