---
UID: NF:dbgeng.IDebugSymbols3.GetModuleByModuleName2Wide
title: IDebugSymbols3::GetModuleByModuleName2Wide (dbgeng.h)
description: The GetModuleByModuleName2Wide method searches through the process's modules for one with the specified name.
old-location: debugger\getmodulebymodulename2wide.htm
tech.root: debugger
ms.assetid: 49e27e24-d38a-4a22-a92f-33a384437250
ms.date: 05/03/2018
keywords: ["IDebugSymbols3::GetModuleByModuleName2Wide"]
ms.keywords: GetModuleByModuleName2Wide, GetModuleByModuleName2Wide method [Windows Debugging], GetModuleByModuleName2Wide method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetModuleByModuleName2Wide method, IDebugSymbols3.GetModuleByModuleName2Wide, IDebugSymbols3::GetModuleByModuleName2Wide, dbgeng/IDebugSymbols3::GetModuleByModuleName2Wide, debugger.getmodulebymodulename2wide
f1_keywords:
 - "dbgeng/IDebugSymbols3.GetModuleByModuleName2Wide"
 - "IDebugSymbols3.GetModuleByModuleName2Wide"
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
- IDebugSymbols3.GetModuleByModuleName2Wide
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::GetModuleByModuleName2Wide


## -description


The <b>GetModuleByModuleName2Wide</b>  method searches through the process's <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/modules">modules</a> for one with the specified name.


## -parameters




### -param Name 
[in]
Specifies the name of the desired module.


### -param StartIndex 
[in]
Specifies the index to start searching from.


### -param Flags 
[in]
Specifies a bit-set containing options used when searching for the module with the specified name.  <i>Flags</i> may contain the following bit-flags:

<table>
<tr>
<th>Flag</th>
<th>Effect</th>
</tr>
<tr>
<td>
DEBUG_GETMOD_NO_LOADED_MODULES

</td>
<td>
Do not search the loaded modules.

</td>
</tr>
<tr>
<td>
DEBUG_GETMOD_NO_UNLOADED_MODULES

</td>
<td>
Do not search the unloaded modules.

</td>
</tr>
</table>
 


### -param Index 
[out, optional]
Receives the index of the first module with the name <i>Name</i>.  If <i>Index</i> is <b>NULL</b>, this information is not returned.


### -param Base 
[out, optional]
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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getmodulebymodulename">GetModuleByModuleName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>
 

 

