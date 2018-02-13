---
UID: NF:dbgeng.IDebugSymbols3.AddSyntheticModuleWide
title: IDebugSymbols3::AddSyntheticModuleWide method
author: windows-driver-content
description: The AddSyntheticModuleWide method adds a synthetic module to the module list the debugger maintains for the current process.
old-location: debugger\addsyntheticmodulewide.htm
old-project: debugger
ms.assetid: dc5dc9f4-53a6-468a-907c-9b271fed83aa
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: debugger.addsyntheticmodulewide, IDebugSymbols3 interface [Windows Debugging], AddSyntheticModuleWide method, AddSyntheticModuleWide method [Windows Debugging], dbgeng/IDebugSymbols3::AddSyntheticModuleWide, AddSyntheticModuleWide method [Windows Debugging], IDebugSymbols3 interface, IDebugSymbols3::AddSyntheticModuleWide, AddSyntheticModuleWide, IDebugSymbols3
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Dbgeng.h
apiname:
-	IDebugSymbols3.AddSyntheticModuleWide
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugSymbols3::AddSyntheticModuleWide method


## -description


The <b>AddSyntheticModuleWide</b>  method adds a synthetic module to the module list the debugger maintains for the <a href="https://msdn.microsoft.com/295b05a3-e27f-4761-a562-7e87e25bfd3b">current process</a>.


## -syntax


````
HRESULT AddSyntheticModuleWide(
  [in] ULONG64 Base,
  [in] ULONG   Size,
  [in] PCSTR   ImagePath,
  [in] PCSTR   ModuleName,
  [in] ULONG   Flags
);
````


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



<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554536">RemoveSyntheticModule</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::AddSyntheticModuleWide method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

