---
UID: NF:dbgeng.IDebugSymbols3.RemoveSyntheticModule
title: IDebugSymbols3::RemoveSyntheticModule method
author: windows-driver-content
description: The RemoveSyntheticModule method removes a synthetic module from the module list the debugger maintains for the current process.
old-location: debugger\removesyntheticmodule.htm
old-project: debugger
ms.assetid: 951b42b6-4d6a-45af-a27f-6e8056676bb0
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], RemoveSyntheticModule method, IDebugSymbols3::RemoveSyntheticModule, IDebugSymbols_f1ed1ce4-53ad-469f-9ab8-17900b6870e8.xml, RemoveSyntheticModule method [Windows Debugging], RemoveSyntheticModule method [Windows Debugging], IDebugSymbols3 interface, RemoveSyntheticModule,IDebugSymbols3.RemoveSyntheticModule, dbgeng/IDebugSymbols3::RemoveSyntheticModule, debugger.removesyntheticmodule
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugSymbols3.RemoveSyntheticModule
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols3::RemoveSyntheticModule method


## -description


The <b>RemoveSyntheticModule</b> method removes a synthetic module from the module list the debugger maintains for the current process.


## -syntax


````
HRESULT RemoveSyntheticModule(
  [in] ULONG64 Base
);
````


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
 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.




## -remarks



If all the modules are reloaded - for example, by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff554379">Reload</a> with the  <i>Module</i> parameter set to the empty string - all synthetic modules will be discarded.

For more information about synthetic modules, see Synthetic Modules.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554542">RemoveSyntheticSymbol</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537937">AddSyntheticModule</a>



 

 


