---
UID: NF:dbgeng.IDebugControl4.GetEventFilterTextWide
title: IDebugControl4::GetEventFilterTextWide (dbgeng.h)
description: The GetEventFilterTextWide method returns a short description of an event for a specific filter.
old-location: debugger\geteventfiltertextwide.htm
tech.root: debugger
ms.date: 02/06/2022
keywords: ["IDebugControl4::GetEventFilterTextWide"]
ms.keywords: GetEventFilterTextWide, GetEventFilterTextWide method [Windows Debugging], GetEventFilterTextWide method [Windows Debugging],IDebugControl4 interface, IDebugControl4 interface [Windows Debugging],GetEventFilterTextWide method, IDebugControl4.GetEventFilterTextWide, IDebugControl4::GetEventFilterTextWide, dbgeng/IDebugControl4::GetEventFilterTextWide, debugger.geteventfiltertextwide
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
 - IDebugControl4::GetEventFilterTextWide
 - dbgeng/IDebugControl4::GetEventFilterTextWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl4::GetEventFilterTextWide
---

# IDebugControl4::GetEventFilterTextWide


## -description

The <b>GetEventFilterTextWide</b>  method returns a short description of an event for a specific filter.

## -parameters

### -param Index [in]


Specifies the index of the event filter whose description will be returned.  Only the specific filters have a description attached to them; <i>Index</i> must refer to a specific filter.

### -param Buffer [out, optional]


Receives the description of the specific filter.

### -param BufferSize [in]


Specifies the size, in characters, of the buffer that <i>Buffer</i> specifies. This size includes the space for the '\0' terminating character.

### -param TextSize [out, optional]


Receives the size of the event description. This size includes the space for the '\0' terminating character. If <i>TextSize</i> is <b>NULL</b>, this information is not returned.

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
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
<i>Index</i> did not refer to a specific filter.  This can occur if <i>Index</i> refers to an arbitrary exception filter.

</td>
</tr>
</table>

## -remarks

For more information about <a href="/windows-hardware/drivers/debugger/event-filters">event filters</a>, see <a href="/windows-hardware/drivers/debugger/event-filters">Event Filters</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getspecificfilterparameters">GetSpecificFilterParameters</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol4">IDebugControl4</a>



<a href="/windows-hardware/drivers/debugger/sx--sxd--sxe--sxi--sxn--sxr--sx---set-exceptions-">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>

