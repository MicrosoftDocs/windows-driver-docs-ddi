---
UID: NF:dbgeng.IDebugSymbols3.GetTypeNameWide
title: IDebugSymbols3::GetTypeNameWide (dbgeng.h)
description: The GetTypeNameWide method returns the name of the type symbol specified by its type ID and module.
old-location: debugger\gettypenamewide.htm
tech.root: debugger
ms.assetid: 0098aa2c-4ee4-49e4-a480-2402e771742f
ms.date: 05/03/2018
keywords: ["IDebugSymbols3::GetTypeNameWide"]
ms.keywords: GetTypeNameWide, GetTypeNameWide method [Windows Debugging], GetTypeNameWide method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetTypeNameWide method, IDebugSymbols3.GetTypeNameWide, IDebugSymbols3::GetTypeNameWide, dbgeng/IDebugSymbols3::GetTypeNameWide, debugger.gettypenamewide
f1_keywords:
 - "dbgeng/IDebugSymbols3.GetTypeNameWide"
 - "IDebugSymbols3.GetTypeNameWide"
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
- IDebugSymbols3.GetTypeNameWide
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::GetTypeNameWide


## -description


The <b>GetTypeNameWide</b>  method returns the name of the type symbol specified by its type ID and module.


## -parameters




### -param Module 
[in]
Specifies the base address of the module to which the type belongs.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/modules">Modules</a>.


### -param TypeId 
[in]
Specifies the type ID of the type.


### -param NameBuffer 
[out, optional]
Receives the name of the type.  If <i>NameBuffer</i> is <b>NULL</b>, this information is not returned.


### -param NameBufferSize 
[in]
Specifies the size in characters of the buffer <i>NameBuffer</i>.


### -param NameSize 
[out, optional]
Receives the size in characters of the type's name.  If <i>NameSize</i> is <b>NULL</b>, this information is not returned.


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
The method was successful. However, the buffer was not large enough to hold the name of the type and it was truncated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL </b></dt>
</dl>
</td>
<td width="60%">
The specified type could not be found in the specified module.

</td>
</tr>
</table>
 




## -remarks



For more information about symbols, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/symbols4">Symbols</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-gettypesize">GetTypeSize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>
 

 

