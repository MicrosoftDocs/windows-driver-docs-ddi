---
UID: NF:dbgeng.IDebugSymbols3.GetModuleByOffset2
title: IDebugSymbols3::GetModuleByOffset2 method
author: windows-driver-content
description: The GetModuleByOffset2 method searches through the process's modules for one whose memory allocation includes the specified location.
old-location: debugger\getmodulebyoffset2.htm
old-project: debugger
ms.assetid: 2bb23245-9d5c-4b9d-8f4a-ce5fe552efc2
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugSymbols3::GetModuleByOffset2, debugger.getmodulebyoffset2, IDebugSymbols3 interface [Windows Debugging], GetModuleByOffset2 method, IDebugSymbols_0eead97d-6ca0-4682-bc06-71df2cf04c69.xml, GetModuleByOffset2, GetModuleByOffset2 method [Windows Debugging], IDebugSymbols3 interface, dbgeng/IDebugSymbols3::GetModuleByOffset2, GetModuleByOffset2 method [Windows Debugging], IDebugSymbols3
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
-	dbgeng.h
apiname:
-	IDebugSymbols3.GetModuleByOffset2
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugSymbols3::GetModuleByOffset2 method


## -description


The <b>GetModuleByOffset2</b> method searches through the process's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552231">modules</a> for one whose memory allocation includes the specified location.


## -syntax


````
HRESULT GetModuleByOffset2(
  [in]            ULONG64  Offset,
  [in]            ULONG    StartIndex,
  [in]            ULONG    Flags,
  [out, optional] PULONG   Index,
  [out, optional] PULONG64 Base
);
````


## -parameters




### -param Offset [in]

Specifies a location in the target's virtual address space which is inside the desired module's memory allocation -- for example, the address of a symbol belonging to the module.


### -param StartIndex [in]

Specifies the index to start searching from.


### -param Flags [in]

Specifies a bit-set containing options used when searching for the module with the specified location.  <i>Flags</i> may contain the following bit-flags:

<table>
<tr>
<th>Flag</th>
<th>Effect</th>
</tr>
<tr>
<td>
DEBUG_GETMOD_NO_LOADED_MODULES

</td>
<td>
Do not search the loaded modules.

</td>
</tr>
<tr>
<td>
DEBUG_GETMOD_NO_UNLOADED_MODULES

</td>
<td>
Do not search the unloaded modules.

</td>
</tr>
</table>
 


### -param Index [out, optional]

Receives the index of the module.  If <i>Index</i> is <b>NULL</b>, this information is not returned.


### -param Base [out, optional]

Receives the location in the target's memory address space of the base of the module.  If <i>Base</i> is <b>NULL</b>, this information is not returned.


## -returns



This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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



Starting at the specified index, this method returns the first module it finds whose memory allocation address range includes the specified location.  If the target has more than one module whose memory address range includes this location, then subsequent modules can be found by repeated calls to this method with higher values of <i>StartIndex</i>.

For more information about modules, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552231">Modules</a>.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547132">GetModuleByOffset</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547080">GetModuleByIndex</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::GetModuleByOffset2 method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

