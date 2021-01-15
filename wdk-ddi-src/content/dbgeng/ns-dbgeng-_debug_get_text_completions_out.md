---
UID: NS:dbgeng._DEBUG_GET_TEXT_COMPLETIONS_OUT
title: _DEBUG_GET_TEXT_COMPLETIONS_OUT (dbgeng.h)
description: Defines information about text completions to get.
old-location: debugger\debug_get_text_completions_out.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["DEBUG_GET_TEXT_COMPLETIONS_OUT structure"]
ms.keywords: "*PDEBUG_GET_TEXT_COMPLETIONS_OUT, DEBUG_GET_TEXT_COMPLETIONS_IS_DOT_COMMAND, DEBUG_GET_TEXT_COMPLETIONS_IS_EXTENSION_COMMAND, DEBUG_GET_TEXT_COMPLETIONS_IS_SYMBOL, DEBUG_GET_TEXT_COMPLETIONS_OUT, DEBUG_GET_TEXT_COMPLETIONS_OUT structure [Windows Debugging], PDEBUG_GET_TEXT_COMPLETIONS_OUT, PDEBUG_GET_TEXT_COMPLETIONS_OUT structure pointer [Windows Debugging], _DEBUG_GET_TEXT_COMPLETIONS_OUT, dbgeng/DEBUG_GET_TEXT_COMPLETIONS_OUT, dbgeng/PDEBUG_GET_TEXT_COMPLETIONS_OUT, debugger.debug_get_text_completions_out"
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
req.typenames: DEBUG_GET_TEXT_COMPLETIONS_OUT, *PDEBUG_GET_TEXT_COMPLETIONS_OUT
f1_keywords:
 - _DEBUG_GET_TEXT_COMPLETIONS_OUT
 - dbgeng/_DEBUG_GET_TEXT_COMPLETIONS_OUT
 - PDEBUG_GET_TEXT_COMPLETIONS_OUT
 - dbgeng/PDEBUG_GET_TEXT_COMPLETIONS_OUT
 - DEBUG_GET_TEXT_COMPLETIONS_OUT
 - dbgeng/DEBUG_GET_TEXT_COMPLETIONS_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - DbgEng.h
api_name:
 - _DEBUG_GET_TEXT_COMPLETIONS_OUT
 - PDEBUG_GET_TEXT_COMPLETIONS_OUT
 - DEBUG_GET_TEXT_COMPLETIONS_OUT
---

# _DEBUG_GET_TEXT_COMPLETIONS_OUT structure


## -description

Defines information about text completions to get.

## -struct-fields

### -field Flags

Flags. Valid flag values include the following:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="DEBUG_GET_TEXT_COMPLETIONS_IS_DOT_COMMAND"></a><a id="debug_get_text_completions_is_dot_command"></a><dl>
<dt><b>DEBUG_GET_TEXT_COMPLETIONS_IS_DOT_COMMAND</b></dt>
<dt>0x00000001</dt>
</dl>
</td>
<td width="60%">
Is dot command. Dot commands begin with a period (.).

</td>
</tr>
<tr>
<td width="40%"><a id="DEBUG_GET_TEXT_COMPLETIONS_IS_EXTENSION_COMMAND"></a><a id="debug_get_text_completions_is_extension_command"></a><dl>
<dt><b>DEBUG_GET_TEXT_COMPLETIONS_IS_EXTENSION_COMMAND</b></dt>
<dt>0x00000002</dt>
</dl>
</td>
<td width="60%">
Is extension command.

</td>
</tr>
<tr>
<td width="40%"><a id="DEBUG_GET_TEXT_COMPLETIONS_IS_SYMBOL"></a><a id="debug_get_text_completions_is_symbol"></a><dl>
<dt><b>DEBUG_GET_TEXT_COMPLETIONS_IS_SYMBOL</b></dt>
<dt>0x00000004</dt>
</dl>
</td>
<td width="60%">
Is symbol.

</td>
</tr>
</table>

### -field ReplaceIndex

The index of the replace location.

### -field MatchCount

Count value of matches.

### -field Reserved1

Reserved.

### -field Reserved2

Reserved.

