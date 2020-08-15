---
UID: NF:dbgeng.IDebugSymbols2.GetOffsetByLine
title: IDebugSymbols2::GetOffsetByLine (dbgeng.h)
description: The GetOffsetByLine method returns the location of the instruction that corresponds to a specified line in the source code.
old-location: debugger\getoffsetbyline.htm
tech.root: debugger
ms.assetid: 347e0d45-8be1-4e4e-8a6a-44d5c914bf0f
ms.date: 05/03/2018
keywords: ["IDebugSymbols2::GetOffsetByLine"]
ms.keywords: GetOffsetByLine, GetOffsetByLine method [Windows Debugging], GetOffsetByLine method [Windows Debugging],IDebugSymbols interface, GetOffsetByLine method [Windows Debugging],IDebugSymbols2 interface, GetOffsetByLine method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols interface [Windows Debugging],GetOffsetByLine method, IDebugSymbols2 interface [Windows Debugging],GetOffsetByLine method, IDebugSymbols2.GetOffsetByLine, IDebugSymbols2::GetOffsetByLine, IDebugSymbols3 interface [Windows Debugging],GetOffsetByLine method, IDebugSymbols3::GetOffsetByLine, IDebugSymbols::GetOffsetByLine, IDebugSymbols_1aa7fddc-6a33-469e-828f-45ff0f31aae7.xml, dbgeng/IDebugSymbols2::GetOffsetByLine, dbgeng/IDebugSymbols3::GetOffsetByLine, dbgeng/IDebugSymbols::GetOffsetByLine, debugger.getoffsetbyline
f1_keywords:
 - "dbgeng/IDebugSymbols.GetOffsetByLine"
 - "IDebugSymbols.GetOffsetByLine"
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
- IDebugSymbols.GetOffsetByLine
- IDebugSymbols2.GetOffsetByLine
- IDebugSymbols3.GetOffsetByLine
targetos: Windows
req.typenames: 
---

# IDebugSymbols2::GetOffsetByLine


## -description


The <b>GetOffsetByLine</b>  method returns the location of the instruction that corresponds to a specified line in the source code.


## -parameters




### -param Line 
[in]
Specifies the line number in the source file.


### -param File 
[in]
Specifies the file name of the source file.


### -param Offset 
[out]
Receives the location in the target's virtual address space of an instruction for the specified line.


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
</table>
 




## -remarks



A line in a source file might correspond to multiple instructions and this method can return any one of these instructions.

For more information about source files, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-source-files">Using Source Files</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getlinebyoffset">GetLineByOffset</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols">IDebugSymbols</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols2">IDebugSymbols2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>
 

 

