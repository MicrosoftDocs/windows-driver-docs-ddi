---
UID: NF:wdbgexts.GetFieldData
title: GetFieldData function (wdbgexts.h)
description: The GetFieldData function returns the value of a member in a structure.
old-location: debugger\getfielddata.htm
tech.root: debugger
ms.assetid: e60c2288-fe25-4da5-9b17-6e95a30e7c1c
ms.date: 05/03/2018
keywords: ["GetFieldData function"]
ms.keywords: GetFieldData, GetFieldData function [Windows Debugging], WdbgExts_Ref_898dacb4-308c-4a8f-99e2-030adf2b0eae.xml, debugger.getfielddata, wdbgexts/GetFieldData
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
 - GetFieldData
 - wdbgexts/GetFieldData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdbgexts.h
api_name:
 - GetFieldData
---

# GetFieldData function


## -description

The <b>GetFieldData</b> function returns the value of a member in a structure.

## -parameters

### -param TypeAddress 

[in]
Specifies the address of the structure in the target's memory.

### -param Type 

[in]
Specifies the name of the type of the structure.  This can be qualified with a module name, for example, <b>mymodule!mystruct</b>.

### -param Field 

[in]
Specifies the name of the member in the structure whose value will be returned.  Submembers can be specified by using a period-separated path, for example, "myfield.mysubfield".

If the size of the structure pointed to by <i>TypeAddress</i> is less than 8 bytes, <i>Field</i> can be <b>NULL</b>; in this case, the entire structure is copied to <i>pOutValue</i>.

### -param OutSize 

[in]
Specifies the size, in bytes, of the buffer <i>pOutValue</i>.

If <i>OutSize</i> is smaller than the size of the value returned, an error message is printed and an exception is raised; if the exception is handled or ignored, the return value is zero. In this case, the data beyond the end of the buffer referred to by <i>pOutValue</i> might be overwritten.

### -param pOutValue 

[out]
Receives the value of the member.  Or, the value of the type, if <i>Field</i> is <b>NULL</b>.

## -returns

If the function succeeds, the return value is zero. Otherwise, the return value is an <a href="/previous-versions/ff550910(v=vs.85)">IG_DUMP_SYMBOL_INFO error code</a>.