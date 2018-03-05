---
UID: NF:dbgeng.IDebugControl.RemoveExtension
title: IDebugControl::RemoveExtension method
author: windows-driver-content
description: The RemoveExtension method unloads an extension library.
old-location: debugger\removeextension.htm
old-project: debugger
ms.assetid: ba4a87cc-2412-4769-9694-d6eefd750c4b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IDebugControl, IDebugControl interface [Windows Debugging], RemoveExtension method, IDebugControl2 interface [Windows Debugging], RemoveExtension method, IDebugControl2::RemoveExtension, IDebugControl3 interface [Windows Debugging], RemoveExtension method, IDebugControl3::RemoveExtension, IDebugControl::RemoveExtension, IDebugControl_c762281b-f49c-4837-a524-e2f04edb3b0c.xml, RemoveExtension method [Windows Debugging], RemoveExtension method [Windows Debugging], IDebugControl interface, RemoveExtension method [Windows Debugging], IDebugControl2 interface, RemoveExtension method [Windows Debugging], IDebugControl3 interface, RemoveExtension,IDebugControl.RemoveExtension, dbgeng/IDebugControl2::RemoveExtension, dbgeng/IDebugControl3::RemoveExtension, dbgeng/IDebugControl::RemoveExtension, debugger.removeextension
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
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl::RemoveExtension method


## -description


The <b>RemoveExtension</b> method unloads an extension library.


## -syntax


````
HRESULT RemoveExtension(
  [in] ULONG64 Handle
);
````


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



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::RemoveExtension method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

