---
UID: NF:dbgeng.IDebugSymbols.ReadTypedDataPhysical
title: IDebugSymbols::ReadTypedDataPhysical (dbgeng.h)
description: The ReadTypedDataPhysical method reads the value of a variable from the target computer's physical memory.
old-location: debugger\readtypeddataphysical.htm
tech.root: debugger
ms.assetid: 72562325-27f9-4e80-b03f-8926adad99c1
ms.date: 05/03/2018
keywords: ["IDebugSymbols::ReadTypedDataPhysical"]
ms.keywords: IDebugSymbols interface [Windows Debugging],ReadTypedDataPhysical method, IDebugSymbols.ReadTypedDataPhysical, IDebugSymbols2 interface [Windows Debugging],ReadTypedDataPhysical method, IDebugSymbols2::ReadTypedDataPhysical, IDebugSymbols3 interface [Windows Debugging],ReadTypedDataPhysical method, IDebugSymbols3::ReadTypedDataPhysical, IDebugSymbols::ReadTypedDataPhysical, IDebugSymbols_d9131c11-5752-4b05-b779-69cb256b8ded.xml, ReadTypedDataPhysical, ReadTypedDataPhysical method [Windows Debugging], ReadTypedDataPhysical method [Windows Debugging],IDebugSymbols interface, ReadTypedDataPhysical method [Windows Debugging],IDebugSymbols2 interface, ReadTypedDataPhysical method [Windows Debugging],IDebugSymbols3 interface, dbgeng/IDebugSymbols2::ReadTypedDataPhysical, dbgeng/IDebugSymbols3::ReadTypedDataPhysical, dbgeng/IDebugSymbols::ReadTypedDataPhysical, debugger.readtypeddataphysical
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
 - IDebugSymbols::ReadTypedDataPhysical
 - dbgeng/IDebugSymbols::ReadTypedDataPhysical
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSymbols.ReadTypedDataPhysical
 - IDebugSymbols2.ReadTypedDataPhysical
 - IDebugSymbols3.ReadTypedDataPhysical
---

# IDebugSymbols::ReadTypedDataPhysical


## -description

The <b>ReadTypedDataPhysical</b> method reads the value of a variable from the target computer's physical memory.

## -parameters

### -param Offset 

[in]
Specifies the physical address in the target computer's memory of the variable to be read.

### -param Module 

[in]
Specifies the base address of the module containing the type of the variable.

### -param TypeId 

[in]
Specifies the type ID of the type of the variable.

### -param Buffer 

[out]
Receives the data that was read.

### -param BufferSize 

[in]
Specifies the size in bytes of the buffer <i>Buffer</i>.  This is the maximum number of bytes that will be read.

### -param BytesRead 

[out, optional]
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
 

This method may also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

## -remarks

This method is only available in kernel mode debugging.

The number of bytes this method attempts to read is the smaller of the size of the buffer and the size of the variable.

This is a convenience method.  The same result can be obtained by calling <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-gettypesize">GetTypeSize</a> and <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugdataspaces4-readphysical">ReadPhysical</a>.

For more information about types, see <a href="/windows-hardware/drivers/debugger/types">Types</a>.