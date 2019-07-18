---
UID: NF:dbgeng.IDebugSymbols3.GetModuleByModuleNameWide
title: IDebugSymbols3::GetModuleByModuleNameWide (dbgeng.h)
description: The GetModuleByModuleNameWide method searches through the target's modules for one with the specified name.
old-location: debugger\getmodulebymodulenamewide.htm
tech.root: debugger
ms.assetid: 66ec7c51-3d2c-4a25-a356-4df06ee1b1f5
ms.date: 05/03/2018
ms.keywords: GetModuleByModuleNameWide, GetModuleByModuleNameWide method [Windows Debugging], GetModuleByModuleNameWide method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetModuleByModuleNameWide method, IDebugSymbols3.GetModuleByModuleNameWide, IDebugSymbols3::GetModuleByModuleNameWide, dbgeng/IDebugSymbols3::GetModuleByModuleNameWide, debugger.getmodulebymodulenamewide
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugSymbols3.GetModuleByModuleNameWide"
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
- IDebugSymbols3.GetModuleByModuleNameWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::GetModuleByModuleNameWide


## -description


The <b>GetModuleByModuleNameWide</b>  method searches through the target's <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/modules">modules</a> for one with the specified name.


## -parameters




### -param Name [in]

Specifies the name of the desired module.


### -param StartIndex [in]

Specifies the index to start searching from.


### -param Index [out, optional]

Receives the index of the first module with the name <i>Name</i>.  If <i>Index</i> is <b>NULL</b>, this information is not returned.


### -param Base [out, optional]

Receives the location in the target's memory address space of the base of the module.  If <i>Base</i> is <b>NULL</b>, this information is not returned.


## -returns



This method may also return other error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
One of the arguments passed in was invalid.

</td>
</tr>
</table>
 




## -remarks



Starting at the specified index, these methods return the first module they find with the specified name.  If the target has more than one module with this name, then subsequent modules can be found by repeated calls to these methods with higher values of <i>StartIndex</i>.  

For more information about modules, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/modules">Modules</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getmodulebymodulename2">GetModuleByModuleName2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>
 

 

