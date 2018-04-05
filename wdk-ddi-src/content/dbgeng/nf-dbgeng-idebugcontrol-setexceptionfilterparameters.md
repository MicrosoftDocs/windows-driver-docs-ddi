---
UID: NF:dbgeng.IDebugControl.SetExceptionFilterParameters
title: IDebugControl::SetExceptionFilterParameters method
author: windows-driver-content
description: The SetExceptionFilterParameters method changes the break status and handling status for some exception filters.
old-location: debugger\setexceptionfilterparameters.htm
old-project: debugger
ms.assetid: b749f96d-d04a-48f2-9012-b7c853e0de14
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: IDebugControl, IDebugControl interface [Windows Debugging], SetExceptionFilterParameters method, IDebugControl2 interface [Windows Debugging], SetExceptionFilterParameters method, IDebugControl2::SetExceptionFilterParameters, IDebugControl3 interface [Windows Debugging], SetExceptionFilterParameters method, IDebugControl3::SetExceptionFilterParameters, IDebugControl::SetExceptionFilterParameters, IDebugControl_4e60bce4-e40d-46b6-83ad-55559b97fbad.xml, SetExceptionFilterParameters method [Windows Debugging], SetExceptionFilterParameters method [Windows Debugging], IDebugControl interface, SetExceptionFilterParameters method [Windows Debugging], IDebugControl2 interface, SetExceptionFilterParameters method [Windows Debugging], IDebugControl3 interface, SetExceptionFilterParameters,IDebugControl.SetExceptionFilterParameters, dbgeng/IDebugControl2::SetExceptionFilterParameters, dbgeng/IDebugControl3::SetExceptionFilterParameters, dbgeng/IDebugControl::SetExceptionFilterParameters, debugger.setexceptionfilterparameters
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugControl.SetExceptionFilterParameters
-	IDebugControl2.SetExceptionFilterParameters
-	IDebugControl3.SetExceptionFilterParameters
product:
- Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl::SetExceptionFilterParameters method


## -description


The <b>SetExceptionFilterParameters</b> method changes the <a href="https://msdn.microsoft.com/1f8f738b-7b2b-419a-949e-b71f937de02d">break status</a> and <a href="https://msdn.microsoft.com/1f8f738b-7b2b-419a-949e-b71f937de02d">handling status</a> for some exception filters.


## -parameters




### -param Count [in]

Specifies the number of exception filters to change the parameters for.


### -param Params [in]

Specifies an array of exception filter parameters of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff541485">DEBUG_EXCEPTION_FILTER_PARAMETERS</a>.  Only the <b>ExecutionOption</b>, <b>ContinueOption</b>, and <b>ExceptionCode</b> fields of these parameters are used.  The <b>ExceptionCode</b> field is used to identify the <a href="https://msdn.microsoft.com/0dd010e7-3e10-422a-adcb-8fe7df9e29ab">exception</a> whose exception filter will be changed.  <b>ExceptionOption</b> specifies the new break status and <b>ContinueOption</b> specifies the new handling status.

If the value of the <b>ExceptionOption</b> field is DEBUG_FILTER_REMOVE and the exception filter is an arbitrary exception filter, the exception filter will be removed.


## -returns



This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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

For more information about <a href="https://msdn.microsoft.com/library/windows/hardware/ff543071">event filters</a>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543071">Event Filters</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546650">GetExceptionFilterParameters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556795">SetSpecificFilterParameters</a>



<a href="https://msdn.microsoft.com/fdb5059f-e7d9-4e14-aa3d-030e72c30732">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>
 

 

