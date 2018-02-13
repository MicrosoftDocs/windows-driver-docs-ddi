---
UID: NF:dbgeng.IDebugControl3.SetSpecificFilterParameters
title: IDebugControl3::SetSpecificFilterParameters method
author: windows-driver-content
description: The SetSpecificFilterParameters method changes the break status and handling status for some specific event filters.
old-location: debugger\setspecificfilterparameters.htm
old-project: debugger
ms.assetid: 97eb6db8-3c0a-44b4-8fb4-9e42ee9f9856
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugControl2, SetSpecificFilterParameters, IDebugControl3::SetSpecificFilterParameters, IDebugControl_9bf01d08-9fc1-4ddf-b8dd-c6db0b568f83.xml, IDebugControl2::SetSpecificFilterParameters, SetSpecificFilterParameters method [Windows Debugging], IDebugControl2 interface, IDebugControl2 interface [Windows Debugging], SetSpecificFilterParameters method, IDebugControl3, dbgeng/IDebugControl3::SetSpecificFilterParameters, IDebugControl, IDebugControl::SetSpecificFilterParameters, dbgeng/IDebugControl::SetSpecificFilterParameters, dbgeng/IDebugControl2::SetSpecificFilterParameters, SetSpecificFilterParameters method [Windows Debugging], IDebugControl3 interface, IDebugControl interface [Windows Debugging], SetSpecificFilterParameters method, SetSpecificFilterParameters method [Windows Debugging], IDebugControl3 interface [Windows Debugging], SetSpecificFilterParameters method, SetSpecificFilterParameters method [Windows Debugging], IDebugControl interface, debugger.setspecificfilterparameters
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugControl.SetSpecificFilterParameters
-	IDebugControl2.SetSpecificFilterParameters
-	IDebugControl3.SetSpecificFilterParameters
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugControl3::SetSpecificFilterParameters method


## -description


The <b>SetSpecificFilterParameters</b> method changes the <a href="https://msdn.microsoft.com/1f8f738b-7b2b-419a-949e-b71f937de02d">break status</a> and <a href="https://msdn.microsoft.com/1f8f738b-7b2b-419a-949e-b71f937de02d">handling status</a> for some specific event filters.


## -syntax


````
HRESULT SetSpecificFilterParameters(
  [in] ULONG                             Start,
  [in] ULONG                             Count,
  [in] PDEBUG_SPECIFIC_FILTER_PARAMETERS Params
);
````


## -parameters




### -param Start [in]

Specifies the index of the first specific event filter whose parameters will be changed.


### -param Count [in]

Specifies the number of specific event filters whose parameters will be changed.


### -param Params [in]

Specifies an array of specific event filter parameters of type <a href="..\dbgeng\ns-dbgeng-_debug_specific_filter_parameters.md">DEBUG_SPECIFIC_FILTER_PARAMETERS</a>.  Only the <b>ExecutionOption</b> and <b>ContinueOption</b> members are used.  <b>ExceptionOption</b> specifies the new break status and <b>ContinueOption</b> specifies the new handling status.


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



<a href="https://msdn.microsoft.com/fdb5059f-e7d9-4e14-aa3d-030e72c30732">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556683">SetExceptionFilterParameters</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::SetSpecificFilterParameters method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

