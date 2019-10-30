---
UID: NF:dbgeng.IDebugControl3.SetExceptionFilterParameters
title: IDebugControl3::SetExceptionFilterParameters (dbgeng.h)
description: The SetExceptionFilterParameters method changes the break status and handling status for some exception filters.
old-location: debugger\setexceptionfilterparameters.htm
tech.root: debugger
ms.assetid: b749f96d-d04a-48f2-9012-b7c853e0de14
ms.date: 05/03/2018
ms.keywords: IDebugControl interface [Windows Debugging],SetExceptionFilterParameters method, IDebugControl2 interface [Windows Debugging],SetExceptionFilterParameters method, IDebugControl2::SetExceptionFilterParameters, IDebugControl3 interface [Windows Debugging],SetExceptionFilterParameters method, IDebugControl3.SetExceptionFilterParameters, IDebugControl3::SetExceptionFilterParameters, IDebugControl::SetExceptionFilterParameters, IDebugControl_4e60bce4-e40d-46b6-83ad-55559b97fbad.xml, SetExceptionFilterParameters, SetExceptionFilterParameters method [Windows Debugging], SetExceptionFilterParameters method [Windows Debugging],IDebugControl interface, SetExceptionFilterParameters method [Windows Debugging],IDebugControl2 interface, SetExceptionFilterParameters method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl2::SetExceptionFilterParameters, dbgeng/IDebugControl3::SetExceptionFilterParameters, dbgeng/IDebugControl::SetExceptionFilterParameters, debugger.setexceptionfilterparameters
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugControl.SetExceptionFilterParameters"
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
- IDebugControl.SetExceptionFilterParameters
- IDebugControl2.SetExceptionFilterParameters
- IDebugControl3.SetExceptionFilterParameters
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl3::SetExceptionFilterParameters


## -description


The <b>SetExceptionFilterParameters</b> method changes the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-filter-xxx">break status</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-filter-xxx">handling status</a> for some exception filters.


## -parameters




### -param Count [in]

Specifies the number of exception filters to change the parameters for.


### -param Params [in]

Specifies an array of exception filter parameters of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_exception_filter_parameters">DEBUG_EXCEPTION_FILTER_PARAMETERS</a>.  Only the <b>ExecutionOption</b>, <b>ContinueOption</b>, and <b>ExceptionCode</b> fields of these parameters are used.  The <b>ExceptionCode</b> field is used to identify the <a href="https://docs.microsoft.com/windows-hardware/drivers/">exception</a> whose exception filter will be changed.  <b>ExceptionOption</b> specifies the new break status and <b>ContinueOption</b> specifies the new handling status.

If the value of the <b>ExceptionOption</b> field is DEBUG_FILTER_REMOVE and the exception filter is an arbitrary exception filter, the exception filter will be removed.


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
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
The maximum number of arbitrary exception filters 

has been exceeded.

</td>
</tr>
</table>
 




## -remarks



For each of the exception filter parameters in <i>Params</i>, if the exception, identified by exception code, already has a filter (specific or arbitrary), that filter will be changed.  Otherwise, a new arbitrary exception filter will be added for the exception.

For more information about <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/event-filters">event filters</a>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/event-filters">Event Filters</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getexceptionfilterparameters">GetExceptionFilterParameters</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setspecificfilterparameters">SetSpecificFilterParameters</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/sx--sxd--sxe--sxi--sxn--sxr--sx---set-exceptions-">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>
 

 

