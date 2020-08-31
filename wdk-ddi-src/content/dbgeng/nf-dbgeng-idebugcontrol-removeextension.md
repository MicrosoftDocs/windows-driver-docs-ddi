---
UID: NF:dbgeng.IDebugControl.RemoveExtension
title: IDebugControl::RemoveExtension (dbgeng.h)
description: The RemoveExtension method unloads an extension library.
old-location: debugger\removeextension.htm
tech.root: debugger
ms.assetid: ba4a87cc-2412-4769-9694-d6eefd750c4b
ms.date: 05/03/2018
keywords: ["IDebugControl::RemoveExtension"]
ms.keywords: IDebugControl interface [Windows Debugging],RemoveExtension method, IDebugControl.RemoveExtension, IDebugControl2 interface [Windows Debugging],RemoveExtension method, IDebugControl2::RemoveExtension, IDebugControl3 interface [Windows Debugging],RemoveExtension method, IDebugControl3::RemoveExtension, IDebugControl::RemoveExtension, IDebugControl_c762281b-f49c-4837-a524-e2f04edb3b0c.xml, RemoveExtension, RemoveExtension method [Windows Debugging], RemoveExtension method [Windows Debugging],IDebugControl interface, RemoveExtension method [Windows Debugging],IDebugControl2 interface, RemoveExtension method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl2::RemoveExtension, dbgeng/IDebugControl3::RemoveExtension, dbgeng/IDebugControl::RemoveExtension, debugger.removeextension
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
 - IDebugControl::RemoveExtension
 - dbgeng/IDebugControl::RemoveExtension
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl.RemoveExtension
 - IDebugControl2.RemoveExtension
 - IDebugControl3.RemoveExtension
---

# IDebugControl::RemoveExtension


## -description

The <b>RemoveExtension</b> method unloads an extension library.

## -parameters

### -param Handle 

[in]
Specifies the handle of the extension library to unload.  This is the handle returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-addextension">AddExtension</a>.

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

For more information on using extension libraries, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/calling-extensions-and-extension-functions">Calling Extensions and Extension Functions</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-addextension">AddExtension</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>

