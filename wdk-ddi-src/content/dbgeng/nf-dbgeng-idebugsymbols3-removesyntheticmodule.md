---
UID: NF:dbgeng.IDebugSymbols3.RemoveSyntheticModule
title: IDebugSymbols3::RemoveSyntheticModule (dbgeng.h)
description: The RemoveSyntheticModule method removes a synthetic module from the module list the debugger maintains for the current process.
old-location: debugger\removesyntheticmodule.htm
tech.root: debugger
ms.assetid: 951b42b6-4d6a-45af-a27f-6e8056676bb0
ms.date: 05/03/2018
ms.keywords: IDebugSymbols3 interface [Windows Debugging],RemoveSyntheticModule method, IDebugSymbols3.RemoveSyntheticModule, IDebugSymbols3::RemoveSyntheticModule, IDebugSymbols_f1ed1ce4-53ad-469f-9ab8-17900b6870e8.xml, RemoveSyntheticModule, RemoveSyntheticModule method [Windows Debugging], RemoveSyntheticModule method [Windows Debugging],IDebugSymbols3 interface, dbgeng/IDebugSymbols3::RemoveSyntheticModule, debugger.removesyntheticmodule
f1_keywords:
 - "dbgeng/IDebugSymbols3.RemoveSyntheticModule"
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
- IDebugSymbols3.RemoveSyntheticModule
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::RemoveSyntheticModule


## -description


The <b>RemoveSyntheticModule</b> method removes a synthetic module from the module list the debugger maintains for the current process.


## -parameters




### -param Base [in]

Specifies the location in the process's virtual address space of the base of the synthetic module.


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
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
No synthetic module was found at the specified location.  This is returned if a synthetic module at this location was previously removed or discarded.

</td>
</tr>
</table>
 

This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.




## -remarks



If all the modules are reloaded - for example, by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-reload">Reload</a> with the  <i>Module</i> parameter set to the empty string - all synthetic modules will be discarded.

For more information about synthetic modules, see Synthetic Modules.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-addsyntheticmodule">AddSyntheticModule</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-removesyntheticsymbol">RemoveSyntheticSymbol</a>
 

 

