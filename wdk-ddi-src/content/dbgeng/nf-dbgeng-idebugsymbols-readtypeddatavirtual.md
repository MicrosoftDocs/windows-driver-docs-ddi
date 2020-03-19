---
UID: NF:dbgeng.IDebugSymbols.ReadTypedDataVirtual
title: IDebugSymbols::ReadTypedDataVirtual (dbgeng.h)
description: The ReadTypedDataVirtual method reads the value of a variable in the target's virtual memory.
old-location: debugger\readtypeddatavirtual.htm
tech.root: debugger
ms.assetid: 526bebd8-95af-4f6f-a381-eb60273d1af5
ms.date: 05/03/2018
keywords: ["IDebugSymbols::ReadTypedDataVirtual"]
ms.keywords: IDebugSymbols interface [Windows Debugging],ReadTypedDataVirtual method, IDebugSymbols.ReadTypedDataVirtual, IDebugSymbols2 interface [Windows Debugging],ReadTypedDataVirtual method, IDebugSymbols2::ReadTypedDataVirtual, IDebugSymbols3 interface [Windows Debugging],ReadTypedDataVirtual method, IDebugSymbols3::ReadTypedDataVirtual, IDebugSymbols::ReadTypedDataVirtual, IDebugSymbols_c7a6fee6-d6bc-4dd6-923a-7e789801091f.xml, ReadTypedDataVirtual, ReadTypedDataVirtual method [Windows Debugging], ReadTypedDataVirtual method [Windows Debugging],IDebugSymbols interface, ReadTypedDataVirtual method [Windows Debugging],IDebugSymbols2 interface, ReadTypedDataVirtual method [Windows Debugging],IDebugSymbols3 interface, dbgeng/IDebugSymbols2::ReadTypedDataVirtual, dbgeng/IDebugSymbols3::ReadTypedDataVirtual, dbgeng/IDebugSymbols::ReadTypedDataVirtual, debugger.readtypeddatavirtual
f1_keywords:
 - "dbgeng/IDebugSymbols.ReadTypedDataVirtual"
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
- IDebugSymbols.ReadTypedDataVirtual
- IDebugSymbols2.ReadTypedDataVirtual
- IDebugSymbols3.ReadTypedDataVirtual
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols::ReadTypedDataVirtual


## -description


The <b>ReadTypedDataVirtual</b> method reads the value of a variable in the target's virtual memory.


## -parameters




### -param Offset [in]

Specifies the location in the target's virtual address space of the variable to read.


### -param Module [in]

Specifies the base address of the module containing the type of the variable.


### -param TypeId [in]

Specifies the type ID of the type.


### -param Buffer [out]

Receives the data that is read.


### -param BufferSize [in]

Specifies the size in bytes of the buffer <i>Buffer</i>.  This is the maximum number of bytes to be read.


### -param BytesRead [out, optional]

Receives the number of bytes that were read.  If <i>BytesRead</i> is <b>NULL</b>, this information is not returned.


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
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.  However, the buffer <i>Buffer</i> was not large enough to hold all the data and it was truncated.

</td>
</tr>
</table>
 

This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.




## -remarks



The number of bytes this method attempts to read is the smaller of the size of the buffer and the size of the variable.

This is a convenience method.  The same result can be obtained by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-gettypesize">GetTypeSize</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugdataspaces4-readvirtual">ReadVirtual</a>.

For more information about types, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/types">Types</a>.



