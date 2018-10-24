---
UID: NF:dbgeng.IDebugControl2.SetSpecificFilterParameters
title: IDebugControl2::SetSpecificFilterParameters
author: windows-driver-content
description: The SetSpecificFilterParameters method changes the break status and handling status for some specific event filters.
old-location: debugger\setspecificfilterparameters.htm
tech.root: debugger
ms.assetid: 97eb6db8-3c0a-44b4-8fb4-9e42ee9f9856
ms.date: 05/03/2018
ms.keywords: IDebugControl interface [Windows Debugging],SetSpecificFilterParameters method, IDebugControl2 interface [Windows Debugging],SetSpecificFilterParameters method, IDebugControl2.SetSpecificFilterParameters, IDebugControl2::SetSpecificFilterParameters, IDebugControl3 interface [Windows Debugging],SetSpecificFilterParameters method, IDebugControl3::SetSpecificFilterParameters, IDebugControl::SetSpecificFilterParameters, IDebugControl_9bf01d08-9fc1-4ddf-b8dd-c6db0b568f83.xml, SetSpecificFilterParameters, SetSpecificFilterParameters method [Windows Debugging], SetSpecificFilterParameters method [Windows Debugging],IDebugControl interface, SetSpecificFilterParameters method [Windows Debugging],IDebugControl2 interface, SetSpecificFilterParameters method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl2::SetSpecificFilterParameters, dbgeng/IDebugControl3::SetSpecificFilterParameters, dbgeng/IDebugControl::SetSpecificFilterParameters, debugger.setspecificfilterparameters
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
-	IDebugControl.SetSpecificFilterParameters
-	IDebugControl2.SetSpecificFilterParameters
-	IDebugControl3.SetSpecificFilterParameters
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl2::SetSpecificFilterParameters


## -description


The <b>SetSpecificFilterParameters</b> method changes the <a href="https://msdn.microsoft.com/1f8f738b-7b2b-419a-949e-b71f937de02d">break status</a> and <a href="https://msdn.microsoft.com/1f8f738b-7b2b-419a-949e-b71f937de02d">handling status</a> for some specific event filters.


## -parameters




### -param Start [in]

Specifies the index of the first specific event filter whose parameters will be changed.


### -param Count [in]

Specifies the number of specific event filters whose parameters will be changed.


### -param Params [in]

Specifies an array of specific event filter parameters of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff541637">DEBUG_SPECIFIC_FILTER_PARAMETERS</a>.  Only the <b>ExecutionOption</b> and <b>ContinueOption</b> members are used.  <b>ExceptionOption</b> specifies the new break status and <b>ContinueOption</b> specifies the new handling status.


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
</table>
 




## -remarks



For more information about <a href="https://msdn.microsoft.com/library/windows/hardware/ff543071">event filters</a>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543071">Event Filters</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548398">GetSpecificFilterParameters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556683">SetExceptionFilterParameters</a>



<a href="https://msdn.microsoft.com/fdb5059f-e7d9-4e14-aa3d-030e72c30732">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>
 

 

