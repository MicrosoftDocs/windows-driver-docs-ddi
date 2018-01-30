---
UID: NF:dbgeng.IDebugControl4.GetExtensionFunctionWide
title: IDebugControl4::GetExtensionFunctionWide method
author: windows-driver-content
description: The GetExtensionFunctionWide method returns a pointer to an extension function from an extension library.
old-location: debugger\getextensionfunctionwide.htm
old-project: debugger
ms.assetid: 351859d5-89fb-4756-a75b-fd4048cb20ef
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugControl4::GetExtensionFunctionWide, dbgeng/IDebugControl4::GetExtensionFunctionWide, IDebugControl4, GetExtensionFunctionWide method [Windows Debugging], debugger.getextensionfunctionwide, IDebugControl4 interface [Windows Debugging], GetExtensionFunctionWide method, GetExtensionFunctionWide, GetExtensionFunctionWide method [Windows Debugging], IDebugControl4 interface
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
-	dbgeng.h
apiname:
-	IDebugControl4.GetExtensionFunctionWide
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_GETENCRYPTIONBLTKEY
---

# IDebugControl4::GetExtensionFunctionWide method


## -description


The <b>GetExtensionFunctionWide</b>  method returns a pointer to an extension function from an extension library.


## -syntax


````
HRESULT GetExtensionFunctionWide(
  [in]  ULONG64 Handle,
  [in]  PCWSTR  FuncName,
  [out] FARPROC *Function
);
````


## -parameters




### -param Handle [in]

Specifies the handle of the extension library that contains the extension function.  If <i>Handle</i> is zero, the engine will walk the extension library chain searching for the extension function.


### -param FuncName [in]

Specifies the name of the extension function to return.  When searching the extension libraries for the function, the debugger engine will prepend "_EFN_" to the name.  For example, if <i>FuncName</i> is "SampleFunction", the engine will search the extension libraries for "_EFN_SampleFunction".


### -param Function [out]

Receives the extension function.


## -returns


This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
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



## -remarks


Extension libraries are loaded into the host engine and extension functions cannot be called remotely.  The current client must not be a debugging client, it must belong to the host engine.

The extension function can have any function prototype.  In order for any program to call this extension function, the extension function should be cast to the correct prototype.

For more information on using extension functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539033">Calling Extensions and Extension Functions</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546717">GetExtensionByPath</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539023">CallExtension</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol4.md">IDebugControl4</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537892">AddExtension</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl4::GetExtensionFunctionWide method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

