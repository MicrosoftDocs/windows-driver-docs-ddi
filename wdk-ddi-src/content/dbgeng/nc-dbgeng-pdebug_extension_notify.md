---
UID: NC:dbgeng.PDEBUG_EXTENSION_NOTIFY
title: PDEBUG_EXTENSION_NOTIFY
author: windows-driver-content
description: The engine calls the DebugExtensionNotify callback function to inform the extension DLL when a session changes its active or accessible status.C++ CALLBACK* PDEBUG_EXTENSION_NOTIFY DebugExtensionNotify;
old-location: debugger\debugextensionnotify.htm
old-project: debugger
ms.assetid: 5e877882-00f7-4c46-86e1-debf576ffdb1
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _DOT4_ACTIVITY, *PDOT4_ACTIVITY, DOT4_ACTIVITY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dbgeng.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DebugExtensionNotify
req.alt-loc: dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# PDEBUG_EXTENSION_NOTIFY callback



## -description
The engine calls the <b>DebugExtensionNotify</b> callback function to inform the extension <a href="wdkgloss.d#wdkgloss.dll#wdkgloss.dll"><i>DLL</i></a> when a session changes its active or accessible status.



## -prototype

````
 CALLBACK* PDEBUG_EXTENSION_NOTIFY DebugExtensionNotify;
````


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


## -returns
This callback function does not return a value.


## -remarks
This function is optional.  A DbgEng extension DLL only needs to export <b>DebugExtensionNotify</b> if it wants to be notified when the session state changes.  The engine looks for this function by name in the extension DLL.

This function allows the extension DLL to cache information about the session without needing to register explicit callbacks.  It is called at the beginning and end of a session, and each time a target starts or stops executing.

After the extension DLL is initialized, the engine will use this function to notify the DLL if it has started a session.  If the current session is suspended, the engine will call this function a second time to notify the DLL that the session is accessible.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nc-dbgeng-pdebug_extension_initialize.md">DebugExtensionInitialize</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20PDEBUG_EXTENSION_NOTIFY callback function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

