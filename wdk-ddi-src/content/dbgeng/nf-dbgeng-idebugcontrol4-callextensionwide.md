---
UID: NF:dbgeng.IDebugControl4.CallExtensionWide
title: IDebugControl4::CallExtensionWide method
author: windows-driver-content
description: The CallExtensionWide method calls a debugger extension.
old-location: debugger\callextensionwide.htm
old-project: debugger
ms.assetid: a46d7ba9-24fc-4e06-9655-3fc6531d6891
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: CallExtensionWide method [Windows Debugging], CallExtensionWide method [Windows Debugging], IDebugControl4 interface, CallExtensionWide,IDebugControl4.CallExtensionWide, IDebugControl4, IDebugControl4 interface [Windows Debugging], CallExtensionWide method, IDebugControl4::CallExtensionWide, dbgeng/IDebugControl4::CallExtensionWide, debugger.callextensionwide
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugControl4.CallExtensionWide
product:
- Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl4::CallExtensionWide method


## -description


The <b>CallExtensionWide</b> method calls a debugger extension.


## -parameters




### -param Handle [in]

Specifies the handle of the extension library that contains the extension to call.  If <i>Handle</i> is zero, the engine will walk the extension library chain searching for the extension.


### -param Function [in]

Specifies the name of the extension to call.


### -param Arguments [in, optional]

Specifies the arguments to pass to the extension.  <i>Arguments</i> is a string that will be parsed by the extension, just like the extension will parse arguments passed to it when called as an extension command.


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
The method was successful.

</td>
</tr>
</table>
 

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.




## -remarks



If <i>Handle</i> is zero, the engine searches each extension library until it finds one that contains the extension; the extension will then be called.  If the extension returns DEBUG_EXTENSION_CONTINUE_SEARCH, the search will continue.

For more information on using extension libraries, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539033">Calling Extensions and Extension Functions</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537892">AddExtension</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546717">GetExtensionByPath</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546733">GetExtensionFunction</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550526">IDebugControl4</a>
 

 

