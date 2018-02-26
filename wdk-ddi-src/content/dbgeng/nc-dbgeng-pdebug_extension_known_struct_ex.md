---
UID: NC:dbgeng.PDEBUG_EXTENSION_KNOWN_STRUCT_EX
title: PDEBUG_EXTENSION_KNOWN_STRUCT_EX
author: windows-driver-content
description: The DebugExtensionKnownStructEx callback function is called by extensions in order to dump structures that are well known to them.
old-location: debugger\debugextensionknownstructex.htm
old-project: debugger
ms.assetid: 830BCD4C-0C3A-45F8-84E9-4F8596B8E1E8
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: DebugExtensionKnownStructEx, DebugExtensionKnownStructEx callback function [Windows Debugging], PDEBUG_EXTENSION_KNOWN_STRUCT_EX, dbgeng/DebugExtensionKnownStructEx, debugger.debugextensionknownstructex
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
-	DebugExtensionKnownStructEx
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# PDEBUG_EXTENSION_KNOWN_STRUCT_EX callback


## -description


The <i>DebugExtensionKnownStructEx</i> callback function is called by extensions in order to dump structures that are well known to them. 
<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre> CALLBACK* PDEBUG_EXTENSION_KNOWN_STRUCT_EX DebugExtensionKnownStructEx;</pre>
</td>
</tr>
</table></span></div>

## -prototype


````
 CALLBACK* PDEBUG_EXTENSION_KNOWN_STRUCT_EX DebugExtensionKnownStructEx;
````


## -parameters




### -param Client [in]

A debug client.


### -param Flags [in]

Flags.


### -param Offset [in]

An offset.


### -param TypeName [in, optional]

The name of a type.


### -param Buffer [out, optional]

An output buffer.


### -param BufferChars [in, out, optional]

A pointer to the length of the output buffer. 


## -returns



If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



<i>DebugExtensionKnownStructEx</i> is called <b>PDEBUG_EXTENSION_KNOWN_STRUCT_EX</b> in the Dbgeng.h header file.



