---
UID: NF:dbgeng.IDebugControl3.GetExtensionFunction
title: IDebugControl3::GetExtensionFunction (dbgeng.h)
description: The GetExtensionFunction method returns a pointer to an extension function from an extension library.
old-location: debugger\getextensionfunction.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugControl3::GetExtensionFunction"]
ms.keywords: GetExtensionFunction, GetExtensionFunction method [Windows Debugging], GetExtensionFunction method [Windows Debugging],IDebugControl interface, GetExtensionFunction method [Windows Debugging],IDebugControl2 interface, GetExtensionFunction method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetExtensionFunction method, IDebugControl2 interface [Windows Debugging],GetExtensionFunction method, IDebugControl2::GetExtensionFunction, IDebugControl3 interface [Windows Debugging],GetExtensionFunction method, IDebugControl3.GetExtensionFunction, IDebugControl3::GetExtensionFunction, IDebugControl::GetExtensionFunction, IDebugControl_9f227e3a-ee1e-44d0-9675-ec773e3391e5.xml, dbgeng/IDebugControl2::GetExtensionFunction, dbgeng/IDebugControl3::GetExtensionFunction, dbgeng/IDebugControl::GetExtensionFunction, debugger.getextensionfunction
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IDebugControl3::GetExtensionFunction
 - dbgeng/IDebugControl3::GetExtensionFunction
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl.GetExtensionFunction
 - IDebugControl2.GetExtensionFunction
 - IDebugControl3.GetExtensionFunction
---

# IDebugControl3::GetExtensionFunction


## -description

The <b>GetExtensionFunction</b>  method returns a pointer to an extension function from an extension library.

## -parameters

### -param Handle 

[in]
Specifies the handle of the extension library that contains the extension function.  If <i>Handle</i> is zero, the engine will walk the extension library chain searching for the extension function.

### -param FuncName 

[in]
Specifies the name of the extension function to return.  When searching the extension libraries for the function, the debugger engine will prepend "_EFN_" to the name.  For example, if <i>FuncName</i> is "SampleFunction", the engine will search the extension libraries for "_EFN_SampleFunction".

### -param Function 

[out]
Receives the extension function.

## -returns

This method can also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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

For more information on using extension functions, see <a href="/windows-hardware/drivers/debugger/calling-extensions-and-extension-functions">Calling Extensions and Extension Functions</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-addextension">AddExtension</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-callextension">CallExtension</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getextensionbypath">GetExtensionByPath</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>
