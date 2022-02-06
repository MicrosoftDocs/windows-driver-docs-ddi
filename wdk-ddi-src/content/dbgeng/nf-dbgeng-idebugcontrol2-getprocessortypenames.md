---
UID: NF:dbgeng.IDebugControl2.GetProcessorTypeNames
title: IDebugControl2::GetProcessorTypeNames (dbgeng.h)
description: Learn about the GetProcessorTypeNames method, which returns the full name and abbreviated name of the specified processor type.
old-location: debugger\getprocessortypenames.htm
tech.root: debugger
ms.date: 02/06/2022
keywords: ["IDebugControl2::GetProcessorTypeNames"]
ms.keywords: GetProcessorTypeNames, GetProcessorTypeNames method [Windows Debugging], GetProcessorTypeNames method [Windows Debugging],IDebugControl interface, GetProcessorTypeNames method [Windows Debugging],IDebugControl2 interface, GetProcessorTypeNames method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetProcessorTypeNames method, IDebugControl2 interface [Windows Debugging],GetProcessorTypeNames method, IDebugControl2.GetProcessorTypeNames, IDebugControl2::GetProcessorTypeNames, IDebugControl3 interface [Windows Debugging],GetProcessorTypeNames method, IDebugControl3::GetProcessorTypeNames, IDebugControl::GetProcessorTypeNames, IDebugControl_f14b5f52-cf94-458b-bd1e-61c3ad66a597.xml, dbgeng/IDebugControl2::GetProcessorTypeNames, dbgeng/IDebugControl3::GetProcessorTypeNames, dbgeng/IDebugControl::GetProcessorTypeNames, debugger.getprocessortypenames
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
 - IDebugControl2::GetProcessorTypeNames
 - dbgeng/IDebugControl2::GetProcessorTypeNames
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl2::GetProcessorTypeNames
---

# IDebugControl2::GetProcessorTypeNames


## -description

The <b>GetProcessorTypeNames</b>  method returns the full name and abbreviated name of the specified processor type.

## -parameters

### -param Type [in]


Specifies the type of the processor whose name is requested.  See <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getactualprocessortype">GetActualProcessorType</a> for a list of possible values.

### -param FullNameBuffer [out, optional]


Receives the full name of the processor type.  If <i>FullNameBuffer</i> is <b>NULL</b>, this information is not returned.

### -param FullNameBufferSize [in]


Specifies the size, in characters, of the buffer that <i>FullNameBuffer</i> specifies. This size includes the space for the '\0' terminating character.

### -param FullNameSize [out, optional]


Receives the size in characters of the full name of the processor type. This size includes the space for the '\0' terminating character. If <i>FullNameSize</i> is <b>NULL</b>, this information is not returned.

### -param AbbrevNameBuffer [out, optional]


Receives the abbreviated name of the processor type.  If <i>AbbrevNameBuffer</i> is <b>NULL</b>, this information is not returned.

### -param AbbrevNameBufferSize [in]


Specifies the size, in characters, of the buffer that <i>AbbrevNameBuffer</i> specifies. This size includes the space for the '\0' terminating character.

### -param AbbrevNameSize [out, optional]


Receives the size in characters of the abbreviated name of the processor type. This size includes the space for the '\0' terminating character. If <i>AbbrevNameSize</i> is <b>NULL</b>, this information is not returned.

## -returns

This method may also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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
The method was successful.  However, at least one of <i>FullNameBuffer</i> or <i>AbbrevNameBuffer</i> was too small for the corresponding name, so the name was truncated.

</td>
</tr>
</table>

## -remarks

For more information, see <a href="/windows-hardware/drivers/debugger/target-information">Target Information</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getsupportedprocessortypes">GetSupportedProcessorTypes</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>

