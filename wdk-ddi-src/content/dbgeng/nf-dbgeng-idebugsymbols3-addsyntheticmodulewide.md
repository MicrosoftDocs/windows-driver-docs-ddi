---
UID: NF:dbgeng.IDebugSymbols3.AddSyntheticModuleWide
title: IDebugSymbols3::AddSyntheticModuleWide
author: windows-driver-content
description: The AddSyntheticModuleWide method adds a synthetic module to the module list the debugger maintains for the current process.
old-location: debugger\addsyntheticmodulewide.htm
tech.root: debugger
ms.assetid: dc5dc9f4-53a6-468a-907c-9b271fed83aa
ms.date: 05/03/2018
ms.keywords: AddSyntheticModuleWide, AddSyntheticModuleWide method [Windows Debugging], AddSyntheticModuleWide method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],AddSyntheticModuleWide method, IDebugSymbols3.AddSyntheticModuleWide, IDebugSymbols3::AddSyntheticModuleWide, dbgeng/IDebugSymbols3::AddSyntheticModuleWide, debugger.addsyntheticmodulewide
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
-	Dbgeng.h
api_name:
-	IDebugSymbols3.AddSyntheticModuleWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::AddSyntheticModuleWide


## -description


The <b>AddSyntheticModuleWide</b>  method adds a synthetic module to the module list the debugger maintains for the <a href="https://msdn.microsoft.com/295b05a3-e27f-4761-a562-7e87e25bfd3b">current process</a>.


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
 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.




## -remarks



The memory region of the synthetic module, described by the <i>Base</i> and <i>Size</i> parameters, must not overlap the memory region of any other module.

If all the modules are reloaded - for example, by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff554379">Reload</a> with the  <i>Module</i> parameter set to an empty string - all synthetic modules will be discarded.

For more information about synthetic modules, see <a href="https://msdn.microsoft.com/0cd99869-4014-4f9f-b5f1-d06c69fd134e">Synthetic Modules</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537943">AddSyntheticSymbol</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554536">RemoveSyntheticModule</a>
 

 

