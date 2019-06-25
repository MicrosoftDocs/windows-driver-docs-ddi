---
UID: NF:dbgeng.IDebugSymbols3.GetOffsetByLineWide
title: IDebugSymbols3::GetOffsetByLineWide (dbgeng.h)
description: The GetOffsetByLineWide method returns the location of the instruction that corresponds to a specified line in the source code.
old-location: debugger\getoffsetbylinewide.htm
tech.root: debugger
ms.assetid: ba09333e-84a5-4166-a859-e09c0cf74347
ms.date: 05/03/2018
ms.keywords: GetOffsetByLineWide, GetOffsetByLineWide method [Windows Debugging], GetOffsetByLineWide method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetOffsetByLineWide method, IDebugSymbols3.GetOffsetByLineWide, IDebugSymbols3::GetOffsetByLineWide, dbgeng/IDebugSymbols3::GetOffsetByLineWide, debugger.getoffsetbylinewide
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugSymbols3.GetOffsetByLineWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::GetOffsetByLineWide


## -description


The <b>GetOffsetByLineWide</b>  method returns the location of the instruction that corresponds to a specified line in the source code.


## -parameters




### -param Line [in]

Specifies the line number in the source file.


### -param File [in]

Specifies the file name of the source file.


### -param Offset [out]

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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getlinebyoffset">GetLineByOffset</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>
 

 

