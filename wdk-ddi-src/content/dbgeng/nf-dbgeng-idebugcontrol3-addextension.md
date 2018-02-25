---
UID: NF:dbgeng.IDebugControl3.AddExtension
title: IDebugControl3::AddExtension method
author: windows-driver-content
description: The AddExtension method loads an extension library into the debugger engine.
old-location: debugger\addextension.htm
old-project: debugger
ms.assetid: 67dbc01a-83ee-4c7c-921e-f0945fbcc2ef
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., 3, :, A, AddExtension method [Windows Debugging], AddExtension method [Windows Debugging], IDebugControl interface, AddExtension method [Windows Debugging], IDebugControl2 interface, AddExtension method [Windows Debugging], IDebugControl3 interface, AddExtension,IDebugControl.AddExtension, AddExtension,IDebugControl2.AddExtension, AddExtension,IDebugControl3.AddExtension, C, D, E, I, IDebugControl, IDebugControl interface [Windows Debugging], AddExtension method, IDebugControl2, IDebugControl2 interface [Windows Debugging], AddExtension method, IDebugControl2::AddExtension, IDebugControl3, IDebugControl3 interface [Windows Debugging], AddExtension method, IDebugControl3::AddExtension, IDebugControl::AddExtension, IDebugControl_9d85fcbb-1c02-4b5a-b9ab-c50b9b266d1d.xml, b, d, dbgeng/IDebugControl2::AddExtension, dbgeng/IDebugControl3::AddExtension, dbgeng/IDebugControl::AddExtension, debugger.addextension, e, g, i, l, n, o, r, s, t, u, x"
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Dbgeng.h
apiname:
-	IDebugControl.AddExtension
-	IDebugControl2.AddExtension
-	IDebugControl3.AddExtension
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl3::AddExtension method


## -description


The <b>AddExtension</b>  method loads an extension library into the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a>.


## -syntax


````
HRESULT AddExtension(
  [in]  PCSTR    Path,
  [in]  ULONG    Flags,
  [out] PULONG64 Handle
);
````


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

<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546717">GetExtensionByPath</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554497">RemoveExtension</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::AddExtension method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

