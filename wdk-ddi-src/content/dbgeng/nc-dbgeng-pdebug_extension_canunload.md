---
UID: NC:dbgeng.PDEBUG_EXTENSION_CANUNLOAD
title: PDEBUG_EXTENSION_CANUNLOAD
author: windows-driver-content
description: The DebugExtensionCanUnload callback function checks whether a debug extension can unload after the uninitialization call.
old-location: debugger\debugextensioncanunload.htm
old-project: debugger
ms.assetid: 6CF651D7-7F5F-4622-8FDF-8BFF4E4A701D
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: debugger.debugextensioncanunload, DebugExtensionCanUnload, DebugExtensionCanUnload callback function [Windows Debugging], DebugExtensionCanUnload, PDEBUG_EXTENSION_CANUNLOAD, PDEBUG_EXTENSION_CANUNLOAD, dbgeng/DebugExtensionCanUnload
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
-	DebugExtensionCanUnload
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# PDEBUG_EXTENSION_CANUNLOAD callback


## -description


The <i>DebugExtensionCanUnload</i> callback function checks whether a debug extension can unload after the uninitialization call. 
<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre> CALLBACK* PDEBUG_EXTENSION_CANUNLOAD DebugExtensionCanUnload;</pre>
</td>
</tr>
</table></span></div>

## -prototype


````
 CALLBACK* PDEBUG_EXTENSION_CANUNLOAD DebugExtensionCanUnload;
````


## -parameters




### -param void






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


If present, this callback function is called between the <a href="..\dbgeng\nc-dbgeng-pdebug_extension_uninitialize.md">DebugExtensionUninitialize</a> callback function and actual unload of the DLL. The extension should return either <b>S_OK</b>, if no objects are present which would prevent unload of the extension, or <b>S_FALSE</b>, if there are still outstanding references to model objects in the debugger extension.

This callback function is the debugger's equivalent of <a href="https://msdn.microsoft.com/a47df9eb-97cb-4875-a121-1dabe7bc9db6">DllCanUnloadNow</a> for extensions which manipulate the object model of the debugger.

<i>DebugExtensionCanUnload</i> is called <b>PDEBUG_EXTENSION_CANUNLOAD</b> in the Dbgeng.h header file.



## -see-also

<a href="https://msdn.microsoft.com/a47df9eb-97cb-4875-a121-1dabe7bc9db6">DllCanUnloadNow</a>

<a href="..\dbgeng\nc-dbgeng-pdebug_extension_uninitialize.md">DebugExtensionUninitialize</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20PDEBUG_EXTENSION_CANUNLOAD callback function%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

