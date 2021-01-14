---
UID: NC:dbgeng.PDEBUG_EXTENSION_UNLOAD
title: PDEBUG_EXTENSION_UNLOAD (dbgeng.h)
description: The DebugExtensionUnload callback function unloads the debug extension.
old-location: debugger\debugextensionunload.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["PDEBUG_EXTENSION_UNLOAD callback function"]
ms.keywords: DebugExtensionUnload, DebugExtensionUnload callback function [Windows Debugging], PDEBUG_EXTENSION_UNLOAD, PDEBUG_EXTENSION_UNLOAD callback, dbgeng/DebugExtensionUnload, debugger.debugextensionunload
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
req.typenames: 
f1_keywords:
 - PDEBUG_EXTENSION_UNLOAD
 - dbgeng/PDEBUG_EXTENSION_UNLOAD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Dbgeng.h
api_name:
 - PDEBUG_EXTENSION_UNLOAD
---

# PDEBUG_EXTENSION_UNLOAD callback function


## -description

The <i>DebugExtensionUnload</i> callback function unloads the debug extension. 

```cpp
 CALLBACK* PDEBUG_EXTENSION_UNLOAD DebugExtensionUnload;
```

## -parameters

### -param Arg1

## -remarks

If and only if <a href="/windows-hardware/drivers/ddi/dbgeng/nc-dbgeng-pdebug_extension_canunload">DebugExtensionCanUnload</a> is present in the debugger extension, this callback function is called after a successful <i>DebugExtensionCanUnload</i> call, immediately before the debugger actually unloads the extension DLL.

<i>DebugExtensionUnload</i> is called <b>PDEBUG_EXTENSION_UNLOAD</b> in the Dbgeng.h header file.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nc-dbgeng-pdebug_extension_canunload">DebugExtensionCanUnload</a>

