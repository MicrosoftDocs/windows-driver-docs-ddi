---
UID: NF:dbgeng.IDebugControl4.GetExtensionByPathWide
title: IDebugControl4::GetExtensionByPathWide (dbgeng.h)
description: The GetExtensionByPathWide method returns the handle for an already loaded extension library.
old-location: debugger\getextensionbypathwide.htm
tech.root: debugger
ms.assetid: 85257190-2b39-487d-ada6-4c8cd0b1450f
ms.date: 05/03/2018
keywords: ["IDebugControl4::GetExtensionByPathWide"]
ms.keywords: GetExtensionByPathWide, GetExtensionByPathWide method [Windows Debugging], GetExtensionByPathWide method [Windows Debugging],IDebugControl4 interface, IDebugControl4 interface [Windows Debugging],GetExtensionByPathWide method, IDebugControl4.GetExtensionByPathWide, IDebugControl4::GetExtensionByPathWide, dbgeng/IDebugControl4::GetExtensionByPathWide, debugger.getextensionbypathwide
f1_keywords:
 - "dbgeng/IDebugControl4.GetExtensionByPathWide"
 - "IDebugControl4.GetExtensionByPathWide"
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
- IDebugControl4.GetExtensionByPathWide
targetos: Windows
req.typenames: 
---

# IDebugControl4::GetExtensionByPathWide


## -description


The <b>GetExtensionByPathWide</b>  method returns the handle for an already loaded extension library.


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



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol4">IDebugControl4</a>
 

 

