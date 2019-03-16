---
UID: NF:dbgeng.IDebugControl3.AddExtension
title: IDebugControl3::AddExtension (dbgeng.h)
description: The AddExtension method loads an extension library into the debugger engine.
old-location: debugger\addextension.htm
tech.root: debugger
ms.assetid: 67dbc01a-83ee-4c7c-921e-f0945fbcc2ef
ms.date: 05/03/2018
ms.keywords: AddExtension, AddExtension method [Windows Debugging], AddExtension method [Windows Debugging],IDebugControl interface, AddExtension method [Windows Debugging],IDebugControl2 interface, AddExtension method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],AddExtension method, IDebugControl2 interface [Windows Debugging],AddExtension method, IDebugControl2::AddExtension, IDebugControl3 interface [Windows Debugging],AddExtension method, IDebugControl3.AddExtension, IDebugControl3::AddExtension, IDebugControl::AddExtension, IDebugControl_9d85fcbb-1c02-4b5a-b9ab-c50b9b266d1d.xml, dbgeng/IDebugControl2::AddExtension, dbgeng/IDebugControl3::AddExtension, dbgeng/IDebugControl::AddExtension, debugger.addextension
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Dbgeng.h
api_name:
- IDebugControl.AddExtension
- IDebugControl2.AddExtension
- IDebugControl3.AddExtension
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl3::AddExtension


## -description


The <b>AddExtension</b>  method loads an extension library into the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a>.


## -parameters




### -param Path [in]

Specifies the fully qualified path and file name of the extension library to load.


### -param Flags [in]

Set to zero.


### -param Handle [out]

Receives the handle of the loaded extension library.


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



If the extension library has already been loaded, the handle to already loaded library is returned.  The extension library is not loaded again.

The extension library is loaded into the host engine and <i>Path</i> contains a path and file name for this instance of the debugger engine.

For more information on using extension libraries, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539033">Calling Extensions and Extension Functions</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546717">GetExtensionByPath</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554497">RemoveExtension</a>
 

 

