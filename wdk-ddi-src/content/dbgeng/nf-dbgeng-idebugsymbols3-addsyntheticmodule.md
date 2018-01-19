---
UID: NF:dbgeng.IDebugSymbols3.AddSyntheticModule
title: IDebugSymbols3::AddSyntheticModule method
author: windows-driver-content
description: The AddSyntheticModule method adds a synthetic module to the module list the debugger maintains for the current process.
old-location: debugger\addsyntheticmodule.htm
old-project: debugger
ms.assetid: 87d9f307-996b-47df-b3dd-368fef6c1042
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSymbols3, IDebugSymbols3::AddSyntheticModule, AddSyntheticModule
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
req.alt-api: IDebugSymbols3.AddSyntheticModule
req.alt-loc: Dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugSymbols3::AddSyntheticModule method



## -description
The <b>AddSyntheticModule</b>  method adds a synthetic module to the module list the debugger maintains for the <a href="debugger.c#current_process#current_process"><i>current process</i></a>.



## -syntax

````
HRESULT AddSyntheticModule(
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
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.


## -remarks
The memory region of the synthetic module, described by the <i>Base</i> and <i>Size</i> parameters, must not overlap the memory region of any other module.

If all the modules are reloaded - for example, by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff554379">Reload</a> with the  <i>Module</i> parameter set to an empty string - all synthetic modules will be discarded.

For more information about synthetic modules, see <a href="debugger.modules#synthetic_modules#synthetic_modules">Synthetic Modules</a>.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554536">RemoveSyntheticModule</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537943">AddSyntheticSymbol</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::AddSyntheticModule method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

