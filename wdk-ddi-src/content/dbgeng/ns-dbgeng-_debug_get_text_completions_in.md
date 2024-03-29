---
UID: NS:dbgeng._DEBUG_GET_TEXT_COMPLETIONS_IN
title: _DEBUG_GET_TEXT_COMPLETIONS_IN (dbgeng.h)
description: The _DEBUG_GET_TEXT_COMPLETIONS_IN structure defines information about the type of text completions to get.
old-location: debugger\debug_get_text_completions_in.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["DEBUG_GET_TEXT_COMPLETIONS_IN structure"]
ms.keywords: "*PDEBUG_GET_TEXT_COMPLETIONS_IN, DEBUG_GET_TEXT_COMPLETIONS_IN, DEBUG_GET_TEXT_COMPLETIONS_IN structure [Windows Debugging], DEBUG_GET_TEXT_COMPLETIONS_NO_DOT_COMMANDS, DEBUG_GET_TEXT_COMPLETIONS_NO_EXTENSION_COMMANDS, DEBUG_GET_TEXT_COMPLETIONS_NO_SYMBOLS, PDEBUG_GET_TEXT_COMPLETIONS_IN, PDEBUG_GET_TEXT_COMPLETIONS_IN structure pointer [Windows Debugging], _DEBUG_GET_TEXT_COMPLETIONS_IN, dbgeng/DEBUG_GET_TEXT_COMPLETIONS_IN, dbgeng/PDEBUG_GET_TEXT_COMPLETIONS_IN, debugger.debug_get_text_completions_in"
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
req.typenames: DEBUG_GET_TEXT_COMPLETIONS_IN, *PDEBUG_GET_TEXT_COMPLETIONS_IN
f1_keywords:
 - _DEBUG_GET_TEXT_COMPLETIONS_IN
 - dbgeng/_DEBUG_GET_TEXT_COMPLETIONS_IN
 - PDEBUG_GET_TEXT_COMPLETIONS_IN
 - dbgeng/PDEBUG_GET_TEXT_COMPLETIONS_IN
 - DEBUG_GET_TEXT_COMPLETIONS_IN
 - dbgeng/DEBUG_GET_TEXT_COMPLETIONS_IN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - DbgEng.h
api_name:
 - _DEBUG_GET_TEXT_COMPLETIONS_IN
 - PDEBUG_GET_TEXT_COMPLETIONS_IN
 - DEBUG_GET_TEXT_COMPLETIONS_IN
---

# _DEBUG_GET_TEXT_COMPLETIONS_IN structure


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
<td width="40%"><a id="DEBUG_GET_TEXT_COMPLETIONS_NO_DOT_COMMANDS"></a><a id="debug_get_text_completions_no_dot_commands"></a><dl>
<dt><b>DEBUG_GET_TEXT_COMPLETIONS_NO_DOT_COMMANDS</b></dt>
<dt>0x00000001</dt>
</dl>
</td>
<td width="60%">
Do not include dot commands. Dot commands begin with a period (.).

</td>
</tr>
<tr>
<td width="40%"><a id="DEBUG_GET_TEXT_COMPLETIONS_NO_EXTENSION_COMMANDS"></a><a id="debug_get_text_completions_no_extension_commands"></a><dl>
<dt><b>DEBUG_GET_TEXT_COMPLETIONS_NO_EXTENSION_COMMANDS</b></dt>
<dt>0x00000002</dt>
</dl>
</td>
<td width="60%">
Do not include extension commands. 

</td>
</tr>
<tr>
<td width="40%"><a id="DEBUG_GET_TEXT_COMPLETIONS_NO_SYMBOLS"></a><a id="debug_get_text_completions_no_symbols"></a><dl>
<dt><b>DEBUG_GET_TEXT_COMPLETIONS_NO_SYMBOLS</b></dt>
<dt>0x00000004</dt>
</dl>
</td>
<td width="60%">
Do not include completions with symbols.

</td>
</tr>
</table>

### -field MatchCountLimit

The limit of matches.

### -field Reserved

Reserved.

