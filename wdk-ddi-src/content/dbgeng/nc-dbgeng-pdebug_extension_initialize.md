---
UID: NC:dbgeng.PDEBUG_EXTENSION_INITIALIZE
title: PDEBUG_EXTENSION_INITIALIZE (dbgeng.h)
description: The DebugExtensionInitialize callback function is called by the engine after loading a DbgEng extension DLL.C++ CALLBACK* PDEBUG_EXTENSION_INITIALIZE DebugExtensionInitialize;
old-location: debugger\debugextensioninitialize.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["PDEBUG_EXTENSION_INITIALIZE callback function"]
ms.keywords: DebugExtensionInitialize, DebugExtensionInitialize callback function [Windows Debugging], Extensions_Ref_e260c42c-8299-4578-8919-3b2167701275.xml, PDEBUG_EXTENSION_INITIALIZE, PDEBUG_EXTENSION_INITIALIZE callback, dbgeng/DebugExtensionInitialize, debugger.debugextensioninitialize
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
 - PDEBUG_EXTENSION_INITIALIZE
 - dbgeng/PDEBUG_EXTENSION_INITIALIZE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dbgeng.h
api_name:
 - PDEBUG_EXTENSION_INITIALIZE
---

# PDEBUG_EXTENSION_INITIALIZE callback function


## -description

The <b>DebugExtensionInitialize</b> callback function is called by the engine after loading a DbgEng extension DLL.

```cpp
 CALLBACK* PDEBUG_EXTENSION_INITIALIZE DebugExtensionInitialize;
```

## -parameters

### -param Version [out]


Receives the version of the extension.  The high 16 bits contain the major version number, and the low 16 bits contain the minor version number.

### -param Flags [out]


Set this to zero. (Reserved for future use.)

## -returns

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
The extension was successfully initialized.

</td>
</tr>
</table>
 

Any other value indicates that the extension DLL was unable to initialize and the engine will unload it.

## -remarks

The engine looks for this function by name in each extension DLL.  This function must be exported by a DbgEng extension DLL.

The version number can be set by using the macro DEBUG_EXTENSION_VERSION found in dbgeng.h, for example:


```
*Version = DEBUG_EXTENSION_VERSION(Major, Minor)
```

Implementations of this function should initialize any global variables required by the extension DLL.

There may or may not be a session active when this function is called, so the extension should not assume that it is able to query session information.

 The function type is defined as PDEBUG_EXTENSION_INITIALIZE in dbgeng.h.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nc-dbgeng-pdebug_extension_notify">DebugExtensionNotify</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nc-dbgeng-pdebug_extension_uninitialize">DebugExtensionUninitialize</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nc-dbgeng-pdebug_extension_known_struct">KnownStructOutput</a>

