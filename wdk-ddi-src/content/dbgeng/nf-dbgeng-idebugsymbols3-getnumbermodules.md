---
UID: NF:dbgeng.IDebugSymbols3.GetNumberModules
title: IDebugSymbols3::GetNumberModules method
author: windows-driver-content
description: The GetNumberModules method returns the number of modules in the current process's module list.
old-location: debugger\getnumbermodules.htm
old-project: debugger
ms.assetid: e74a4e51-0e3b-4d16-b39c-379dfb3905ad
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetNumberModules method [Windows Debugging], GetNumberModules method [Windows Debugging], IDebugSymbols interface, GetNumberModules method [Windows Debugging], IDebugSymbols2 interface, GetNumberModules method [Windows Debugging], IDebugSymbols3 interface, GetNumberModules,IDebugSymbols3.GetNumberModules, IDebugSymbols interface [Windows Debugging], GetNumberModules method, IDebugSymbols2 interface [Windows Debugging], GetNumberModules method, IDebugSymbols2::GetNumberModules, IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], GetNumberModules method, IDebugSymbols3::GetNumberModules, IDebugSymbols::GetNumberModules, IDebugSymbols_151a5c5e-ec01-4801-9ba2-86f26506410c.xml, dbgeng/IDebugSymbols2::GetNumberModules, dbgeng/IDebugSymbols3::GetNumberModules, dbgeng/IDebugSymbols::GetNumberModules, debugger.getnumbermodules
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugSymbols.GetNumberModules
-	IDebugSymbols2.GetNumberModules
-	IDebugSymbols3.GetNumberModules
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols3::GetNumberModules method


## -description


The <b>GetNumberModules</b> method returns the number of <a href="https://msdn.microsoft.com/library/windows/hardware/ff552231">modules</a> in the current process's module list.


## -syntax


````
HRESULT GetNumberModules(
  [out] PULONG Loaded,
  [out] PULONG Unloaded
);
````


## -parameters




### -param Loaded [out]

Receives the number of loaded modules in the current process's module list.


### -param Unloaded [out]

Receives the number of unloaded modules in the current process's module list. This number will be zero if the version of Microsoft Windows running on the target computer does not track unloaded modules.


## -returns



This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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



The list of loaded and unloaded modules is maintained by Windows.  The engine caches a copy of this list, but it may become out of date.  <a href="https://msdn.microsoft.com/library/windows/hardware/ff554379">Reload</a> can be used to synchronize the engine's copy of the list with the list maintained by Windows.

The unloaded modules are not tracked in all versions of Windows.  Unloaded modules are tracked for user-mode targets in Microsoft Windows Server 2003 and later; for kernel-mode targets, the unloaded modules are tracked in earlier Windows versions as well.  When they are tracked they are indexed after the loaded modules.  Unloaded modules can be used to analyze failures caused by an attempt to call unloaded code.

For more information about modules, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552231">Modules</a>.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugsymbols.md">IDebugSymbols</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols2.md">IDebugSymbols2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547080">GetModuleByIndex</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols::GetNumberModules method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

