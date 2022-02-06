---
UID: NF:dbgeng.IDebugControl3.GetExpressionSyntaxNames
title: IDebugControl3::GetExpressionSyntaxNames (dbgeng.h)
description: The GetExpressionSyntaxNames method returns the full and abbreviated names of an expression syntax.
old-location: debugger\getexpressionsyntaxnames.htm
tech.root: debugger
ms.date: 02/06/2022
keywords: ["IDebugControl3::GetExpressionSyntaxNames"]
ms.keywords: GetExpressionSyntaxNames, GetExpressionSyntaxNames method [Windows Debugging], GetExpressionSyntaxNames method [Windows Debugging],IDebugControl3 interface, IDebugControl3 interface [Windows Debugging],GetExpressionSyntaxNames method, IDebugControl3.GetExpressionSyntaxNames, IDebugControl3::GetExpressionSyntaxNames, IDebugControl_9556ddd4-d38f-4c56-8456-81c12afb177e.xml, dbgeng/IDebugControl3::GetExpressionSyntaxNames, debugger.getexpressionsyntaxnames
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
 - IDebugControl3::GetExpressionSyntaxNames
 - dbgeng/IDebugControl3::GetExpressionSyntaxNames
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl3::GetExpressionSyntaxNames
---

# IDebugControl3::GetExpressionSyntaxNames


## -description

The <b>GetExpressionSyntaxNames</b>  method returns the full and abbreviated names of an expression syntax.

## -parameters

### -param Index [in]


Specifies the index of the expression syntax.  <i>Index</i> should be between zero and the number of expression syntaxes returned by <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getnumberexpressionsyntaxes">GetNumberExpressionSyntaxes</a> minus one.

### -param FullNameBuffer [out, optional]


Receives the full name of the expression syntax. If <i>FullNameBuffer</i> is <b>NULL</b>, this information is not returned.

### -param FullNameBufferSize [in]


Specifies the size, in characters, of the buffer <i>FullNameBuffer</i>. This size includes the space for the '\0' terminating character.

### -param FullNameSize [out, optional]


Receives the size, in characters, of the full name of the expression syntax. This size includes the space for the '\0' terminating character. If <i>FullNameSize</i> is <b>NULL</b>, this information is not returned.

### -param AbbrevNameBuffer [out, optional]


Receives the abbreviated name of the expression syntax. This size includes the space for the '\0' terminating character. If <i>AbbrevNameBuffer</i> is <b>NULL</b>, this information is not returned.

### -param AbbrevNameBufferSize [in]


Specifies the size, in characters, of the buffer <i>AbbrevNameBufferSize</i>. This size includes the space for the '\0' terminating character.

### -param AbbrevNameSize [out, optional]


Receives the size, in characters, of the abbreviated name of the expression syntax. This size includes the space for the '\0' terminating character. If <i>AbbrevNameSize</i> is <b>NULL</b>, this information is not returned.

## -returns

This method can also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-evaluate">Evaluate</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getnumberexpressionsyntaxes">GetNumberExpressionSyntaxes</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setexpressionsyntaxbyname">SetExpressionSyntaxByName</a>

