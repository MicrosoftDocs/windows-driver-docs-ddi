---
UID: NF:dbgeng.IDebugSymbols2.GetNumberModules
title: IDebugSymbols2::GetNumberModules (dbgeng.h)
description: The GetNumberModules method returns the number of modules in the current process's module list.
old-location: debugger\getnumbermodules.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugSymbols2::GetNumberModules"]
ms.keywords: GetNumberModules, GetNumberModules method [Windows Debugging], GetNumberModules method [Windows Debugging],IDebugSymbols interface, GetNumberModules method [Windows Debugging],IDebugSymbols2 interface, GetNumberModules method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols interface [Windows Debugging],GetNumberModules method, IDebugSymbols2 interface [Windows Debugging],GetNumberModules method, IDebugSymbols2.GetNumberModules, IDebugSymbols2::GetNumberModules, IDebugSymbols3 interface [Windows Debugging],GetNumberModules method, IDebugSymbols3::GetNumberModules, IDebugSymbols::GetNumberModules, IDebugSymbols_151a5c5e-ec01-4801-9ba2-86f26506410c.xml, dbgeng/IDebugSymbols2::GetNumberModules, dbgeng/IDebugSymbols3::GetNumberModules, dbgeng/IDebugSymbols::GetNumberModules, debugger.getnumbermodules
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
 - IDebugSymbols2::GetNumberModules
 - dbgeng/IDebugSymbols2::GetNumberModules
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSymbols.GetNumberModules
 - IDebugSymbols2.GetNumberModules
 - IDebugSymbols3.GetNumberModules
---

# IDebugSymbols2::GetNumberModules


## -description

The <b>GetNumberModules</b> method returns the number of <a href="/windows-hardware/drivers/debugger/modules">modules</a> in the current process's module list.

## -parameters

### -param Loaded 

[out]
Receives the number of loaded modules in the current process's module list.

### -param Unloaded 

[out]
Receives the number of unloaded modules in the current process's module list. This number will be zero if the version of Microsoft Windows running on the target computer does not track unloaded modules.

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
</table>

## -remarks

The list of loaded and unloaded modules is maintained by Windows.  The engine caches a copy of this list, but it may become out of date.  <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-reload">Reload</a> can be used to synchronize the engine's copy of the list with the list maintained by Windows.

The unloaded modules are not tracked in all versions of Windows.  Unloaded modules are tracked for user-mode targets in Microsoft Windows Server 2003 and later; for kernel-mode targets, the unloaded modules are tracked in earlier Windows versions as well.  When they are tracked they are indexed after the loaded modules.  Unloaded modules can be used to analyze failures caused by an attempt to call unloaded code.

For more information about modules, see <a href="/windows-hardware/drivers/debugger/modules">Modules</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getmodulebyindex">GetModuleByIndex</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols">IDebugSymbols</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols2">IDebugSymbols2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>
