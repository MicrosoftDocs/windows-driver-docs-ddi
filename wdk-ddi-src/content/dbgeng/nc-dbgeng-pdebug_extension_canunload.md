---
UID: NC:dbgeng.PDEBUG_EXTENSION_CANUNLOAD
title: PDEBUG_EXTENSION_CANUNLOAD
author: windows-driver-content
description: The DebugExtensionCanUnload callback function checks whether a debug extension can unload after the uninitialization call.
old-location: debugger\debugextensioncanunload.htm
old-project: debugger
ms.assetid: 6CF651D7-7F5F-4622-8FDF-8BFF4E4A701D
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _DOT4_ACTIVITY, *PDOT4_ACTIVITY, DOT4_ACTIVITY
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
req.alt-api: DebugExtensionCanUnload
req.alt-loc: Dbgeng.h
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

# PDEBUG_EXTENSION_CANUNLOAD callback



## -description
The <i>DebugExtensionCanUnload</i> callback function checks whether a debug extension can unload after the uninitialization call. 



## -prototype

````
 CALLBACK* PDEBUG_EXTENSION_CANUNLOAD DebugExtensionCanUnload;
````


## -parameters


## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl>The extension was successfully initialized.

 

Any other value indicates that the extension DLL was unable to initialize and the engine will unload it.
<dl>
<dt><b>S_OK</b></dt>
</dl>The extension was successfully initialized.

 

Any other value indicates that the extension DLL was unable to initialize and the engine will unload it.
<dl>
<dt><b>S_OK</b></dt>
</dl>The extension was successfully initialized.

 

Any other value indicates that the extension DLL was unable to initialize and the engine will unload it.


## -remarks
If present, this callback function is called between the <a href="..\dbgeng\nc-dbgeng-pdebug_extension_uninitialize.md">DebugExtensionUninitialize</a> callback function and actual unload of the DLL. The extension should return either <b>S_OK</b>, if no objects are present which would prevent unload of the extension, or <b>S_FALSE</b>, if there are still outstanding references to model objects in the debugger extension.

This callback function is the debugger's equivalent of <a href="https://msdn.microsoft.com/a47df9eb-97cb-4875-a121-1dabe7bc9db6">DllCanUnloadNow</a> for extensions which manipulate the object model of the debugger.

<i>DebugExtensionCanUnload</i> is called <b>PDEBUG_EXTENSION_CANUNLOAD</b> in the Dbgeng.h header file.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nc-dbgeng-pdebug_extension_uninitialize.md">DebugExtensionUninitialize</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/a47df9eb-97cb-4875-a121-1dabe7bc9db6">DllCanUnloadNow</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20PDEBUG_EXTENSION_CANUNLOAD callback function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

