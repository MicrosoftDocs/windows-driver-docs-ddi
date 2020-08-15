---
UID: NF:dbgeng.IDebugControl2.GetExceptionFilterParameters
title: IDebugControl2::GetExceptionFilterParameters (dbgeng.h)
description: The GetExceptionFilterParameters method returns the parameters for exception filters specified by exception codes or by index.
old-location: debugger\getexceptionfilterparameters.htm
tech.root: debugger
ms.assetid: 6c3db06a-0305-480f-ab7f-38e4295ebe9b
ms.date: 05/03/2018
keywords: ["IDebugControl2::GetExceptionFilterParameters"]
ms.keywords: GetExceptionFilterParameters, GetExceptionFilterParameters method [Windows Debugging], GetExceptionFilterParameters method [Windows Debugging],IDebugControl interface, GetExceptionFilterParameters method [Windows Debugging],IDebugControl2 interface, GetExceptionFilterParameters method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetExceptionFilterParameters method, IDebugControl2 interface [Windows Debugging],GetExceptionFilterParameters method, IDebugControl2.GetExceptionFilterParameters, IDebugControl2::GetExceptionFilterParameters, IDebugControl3 interface [Windows Debugging],GetExceptionFilterParameters method, IDebugControl3::GetExceptionFilterParameters, IDebugControl::GetExceptionFilterParameters, IDebugControl_012d902c-ff4c-4ac8-9a35-b6cdcd1e2894.xml, dbgeng/IDebugControl2::GetExceptionFilterParameters, dbgeng/IDebugControl3::GetExceptionFilterParameters, dbgeng/IDebugControl::GetExceptionFilterParameters, debugger.getexceptionfilterparameters
f1_keywords:
 - "dbgeng/IDebugControl.GetExceptionFilterParameters"
 - "IDebugControl.GetExceptionFilterParameters"
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
- IDebugControl.GetExceptionFilterParameters
- IDebugControl2.GetExceptionFilterParameters
- IDebugControl3.GetExceptionFilterParameters
targetos: Windows
req.typenames: 
---

# IDebugControl2::GetExceptionFilterParameters


## -description


The <b>GetExceptionFilterParameters</b> method returns the parameters for exception filters specified by exception codes or by index.


## -parameters




### -param Count 
[in]
Specifies the number of exception filters for which to return parameters.


### -param Codes 
[in, optional]
Specifies an array of exception codes.  The parameters for the exception filters with these exception codes will be returned.  If <i>Codes</i> is <b>NULL</b>, <i>Start</i> is used instead.


### -param Start 
[in]
Specifies the index of the first exception filter.  The parameters for the exception filters starting at <i>Start</i> will be returned.  If <i>Codes</i> is not <b>NULL</b>, <i>Start</i> is ignored.


### -param Params 
[out]
Receives the parameters for the exception filters specified by <i>Codes</i> or <i>Start</i>.  <i>Params</i> is an array of elements of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_exception_filter_parameters">DEBUG_EXCEPTION_FILTER_PARAMETERS</a>.


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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getspecificfilterparameters">GetSpecificFilterParameters</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setexceptionfilterparameters">SetExceptionFilterParameters</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/sx--sxd--sxe--sxi--sxn--sxr--sx---set-exceptions-">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>
 

 

