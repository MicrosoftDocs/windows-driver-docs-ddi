---
UID: NF:dbgeng.IDebugSymbols3.AddSyntheticModule
title: IDebugSymbols3::AddSyntheticModule (dbgeng.h)
description: The AddSyntheticModule method adds a synthetic module to the module list the debugger maintains for the current process.
old-location: debugger\addsyntheticmodule.htm
tech.root: debugger
ms.assetid: 87d9f307-996b-47df-b3dd-368fef6c1042
ms.date: 05/03/2018
ms.keywords: AddSyntheticModule, AddSyntheticModule method [Windows Debugging], AddSyntheticModule method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],AddSyntheticModule method, IDebugSymbols3.AddSyntheticModule, IDebugSymbols3::AddSyntheticModule, IDebugSymbols_ecccfdc4-2942-480c-9f78-c21c4ed46c90.xml, dbgeng/IDebugSymbols3::AddSyntheticModule, debugger.addsyntheticmodule
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugSymbols3.AddSyntheticModule"
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
- Dbgeng.h
api_name:
- IDebugSymbols3.AddSyntheticModule
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::AddSyntheticModule


## -description


The <b>AddSyntheticModule</b>  method adds a synthetic module to the module list the debugger maintains for the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/c">current process</a>.


## -parameters




### -param Base [in]

Specifies the location in the process's virtual address space of the base of the synthetic module.


### -param Size [in]

Specifies the size in bytes of the synthetic module.


### -param ImagePath [in]

Specifies the image name of the synthetic module.  This is the name that will be returned as the name of the executable file for the synthetic module.  The full path should be included if known.


### -param ModuleName [in]

Specifies the module name for the synthetic module.


### -param Flags [in]

Set to DEBUG_ADDSYNTHMOD_DEFAULT.


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
 

This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.




## -remarks



The memory region of the synthetic module, described by the <i>Base</i> and <i>Size</i> parameters, must not overlap the memory region of any other module.

If all the modules are reloaded - for example, by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-reload">Reload</a> with the  <i>Module</i> parameter set to an empty string - all synthetic modules will be discarded.

For more information about synthetic modules, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/modules">Synthetic Modules</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-addsyntheticsymbol">AddSyntheticSymbol</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-removesyntheticmodule">RemoveSyntheticModule</a>
 

 

