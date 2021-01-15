---
UID: NF:dbgeng.IDebugSymbols2.GetModuleParameters
title: IDebugSymbols2::GetModuleParameters (dbgeng.h)
description: The GetModuleParameters method returns parameters for modules in the target.
old-location: debugger\getmoduleparameters.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugSymbols2::GetModuleParameters"]
ms.keywords: GetModuleParameters, GetModuleParameters method [Windows Debugging], GetModuleParameters method [Windows Debugging],IDebugSymbols interface, GetModuleParameters method [Windows Debugging],IDebugSymbols2 interface, GetModuleParameters method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols interface [Windows Debugging],GetModuleParameters method, IDebugSymbols2 interface [Windows Debugging],GetModuleParameters method, IDebugSymbols2.GetModuleParameters, IDebugSymbols2::GetModuleParameters, IDebugSymbols3 interface [Windows Debugging],GetModuleParameters method, IDebugSymbols3::GetModuleParameters, IDebugSymbols::GetModuleParameters, IDebugSymbols_0a78fd64-15b7-4032-83a8-9867037e5081.xml, dbgeng/IDebugSymbols2::GetModuleParameters, dbgeng/IDebugSymbols3::GetModuleParameters, dbgeng/IDebugSymbols::GetModuleParameters, debugger.getmoduleparameters
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
 - IDebugSymbols2::GetModuleParameters
 - dbgeng/IDebugSymbols2::GetModuleParameters
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSymbols2::GetModuleParameters
---

# IDebugSymbols2::GetModuleParameters


## -description

The <b>GetModuleParameters</b> method returns parameters for <a href="/windows-hardware/drivers/debugger/modules">modules</a> in the target.

## -parameters

### -param Count 

[in]
Specifies the number of modules whose parameters are desired.

### -param Bases 

[in, optional]
Specifies an array of locations in the target's virtual address space representing the base address of the modules whose parameters are desired.  The size of this array is the value of <i>Count</i>.  If <i>Bases</i> is <b>NULL</b>, the <i>Start</i> parameter is used to specify the modules by index.

### -param Start 

[in]
Specifies the index of the first module whose parameters are desired.  If <i>Bases</i> is not <b>NULL</b>, this parameter is ignored.

### -param Params 

[out]
Receives the parameters.  The size of this array is the value of <i>Count</i>.  See <a href="/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_module_parameters">DEBUG_MODULE_PARAMETERS</a>.

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
The method was successful.  However, if <i>Bases</i> is not <b>NULL</b>, it is possible that not all of the modules were found, in which case partial results are returned.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
When <i>Bases</i> is <b>NULL</b>, this value indicates that the target contains fewer than the sum of <i>Count</i> and <i>Start</i> modules.  Partial results are returned.

</td>
</tr>
</table>

## -remarks

In the cases when partial results are returned, the entries in the array <i>Params</i> corresponding to modules that could not be found have their <b>Base</b> field set to DEBUG_INVALID_OFFSET.  See <a href="/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_module_parameters">DEBUG_MODULE_PARAMETERS</a>.

For more information about modules, see <a href="/windows-hardware/drivers/debugger/modules">Modules</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_module_parameters">DEBUG_MODULE_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols">IDebugSymbols</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols2">IDebugSymbols2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>

