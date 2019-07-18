---
UID: NF:dbgeng.IDebugSymbols2.GetModuleVersionInformation
title: IDebugSymbols2::GetModuleVersionInformation (dbgeng.h)
description: The GetModuleVersionInformation method returns version information for the specified module.
old-location: debugger\getmoduleversioninformation.htm
tech.root: debugger
ms.assetid: af655cd2-2e1f-4d78-aff3-3875106b50bc
ms.date: 05/03/2018
ms.keywords: GetModuleVersionInformation, GetModuleVersionInformation method [Windows Debugging], GetModuleVersionInformation method [Windows Debugging],IDebugSymbols2 interface, GetModuleVersionInformation method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols2 interface [Windows Debugging],GetModuleVersionInformation method, IDebugSymbols2.GetModuleVersionInformation, IDebugSymbols2::GetModuleVersionInformation, IDebugSymbols3 interface [Windows Debugging],GetModuleVersionInformation method, IDebugSymbols3::GetModuleVersionInformation, IDebugSymbols_a325db82-91a3-48d9-b189-8971cd5eaf75.xml, dbgeng/IDebugSymbols2::GetModuleVersionInformation, dbgeng/IDebugSymbols3::GetModuleVersionInformation, debugger.getmoduleversioninformation
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugSymbols2.GetModuleVersionInformation"
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
- IDebugSymbols2.GetModuleVersionInformation
- IDebugSymbols3.GetModuleVersionInformation
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols2::GetModuleVersionInformation


## -description


The <b>GetModuleVersionInformation</b>  method returns version information for the specified module.


## -parameters




### -param Index [in]

Specifies the index of the module.  If it is set to DEBUG_ANY_ID, the <i>Base</i> parameter is used to specify the location of the module instead.


### -param Base [in]

If <i>Index</i> is DEBUG_ANY_ID, specifies the location in the target's memory address space of the base of the module.  Otherwise it is ignored.


### -param Item [in]

Specifies the version information being requested.  This string corresponds to the <i>lpSubBlock</i> parameter of the function <b>VerQueryValue</b>.  For details on the <b>VerQueryValue</b> function, see the Platform SDK.


### -param Buffer [out, optional]

Receives the requested version information.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize [in]

Specifies the size in characters of the buffer <i>Buffer</i>.


### -param VerInfoSize [out, optional]

Receives the size in characters of the version information.  If <i>VerInfoSize</i> is <b>NULL</b>, this information is not returned.


## -returns



This method may also return other error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The size of the buffer was smaller than the size of the version information.  In this case the buffer is filled with the truncated version information.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
The specified module was not found.

</td>
</tr>
</table>
 




## -remarks



Module version information is available only for loaded modules and may not be available in all sessions.

For more information about modules, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/modules">Modules</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getmodulebyindex">GetModuleByIndex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getmodulebyoffset2">GetModuleByOffset2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getnumbermodules">GetNumberModules</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugsymbols2">IDebugSymbols2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>
 

 

