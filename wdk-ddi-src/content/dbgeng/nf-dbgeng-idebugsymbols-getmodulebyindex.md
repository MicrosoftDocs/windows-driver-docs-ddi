---
UID: NF:dbgeng.IDebugSymbols.GetModuleByIndex
title: IDebugSymbols::GetModuleByIndex (dbgeng.h)
description: The GetModuleByIndex method returns the location of the module with the specified index.
old-location: debugger\getmodulebyindex.htm
tech.root: debugger
ms.assetid: a33f8a78-4026-4424-af42-2ad359054556
ms.date: 05/03/2018
keywords: ["IDebugSymbols::GetModuleByIndex"]
ms.keywords: GetModuleByIndex, GetModuleByIndex method [Windows Debugging], GetModuleByIndex method [Windows Debugging],IDebugSymbols interface, GetModuleByIndex method [Windows Debugging],IDebugSymbols2 interface, GetModuleByIndex method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols interface [Windows Debugging],GetModuleByIndex method, IDebugSymbols.GetModuleByIndex, IDebugSymbols2 interface [Windows Debugging],GetModuleByIndex method, IDebugSymbols2::GetModuleByIndex, IDebugSymbols3 interface [Windows Debugging],GetModuleByIndex method, IDebugSymbols3::GetModuleByIndex, IDebugSymbols::GetModuleByIndex, IDebugSymbols_0406a71f-e9eb-4acd-93e8-1637ee2506df.xml, dbgeng/IDebugSymbols2::GetModuleByIndex, dbgeng/IDebugSymbols3::GetModuleByIndex, dbgeng/IDebugSymbols::GetModuleByIndex, debugger.getmodulebyindex
f1_keywords:
 - "dbgeng/IDebugSymbols.GetModuleByIndex"
 - "IDebugSymbols.GetModuleByIndex"
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
- IDebugSymbols.GetModuleByIndex
- IDebugSymbols2.GetModuleByIndex
- IDebugSymbols3.GetModuleByIndex
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols::GetModuleByIndex


## -description


The <b>GetModuleByIndex</b> method returns the location of the module with the specified index.


## -parameters




### -param Index [in]

Specifies the index of the module whose location is requested.


### -param Base [out]

Receives the location in the target's memory address space of the module.


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
The specified module was not loaded, and information about the module was not available.

</td>
</tr>
</table>
 




## -remarks



For more information about modules, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/modules">Modules</a>.



