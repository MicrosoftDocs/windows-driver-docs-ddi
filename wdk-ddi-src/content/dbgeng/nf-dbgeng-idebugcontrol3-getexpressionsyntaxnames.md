---
UID: NF:dbgeng.IDebugControl3.GetExpressionSyntaxNames
title: IDebugControl3::GetExpressionSyntaxNames (dbgeng.h)
description: The GetExpressionSyntaxNames method returns the full and abbreviated names of an expression syntax.
old-location: debugger\getexpressionsyntaxnames.htm
tech.root: debugger
ms.assetid: c60b1d7b-b82d-4f59-a076-2122da97a161
ms.date: 05/03/2018
ms.keywords: GetExpressionSyntaxNames, GetExpressionSyntaxNames method [Windows Debugging], GetExpressionSyntaxNames method [Windows Debugging],IDebugControl3 interface, IDebugControl3 interface [Windows Debugging],GetExpressionSyntaxNames method, IDebugControl3.GetExpressionSyntaxNames, IDebugControl3::GetExpressionSyntaxNames, IDebugControl_9556ddd4-d38f-4c56-8456-81c12afb177e.xml, dbgeng/IDebugControl3::GetExpressionSyntaxNames, debugger.getexpressionsyntaxnames
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugControl3.GetExpressionSyntaxNames"
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
- IDebugControl3.GetExpressionSyntaxNames
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl3::GetExpressionSyntaxNames


## -description


The <b>GetExpressionSyntaxNames</b>  method returns the full and abbreviated names of an expression syntax.


## -parameters




### -param Index [in]

Specifies the index of the expression syntax.  <i>Index</i> should be between zero and the number of expression syntaxes returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getnumberexpressionsyntaxes">GetNumberExpressionSyntaxes</a> minus one.


### -param FullNameBuffer [out, optional]

Receives the full name of the expression syntax.  If <i>FullNameBuffer</i> is <b>NULL</b>, this information is not returned.


### -param FullNameBufferSize [in]

Specifies the size, in characters, of the buffer <i>FullNameBuffer</i>.


### -param FullNameSize [out, optional]

Receives the size, in characters, of the full name of the expression syntax.  If <i>FullNameSize</i> is <b>NULL</b>, this information is not returned.


### -param AbbrevNameBuffer [out, optional]

Receives the abbreviated name of the expression syntax.  If <i>AbbrevNameBuffer</i> is <b>NULL</b>, this information is not returned.


### -param AbbrevNameBufferSize [in]

Specifies the size, in characters, of the buffer <i>AbbrevNameBufferSize</i>.


### -param AbbrevNameSize [out, optional]

Receives the size, in characters, of the abbreviated name of the expression syntax.  If <i>AbbrevNameSize</i> is <b>NULL</b>, this information is not returned.


## -returns



This method can also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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
The method was successful.  However, either <i>FullNameBufferSize</i> or <i>AbbrevNameBufferSize</i> was smaller than the size of the respective expression syntax name, and the name was truncated to fit inside the buffer.

</td>
</tr>
</table>
 




## -remarks



Currently, there are two expression syntaxes, their full names are "Microsoft Assembler expressions" and "C++ source expressions."  The corresponding abbreviated expression syntaxes are "MASM" and "C++."




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-evaluate">Evaluate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getnumberexpressionsyntaxes">GetNumberExpressionSyntaxes</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-setexpressionsyntaxbyname">SetExpressionSyntaxByName</a>
 

 

