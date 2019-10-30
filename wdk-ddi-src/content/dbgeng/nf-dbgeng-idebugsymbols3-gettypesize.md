---
UID: NF:dbgeng.IDebugSymbols3.GetTypeSize
title: IDebugSymbols3::GetTypeSize (dbgeng.h)
description: The GetTypeSize method returns the number of bytes of memory an instance of the specified type requires.
old-location: debugger\gettypesize2.htm
tech.root: debugger
ms.assetid: b6f03eb5-e386-4e88-a729-db08f1fa460c
ms.date: 05/03/2018
ms.keywords: GetTypeSize, GetTypeSize method [Windows Debugging], GetTypeSize method [Windows Debugging],IDebugSymbols interface, GetTypeSize method [Windows Debugging],IDebugSymbols2 interface, GetTypeSize method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols interface [Windows Debugging],GetTypeSize method, IDebugSymbols2 interface [Windows Debugging],GetTypeSize method, IDebugSymbols2::GetTypeSize, IDebugSymbols3 interface [Windows Debugging],GetTypeSize method, IDebugSymbols3.GetTypeSize, IDebugSymbols3::GetTypeSize, IDebugSymbols::GetTypeSize, IDebugSymbols_d1c65bea-0479-4ca8-bdfa-6c7a7376792a.xml, dbgeng/IDebugSymbols2::GetTypeSize, dbgeng/IDebugSymbols3::GetTypeSize, dbgeng/IDebugSymbols::GetTypeSize, debugger.gettypesize2
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugSymbols.GetTypeSize"
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
- IDebugSymbols.GetTypeSize
- IDebugSymbols2.GetTypeSize
- IDebugSymbols3.GetTypeSize
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::GetTypeSize


## -description


The <b>GetTypeSize</b> method returns the number of bytes of memory an instance of the specified type requires.


## -parameters




### -param Module [in]

Specifies the base address of the module containing the type.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/modules">Modules</a>.


### -param TypeId [in]

Specifies the type ID of the type.


### -param Size [out]

Receives the number of bytes of memory an instance of the specified type requires.


## -returns



This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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
The method was successful

</td>
</tr>
</table>
 




## -remarks



For more information about symbols, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/symbols4">Symbols</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-gettypename">GetTypeName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols">IDebugSymbols</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols2">IDebugSymbols2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>
 

 

