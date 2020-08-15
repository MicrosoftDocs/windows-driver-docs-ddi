---
UID: NF:dbgeng.IDebugSymbols3.GetLineByOffsetWide
title: IDebugSymbols3::GetLineByOffsetWide (dbgeng.h)
description: The GetLineByOffsetWide method returns the source filename and the line number within the source file of an instruction in the target.
old-location: debugger\getlinebyoffsetwide.htm
tech.root: debugger
ms.assetid: e780be4b-ac62-43c2-9767-7745ff1c7dbb
ms.date: 05/03/2018
keywords: ["IDebugSymbols3::GetLineByOffsetWide"]
ms.keywords: GetLineByOffsetWide, GetLineByOffsetWide method [Windows Debugging], GetLineByOffsetWide method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetLineByOffsetWide method, IDebugSymbols3.GetLineByOffsetWide, IDebugSymbols3::GetLineByOffsetWide, dbgeng/IDebugSymbols3::GetLineByOffsetWide, debugger.getlinebyoffsetwide
f1_keywords:
 - "dbgeng/IDebugSymbols3.GetLineByOffsetWide"
 - "IDebugSymbols3.GetLineByOffsetWide"
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
- IDebugSymbols3.GetLineByOffsetWide
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::GetLineByOffsetWide


## -description


The <b>GetLineByOffsetWide</b>  method returns the source filename and the line number within the source file of an instruction in the target.


## -parameters




### -param Offset 
[in]
Specifies the location in the target's virtual address space of the instruction for which to return the source file and line number.


### -param Line 
[out, optional]
Receives the line number within the source file of the instruction specified by <i>Offset</i>.  If <i>Line</i> is <b>NULL</b>, this information is not returned.


### -param FileBuffer 
[out, optional]
Receives the file name of the file that contains the instruction specified by <i>Offset</i>.  If <i>FileBuffer</i> is <b>NULL</b>, this information is not returned.


### -param FileBufferSize 
[in]
Specifies the size, in characters, of the <i>FileBuffer</i> buffer.


### -param FileSize 
[out, optional]
Specifies the size, in characters, of the source filename.  If <i>FileSize</i> is <b>NULL</b>, this information is not returned.


### -param Displacement 
[out, optional]
Receives the difference between the location specified in <i>Offset</i> and the location of the first instruction of the returned line.  If <i>Displacement</i> is <b>NULL</b>, this information is not returned.


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
The method was successful. However, the buffer was not large enough to hold the name of the source file and the name was truncated.

</td>
</tr>
</table>
 




## -remarks



For more information about source files, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-source-files">Using Source Files</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getoffsetbyline">GetOffsetByLine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>
 

 

