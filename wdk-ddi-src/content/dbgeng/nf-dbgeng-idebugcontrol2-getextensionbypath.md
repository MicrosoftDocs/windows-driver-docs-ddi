---
UID: NF:dbgeng.IDebugControl2.GetExtensionByPath
title: IDebugControl2::GetExtensionByPath (dbgeng.h)
description: The GetExtensionByPath method returns the handle for an already loaded extension library.
old-location: debugger\getextensionbypath.htm
tech.root: debugger
ms.assetid: 32755878-3f52-4e52-b093-1678c8b8bb42
ms.date: 05/03/2018
keywords: ["IDebugControl2::GetExtensionByPath"]
ms.keywords: GetExtensionByPath, GetExtensionByPath method [Windows Debugging], GetExtensionByPath method [Windows Debugging],IDebugControl interface, GetExtensionByPath method [Windows Debugging],IDebugControl2 interface, GetExtensionByPath method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetExtensionByPath method, IDebugControl2 interface [Windows Debugging],GetExtensionByPath method, IDebugControl2.GetExtensionByPath, IDebugControl2::GetExtensionByPath, IDebugControl3 interface [Windows Debugging],GetExtensionByPath method, IDebugControl3::GetExtensionByPath, IDebugControl::GetExtensionByPath, IDebugControl_821ee348-ddb2-4464-93cd-b6a58e267795.xml, dbgeng/IDebugControl2::GetExtensionByPath, dbgeng/IDebugControl3::GetExtensionByPath, dbgeng/IDebugControl::GetExtensionByPath, debugger.getextensionbypath
f1_keywords:
 - "dbgeng/IDebugControl.GetExtensionByPath"
 - "IDebugControl.GetExtensionByPath"
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
- dbgeng.h
api_name:
- IDebugControl.GetExtensionByPath
- IDebugControl2.GetExtensionByPath
- IDebugControl3.GetExtensionByPath
targetos: Windows
req.typenames: 
---

# IDebugControl2::GetExtensionByPath


## -description


The <b>GetExtensionByPath</b>  method returns the handle for an already loaded extension library.


## -parameters




### -param Path 
[in]
Specifies the fully qualified path and file name of the extension library.


### -param Handle 
[out]
Receives the handle of the extension library.


## -returns



This method can also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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



Extension libraries are loaded into the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debugging-session-and-execution-model">host engine</a>, which is where this method looks for the requested extension library.  <i>Path</i> is a path and file name for the host engine.

For more information on using extension libraries, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/calling-extensions-and-extension-functions">Calling Extensions and Extension Functions</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-addextension">AddExtension</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>
 

 

