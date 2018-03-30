---
UID: NF:dbgeng.IDebugSymbols.GetModuleByModuleName
title: IDebugSymbols::GetModuleByModuleName method
author: windows-driver-content
description: The GetModuleByModuleName method searches through the target's modules for one with the specified name.
old-location: debugger\getmodulebymodulename.htm
old-project: debugger
ms.assetid: 243b79fe-b1b2-48b4-bb0b-c56b787e7b83
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetModuleByModuleName method [Windows Debugging], GetModuleByModuleName method [Windows Debugging], IDebugSymbols interface, GetModuleByModuleName method [Windows Debugging], IDebugSymbols2 interface, GetModuleByModuleName method [Windows Debugging], IDebugSymbols3 interface, GetModuleByModuleName,IDebugSymbols.GetModuleByModuleName, IDebugSymbols, IDebugSymbols interface [Windows Debugging], GetModuleByModuleName method, IDebugSymbols2 interface [Windows Debugging], GetModuleByModuleName method, IDebugSymbols2::GetModuleByModuleName, IDebugSymbols3 interface [Windows Debugging], GetModuleByModuleName method, IDebugSymbols3::GetModuleByModuleName, IDebugSymbols::GetModuleByModuleName, IDebugSymbols_1a407f12-64e8-43a3-b831-ef8c9b701537.xml, dbgeng/IDebugSymbols2::GetModuleByModuleName, dbgeng/IDebugSymbols3::GetModuleByModuleName, dbgeng/IDebugSymbols::GetModuleByModuleName, debugger.getmodulebymodulename
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
-	IDebugSymbols.GetModuleByModuleName
-	IDebugSymbols2.GetModuleByModuleName
-	IDebugSymbols3.GetModuleByModuleName
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols::GetModuleByModuleName method


## -description


The <b>GetModuleByModuleName</b>  method searches through the target's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552231">modules</a> for one with the specified name.


## -parameters




### -param Name [in]

Specifies the name of the desired module.


### -param StartIndex [in]

Specifies the index to start searching from.


### -param Index [out, optional]

Receives the index of the first module with the name <i>Name</i>.  If <i>Index</i> is <b>NULL</b>, this information is not returned.


### -param Base [out, optional]

Receives the location in the target's memory address space of the base of the module.  If <i>Base</i> is <b>NULL</b>, this information is not returned.


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
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
One of the arguments passed in was invalid.

</td>
</tr>
</table>
 




## -remarks



Starting at the specified index, these methods return the first module they find with the specified name.  If the target has more than one module with this name, then subsequent modules can be found by repeated calls to these methods with higher values of <i>StartIndex</i>.  

For more information about modules, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552231">Modules</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547102">GetModuleByModuleName2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550856">IDebugSymbols</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550864">IDebugSymbols2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>
 

 

