---
UID: NC:dbgeng.PDEBUG_EXTENSION_NOTIFY
title: PDEBUG_EXTENSION_NOTIFY (dbgeng.h)
description: The engine calls the DebugExtensionNotify callback function to inform the extension DLL when a session changes its active or accessible status.C++ CALLBACK* PDEBUG_EXTENSION_NOTIFY DebugExtensionNotify;
old-location: debugger\debugextensionnotify.htm
tech.root: debugger
ms.assetid: 5e877882-00f7-4c46-86e1-debf576ffdb1
ms.date: 05/03/2018
keywords: ["PDEBUG_EXTENSION_NOTIFY callback function"]
ms.keywords: DebugExtensionNotify, DebugExtensionNotify callback function [Windows Debugging], Extensions_Ref_18dd6999-773d-42e8-826a-dcac1fc1ed35.xml, PDEBUG_EXTENSION_NOTIFY, PDEBUG_EXTENSION_NOTIFY callback, dbgeng/DebugExtensionNotify, debugger.debugextensionnotify
f1_keywords:
 - "dbgeng/DebugExtensionNotify"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- dbgeng.h
api_name:
- DebugExtensionNotify
product:
- Windows
targetos: Windows
req.typenames: 
---

# PDEBUG_EXTENSION_NOTIFY callback function


## -description


The engine calls the <b>DebugExtensionNotify</b> callback function to inform the extension <a href="https://docs.microsoft.com/windows-hardware/drivers/">DLL</a> when a session changes its active or accessible status.
<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre> CALLBACK* PDEBUG_EXTENSION_NOTIFY DebugExtensionNotify;</pre>
</td>
</tr>
</table></span></div>

## -parameters




### -param Notify [in]

Can be any of the following values:

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_NOTIFY_SESSION_ACTIVE

</td>
<td>
A debugging session is active.  The session may not necessarily be suspended.

</td>
</tr>
<tr>
<td>
DEBUG_NOTIFY_SESSION_INACTIVE

</td>
<td>
No debugging session is active.

</td>
</tr>
<tr>
<td>
DEBUG_NOTIFY_SESSION_ACCESSIBLE

</td>
<td>
The debugging session has suspended and is now accessible.

</td>
</tr>
<tr>
<td>
DEBUG_NOTIFY_SESSION_INACCESSIBLE

</td>
<td>
The debugging session has started running and is now inaccessible.

</td>
</tr>
</table>
 


### -param Argument [in]

Set to zero. (Reserved for future use.)


## -remarks



This function is optional.  A DbgEng extension DLL only needs to export <b>DebugExtensionNotify</b> if it wants to be notified when the session state changes.  The engine looks for this function by name in the extension DLL.

This function allows the extension DLL to cache information about the session without needing to register explicit callbacks.  It is called at the beginning and end of a session, and each time a target starts or stops executing.

After the extension DLL is initialized, the engine will use this function to notify the DLL if it has started a session.  If the current session is suspended, the engine will call this function a second time to notify the DLL that the session is accessible.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nc-dbgeng-pdebug_extension_initialize">DebugExtensionInitialize</a>
 

 

