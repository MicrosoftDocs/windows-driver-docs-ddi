---
UID: NC:dbgeng.PDEBUG_EXTENSION_UNLOAD
title: PDEBUG_EXTENSION_UNLOAD
author: windows-driver-content
description: The DebugExtensionUnload callback function unloads the debug extension.
old-location: debugger\debugextensionunload.htm
old-project: debugger
ms.assetid: 8F83F94E-CF4F-4709-A860-DDF1850A7264
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: DebugExtensionUnload, DebugExtensionUnload callback function [Windows Debugging], PDEBUG_EXTENSION_UNLOAD, dbgeng/DebugExtensionUnload, debugger.debugextensionunload
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Dbgeng.h
apiname:
-	DebugExtensionUnload
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# PDEBUG_EXTENSION_UNLOAD callback


## -description


The <i>DebugExtensionUnload</i> callback function unloads the debug extension. 
<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre> CALLBACK* PDEBUG_EXTENSION_UNLOAD DebugExtensionUnload;</pre>
</td>
</tr>
</table></span></div>

## -prototype


````
 CALLBACK* PDEBUG_EXTENSION_UNLOAD DebugExtensionUnload;
````


## -parameters




### -param void








## -returns



This callback function does not return a value.




## -remarks



If and only if <a href="..\dbgeng\nc-dbgeng-pdebug_extension_canunload.md">DebugExtensionCanUnload</a> is present in the debugger extension, this callback function is called after a successful <i>DebugExtensionCanUnload</i> call, immediately before the debugger actually unloads the extension DLL.

<i>DebugExtensionUnload</i> is called <b>PDEBUG_EXTENSION_UNLOAD</b> in the Dbgeng.h header file.




## -see-also

<a href="..\dbgeng\nc-dbgeng-pdebug_extension_canunload.md">DebugExtensionCanUnload</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20PDEBUG_EXTENSION_UNLOAD callback function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

