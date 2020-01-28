---
UID: NF:dbgeng.IDebugControl4.GetProcessorTypeNamesWide
title: IDebugControl4::GetProcessorTypeNamesWide (dbgeng.h)
description: The GetProcessorTypeNamesWide method returns the full name and abbreviated name of the specified processor type.
old-location: debugger\getprocessortypenameswide.htm
tech.root: debugger
ms.assetid: 24787963-98c6-4c32-9ba8-2cd4778f8436
ms.date: 05/03/2018
ms.keywords: GetProcessorTypeNamesWide, GetProcessorTypeNamesWide method [Windows Debugging], GetProcessorTypeNamesWide method [Windows Debugging],IDebugControl4 interface, IDebugControl4 interface [Windows Debugging],GetProcessorTypeNamesWide method, IDebugControl4.GetProcessorTypeNamesWide, IDebugControl4::GetProcessorTypeNamesWide, dbgeng/IDebugControl4::GetProcessorTypeNamesWide, debugger.getprocessortypenameswide
f1_keywords:
 - "dbgeng/IDebugControl4.GetProcessorTypeNamesWide"
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
- IDebugControl4.GetProcessorTypeNamesWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl4::GetProcessorTypeNamesWide


## -description


The <b>GetProcessorTypeNamesWide</b>  method returns the full name and abbreviated name of the specified processor type.


## -parameters




### -param Type [in]

Specifies the type of the processor whose name is requested.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getactualprocessortype">GetActualProcessorType</a> for a list of possible values.


### -param FullNameBuffer [out, optional]

Receives the full name of the processor type.  If <i>FullNameBuffer</i> is <b>NULL</b>, this information is not returned.


### -param FullNameBufferSize [in]

Specifies the size, in characters, of the buffer that <i>FullNameBuffer</i> specifies.


### -param FullNameSize [out, optional]

Receives the size in characters of the full name of the processor type.  If <i>FullNameSize</i> is <b>NULL</b>, this information is not returned.


### -param AbbrevNameBuffer [out, optional]

Receives the abbreviated name of the processor type.  If <i>AbbrevNameBuffer</i> is <b>NULL</b>, this information is not returned.


### -param AbbrevNameBufferSize [in]

Specifies the size, in characters, of the buffer that <i>AbbrevNameBuffer</i> specifies.


### -param AbbrevNameSize [out, optional]

Receives the size in characters of the abbreviated name of the processor type.  If <i>AbbrevNameSize</i> is <b>NULL</b>, this information is not returned.


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



For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/target-information">Target Information</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getsupportedprocessortypes">GetSupportedProcessorTypes</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol4">IDebugControl4</a>
 

 

