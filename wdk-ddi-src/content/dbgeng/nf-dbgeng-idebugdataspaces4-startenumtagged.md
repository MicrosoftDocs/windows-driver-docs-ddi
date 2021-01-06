---
UID: NF:dbgeng.IDebugDataSpaces4.StartEnumTagged
title: IDebugDataSpaces4::StartEnumTagged (dbgeng.h)
description: The StartEnumTagged method initializes a enumeration over the tagged data associated with a debugger session.
old-location: debugger\startenumtagged.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugDataSpaces4::StartEnumTagged"]
ms.keywords: IDebugDataSpaces3 interface [Windows Debugging],StartEnumTagged method, IDebugDataSpaces3::StartEnumTagged, IDebugDataSpaces4 interface [Windows Debugging],StartEnumTagged method, IDebugDataSpaces4.StartEnumTagged, IDebugDataSpaces4::StartEnumTagged, IDebugDataSpaces_bc6f5148-04e1-4912-8ca2-8c095519af8f.xml, StartEnumTagged, StartEnumTagged method [Windows Debugging], StartEnumTagged method [Windows Debugging],IDebugDataSpaces3 interface, StartEnumTagged method [Windows Debugging],IDebugDataSpaces4 interface, dbgeng/IDebugDataSpaces3::StartEnumTagged, dbgeng/IDebugDataSpaces4::StartEnumTagged, debugger.startenumtagged
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
 - IDebugDataSpaces4::StartEnumTagged
 - dbgeng/IDebugDataSpaces4::StartEnumTagged
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugDataSpaces3.StartEnumTagged
 - IDebugDataSpaces4.StartEnumTagged
---

# IDebugDataSpaces4::StartEnumTagged


## -description

The <b>StartEnumTagged</b> method initializes a enumeration over the tagged data associated with a debugger session.

## -parameters

### -param Handle 

[out]
Receives the handle identifying the enumeration.  This handle can be passed to <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugdataspaces4-getnexttagged">GetNextTagged</a> and <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugdataspaces4-endenumtagged">EndEnumTagged</a>.

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
</table>

## -remarks

The resources held by an enumeration created with this method can be released using <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugdataspaces4-endenumtagged">EndEnumTagged</a>.
