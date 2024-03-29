---
UID: NC:dbgeng.PDEBUG_EXTENSION_UNINITIALIZE
title: PDEBUG_EXTENSION_UNINITIALIZE (dbgeng.h)
description: The DebugExtensionUninitialize callback function is called by the engine to uninitialize the DbgEng extension DLL before it is unloaded.
old-location: debugger\debugextensionuninitialize.htm
tech.root: debugger
ms.date: 08/10/2023
keywords: ["PDEBUG_EXTENSION_UNINITIALIZE callback function"]
ms.keywords: DebugExtensionUninitialize, DebugExtensionUninitialize callback function [Windows Debugging], Extensions_Ref_76594e24-5f2d-495f-b8a9-6acec1f21ba4.xml, PDEBUG_EXTENSION_UNINITIALIZE, PDEBUG_EXTENSION_UNINITIALIZE callback, dbgeng/DebugExtensionUninitialize, debugger.debugextensionuninitialize
req.header: dbgeng.h
req.include-header: 
req.target-type: Universal
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
 - PDEBUG_EXTENSION_UNINITIALIZE
 - dbgeng/PDEBUG_EXTENSION_UNINITIALIZE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dbgeng.h
api_name:
 - PDEBUG_EXTENSION_UNINITIALIZE
---

# PDEBUG_EXTENSION_UNINITIALIZE callback function

## -description

The <b>DebugExtensionUninitialize</b> callback function is called by the engine to uninitialize the DbgEng extension DLL before it is unloaded.

```
 CALLBACK* PDEBUG_EXTENSION_UNINITIALIZE DebugExtensionUninitialize;
```

## -remarks

This function is optional.  A DbgEng extension DLL only needs to export <b>DebugExtensionUninitialize</b> if it needs to be notified before it is unloaded.  The engine looks for this function by name in the extension DLL.

This function can be used by the extension DLL to clean up before it is unloaded.

There may or may not be a session active when this function is called, so the extension should not assume that it is able to query session information.

DebugExtensionUninitialize is called <b>PDEBUG_EXTENSION_UNINITIALIZE</b> in the Dbgeng.h header file.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nc-dbgeng-pdebug_extension_initialize">DebugExtensionInitialize</a>

