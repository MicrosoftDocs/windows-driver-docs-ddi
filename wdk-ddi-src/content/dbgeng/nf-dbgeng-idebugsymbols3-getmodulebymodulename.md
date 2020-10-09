---
UID: NF:dbgeng.IDebugSymbols3.GetModuleByModuleName
title: IDebugSymbols3::GetModuleByModuleName (dbgeng.h)
description: The GetModuleByModuleName method searches through the target's modules for one with the specified name.
old-location: debugger\getmodulebymodulename.htm
tech.root: debugger
ms.assetid: 243b79fe-b1b2-48b4-bb0b-c56b787e7b83
ms.date: 05/03/2018
keywords: ["IDebugSymbols3::GetModuleByModuleName"]
ms.keywords: GetModuleByModuleName, GetModuleByModuleName method [Windows Debugging], GetModuleByModuleName method [Windows Debugging],IDebugSymbols interface, GetModuleByModuleName method [Windows Debugging],IDebugSymbols2 interface, GetModuleByModuleName method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols interface [Windows Debugging],GetModuleByModuleName method, IDebugSymbols2 interface [Windows Debugging],GetModuleByModuleName method, IDebugSymbols2::GetModuleByModuleName, IDebugSymbols3 interface [Windows Debugging],GetModuleByModuleName method, IDebugSymbols3.GetModuleByModuleName, IDebugSymbols3::GetModuleByModuleName, IDebugSymbols::GetModuleByModuleName, IDebugSymbols_1a407f12-64e8-43a3-b831-ef8c9b701537.xml, dbgeng/IDebugSymbols2::GetModuleByModuleName, dbgeng/IDebugSymbols3::GetModuleByModuleName, dbgeng/IDebugSymbols::GetModuleByModuleName, debugger.getmodulebymodulename
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
 - IDebugSymbols3::GetModuleByModuleName
 - dbgeng/IDebugSymbols3::GetModuleByModuleName
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSymbols.GetModuleByModuleName
 - IDebugSymbols2.GetModuleByModuleName
 - IDebugSymbols3.GetModuleByModuleName
---

# IDebugSymbols3::GetModuleByModuleName


## -description

The <b>GetModuleByModuleName</b>  method searches through the target's <a href="/windows-hardware/drivers/debugger/modules">modules</a> for one with the specified name.

## -parameters

### -param Name 

[in]
Specifies the name of the desired module.

### -param StartIndex 

[in]
Specifies the index to start searching from.

### -param Index 

[out, optional]
Receives the index of the first module with the name <i>Name</i>.  If <i>Index</i> is <b>NULL</b>, this information is not returned.

### -param Base 

[out, optional]
Receives the location in the target's memory address space of the base of the module.  If <i>Base</i> is <b>NULL</b>, this information is not returned.

## -returns

This method may also return other error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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

For more information about modules, see <a href="/windows-hardware/drivers/debugger/modules">Modules</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getmodulebymodulename2">GetModuleByModuleName2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols">IDebugSymbols</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols2">IDebugSymbols2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>