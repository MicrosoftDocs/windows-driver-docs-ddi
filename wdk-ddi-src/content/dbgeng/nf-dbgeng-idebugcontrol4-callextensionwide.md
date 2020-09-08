---
UID: NF:dbgeng.IDebugControl4.CallExtensionWide
title: IDebugControl4::CallExtensionWide (dbgeng.h)
description: The CallExtensionWide method calls a debugger extension.
old-location: debugger\callextensionwide.htm
tech.root: debugger
ms.assetid: a46d7ba9-24fc-4e06-9655-3fc6531d6891
ms.date: 05/03/2018
keywords: ["IDebugControl4::CallExtensionWide"]
ms.keywords: CallExtensionWide, CallExtensionWide method [Windows Debugging], CallExtensionWide method [Windows Debugging],IDebugControl4 interface, IDebugControl4 interface [Windows Debugging],CallExtensionWide method, IDebugControl4.CallExtensionWide, IDebugControl4::CallExtensionWide, dbgeng/IDebugControl4::CallExtensionWide, debugger.callextensionwide
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
 - IDebugControl4::CallExtensionWide
 - dbgeng/IDebugControl4::CallExtensionWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl4.CallExtensionWide
---

# IDebugControl4::CallExtensionWide


## -description

The <b>CallExtensionWide</b> method calls a debugger extension.

## -parameters

### -param Handle 

[in]
Specifies the handle of the extension library that contains the extension to call.  If <i>Handle</i> is zero, the engine will walk the extension library chain searching for the extension.

### -param Function 

[in]
Specifies the name of the extension to call.

### -param Arguments 

[in, optional]
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
 

This method can also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

## -remarks

If <i>Handle</i> is zero, the engine searches each extension library until it finds one that contains the extension; the extension will then be called.  If the extension returns DEBUG_EXTENSION_CONTINUE_SEARCH, the search will continue.

For more information on using extension libraries, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/calling-extensions-and-extension-functions">Calling Extensions and Extension Functions</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-addextension">AddExtension</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getextensionbypath">GetExtensionByPath</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getextensionfunction">GetExtensionFunction</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol4">IDebugControl4</a>

