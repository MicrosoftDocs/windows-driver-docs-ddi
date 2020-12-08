---
UID: NC:dbgeng.PDEBUG_EXTENSION_QUERY_VALUE_NAMES
title: PDEBUG_EXTENSION_QUERY_VALUE_NAMES (dbgeng.h)
description: The DebugExtensionQueryValueNames callback function recovers pseudo-register values.C++ CALLBACK* PDEBUG_EXTENSION_QUERY_VALUE_NAMES DebugExtensionQueryValueNames;
old-location: debugger\debugextensionqueryvaluenames.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["PDEBUG_EXTENSION_QUERY_VALUE_NAMES callback function"]
ms.keywords: DebugExtensionQueryValueNames, DebugExtensionQueryValueNames callback function [Windows Debugging], Extensions_Ref_d06137e2-2d0a-4760-b5f6-2f03355f8c07.xml, PDEBUG_EXTENSION_QUERY_VALUE_NAMES, PDEBUG_EXTENSION_QUERY_VALUE_NAMES callback, dbgeng/DebugExtensionQueryValueNames, debugger.debugextensionqueryvaluenames
req.header: dbgeng.h
req.include-header: 
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
 - PDEBUG_EXTENSION_QUERY_VALUE_NAMES
 - dbgeng/PDEBUG_EXTENSION_QUERY_VALUE_NAMES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Dbgeng.h
api_name:
 - DebugExtensionQueryValueNames
---

# PDEBUG_EXTENSION_QUERY_VALUE_NAMES callback function


## -description

The <b>DebugExtensionQueryValueNames</b> callback function recovers <a href="/windows-hardware/drivers/debugger/registers">pseudo-register</a> values.

```cpp
 CALLBACK* PDEBUG_EXTENSION_QUERY_VALUE_NAMES DebugExtensionQueryValueNames;
```


## -parameters

### -param Client 

[in]
A client to use if the extension needs DbgEng functions.

### -param Flags 

[in]
Provides behavioral flags. This parameter is currently reserved.

### -param Buffer 

[out]
A string buffer that the caller provides, to be filled with the set of value names that the client wants to expose.

### -param BufferChars 

[in]
The count of wide characters in <i>Buffer</i>.

### -param BufferNeeded 

[out]
The number of wide characters that this function needs to complete successfully.

## -returns

<b>DebugExtensionQueryValueNames</b> might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The function was successfully completed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The function completed without error, but it obtained only partial results.

</td>
</tr>
</table>
 

This function might also return error values.  For more information about possible return values, see <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a>.

## -remarks

Value names must start with <b>$$</b> and have a terminating NULL character. The <i>Buffer</i> string must also be NULL-terminated. For example, <i>Buffer</i> could be "$$myval1\0$$myval2\0\0".

<i>DebugExtensionQueryValueNames</i> is called <b>PDEBUG_EXTENSION_QUERY_VALUE_NAMES</b> in the Dbgeng.h header file.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nc-dbgeng-pdebug_extension_initialize">DebugExtensionInitialize</a>



<i>DebugExtensionNotify</i>



<i>DebugExtensionProvideValue</i>



<i>DebugExtensionUninitialize</i>



<i>KnownStructOutput</i>
