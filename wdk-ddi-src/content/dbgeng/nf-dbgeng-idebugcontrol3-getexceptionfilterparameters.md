---
UID: NF:dbgeng.IDebugControl3.GetExceptionFilterParameters
title: IDebugControl3::GetExceptionFilterParameters method
author: windows-driver-content
description: The GetExceptionFilterParameters method returns the parameters for exception filters specified by exception codes or by index.
old-location: debugger\getexceptionfilterparameters.htm
old-project: debugger
ms.assetid: 6c3db06a-0305-480f-ab7f-38e4295ebe9b
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetExceptionFilterParameters method [Windows Debugging], GetExceptionFilterParameters method [Windows Debugging], IDebugControl interface, GetExceptionFilterParameters method [Windows Debugging], IDebugControl2 interface, GetExceptionFilterParameters method [Windows Debugging], IDebugControl3 interface, GetExceptionFilterParameters,IDebugControl3.GetExceptionFilterParameters, IDebugControl interface [Windows Debugging], GetExceptionFilterParameters method, IDebugControl2 interface [Windows Debugging], GetExceptionFilterParameters method, IDebugControl2::GetExceptionFilterParameters, IDebugControl3, IDebugControl3 interface [Windows Debugging], GetExceptionFilterParameters method, IDebugControl3::GetExceptionFilterParameters, IDebugControl::GetExceptionFilterParameters, IDebugControl_012d902c-ff4c-4ac8-9a35-b6cdcd1e2894.xml, dbgeng/IDebugControl2::GetExceptionFilterParameters, dbgeng/IDebugControl3::GetExceptionFilterParameters, dbgeng/IDebugControl::GetExceptionFilterParameters, debugger.getexceptionfilterparameters
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
-	IDebugControl.GetExceptionFilterParameters
-	IDebugControl2.GetExceptionFilterParameters
-	IDebugControl3.GetExceptionFilterParameters
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl3::GetExceptionFilterParameters method


## -description


The <b>GetExceptionFilterParameters</b> method returns the parameters for exception filters specified by exception codes or by index.


## -parameters




### -param Count [in]

Specifies the number of exception filters for which to return parameters.


### -param Codes [in, optional]

Specifies an array of exception codes.  The parameters for the exception filters with these exception codes will be returned.  If <i>Codes</i> is <b>NULL</b>, <i>Start</i> is used instead.


### -param Start [in]

Specifies the index of the first exception filter.  The parameters for the exception filters starting at <i>Start</i> will be returned.  If <i>Codes</i> is not <b>NULL</b>, <i>Start</i> is ignored.


### -param Params [out]

Receives the parameters for the exception filters specified by <i>Codes</i> or <i>Start</i>.  <i>Params</i> is an array of elements of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff541485">DEBUG_EXCEPTION_FILTER_PARAMETERS</a>.


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
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::GetExceptionFilterParameters method%20 RELEASE:%20(3/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

