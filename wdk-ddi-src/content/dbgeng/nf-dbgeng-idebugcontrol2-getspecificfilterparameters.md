---
UID: NF:dbgeng.IDebugControl2.GetSpecificFilterParameters
title: IDebugControl2::GetSpecificFilterParameters (dbgeng.h)
description: The GetSpecificFilterParameters method returns the parameters for specific event filters.
old-location: debugger\getspecificfilterparameters.htm
tech.root: debugger
ms.assetid: d2140270-558d-4cd9-b497-f61be40c7a87
ms.date: 05/03/2018
keywords: ["IDebugControl2::GetSpecificFilterParameters"]
ms.keywords: GetSpecificFilterParameters, GetSpecificFilterParameters method [Windows Debugging], GetSpecificFilterParameters method [Windows Debugging],IDebugControl interface, GetSpecificFilterParameters method [Windows Debugging],IDebugControl2 interface, GetSpecificFilterParameters method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetSpecificFilterParameters method, IDebugControl2 interface [Windows Debugging],GetSpecificFilterParameters method, IDebugControl2.GetSpecificFilterParameters, IDebugControl2::GetSpecificFilterParameters, IDebugControl3 interface [Windows Debugging],GetSpecificFilterParameters method, IDebugControl3::GetSpecificFilterParameters, IDebugControl::GetSpecificFilterParameters, IDebugControl_ebe245a7-c76c-4b31-aa58-ccad250ed92a.xml, dbgeng/IDebugControl2::GetSpecificFilterParameters, dbgeng/IDebugControl3::GetSpecificFilterParameters, dbgeng/IDebugControl::GetSpecificFilterParameters, debugger.getspecificfilterparameters
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
 - IDebugControl2::GetSpecificFilterParameters
 - dbgeng/IDebugControl2::GetSpecificFilterParameters
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl.GetSpecificFilterParameters
 - IDebugControl2.GetSpecificFilterParameters
 - IDebugControl3.GetSpecificFilterParameters
---

# IDebugControl2::GetSpecificFilterParameters


## -description

The <b>GetSpecificFilterParameters</b> method returns the parameters for specific event filters.

## -parameters

### -param Start 

[in]
Specifies the index of the first specific event filter whose parameters will be returned.

### -param Count 

[in]
Specifies the number of specific event filters to return parameters for.

### -param Params 

[out]
Receives the parameters for the specific event filters.  <i>Params</i> is an array of elements of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_specific_filter_parameters">DEBUG_SPECIFIC_FILTER_PARAMETERS</a>.

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
</table>

## -remarks

For more information about <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/event-filters">event filters</a>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/event-filters">Event Filters</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getexceptionfilterparameters">GetExceptionFilterParameters</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setspecificfilterparameters">SetSpecificFilterParameters</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/sx--sxd--sxe--sxi--sxn--sxr--sx---set-exceptions-">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>

