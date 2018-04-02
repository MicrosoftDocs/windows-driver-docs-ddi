---
UID: NF:dbgeng.IDebugControl3.RemoveExtension
title: IDebugControl3::RemoveExtension method
author: windows-driver-content
description: The RemoveExtension method unloads an extension library.
old-location: debugger\removeextension.htm
old-project: debugger
ms.assetid: ba4a87cc-2412-4769-9694-d6eefd750c4b
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: IDebugControl interface [Windows Debugging], RemoveExtension method, IDebugControl2 interface [Windows Debugging], RemoveExtension method, IDebugControl2::RemoveExtension, IDebugControl3, IDebugControl3 interface [Windows Debugging], RemoveExtension method, IDebugControl3::RemoveExtension, IDebugControl::RemoveExtension, IDebugControl_c762281b-f49c-4837-a524-e2f04edb3b0c.xml, RemoveExtension method [Windows Debugging], RemoveExtension method [Windows Debugging], IDebugControl interface, RemoveExtension method [Windows Debugging], IDebugControl2 interface, RemoveExtension method [Windows Debugging], IDebugControl3 interface, RemoveExtension,IDebugControl3.RemoveExtension, dbgeng/IDebugControl2::RemoveExtension, dbgeng/IDebugControl3::RemoveExtension, dbgeng/IDebugControl::RemoveExtension, debugger.removeextension
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
-	IDebugControl.RemoveExtension
-	IDebugControl2.RemoveExtension
-	IDebugControl3.RemoveExtension
product:
- Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl3::RemoveExtension method


## -description


The <b>RemoveExtension</b> method unloads an extension library.


## -parameters




### -param Handle [in]

Specifies the handle of the extension library to unload.  This is the handle returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff537892">AddExtension</a>.


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



For more information on using extension libraries, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539033">Calling Extensions and Extension Functions</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537892">AddExtension</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>
 

 

