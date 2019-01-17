---
UID: NF:dbgeng.IDebugControl.GetExecutingProcessorType
title: IDebugControl::GetExecutingProcessorType
description: The GetExecutingProcessorType method returns the executing processor type for the processor for which the last event occurred.
old-location: debugger\getexecutingprocessortype.htm
tech.root: debugger
ms.assetid: 62d0397b-da20-414e-accf-656749a771f6
ms.date: 05/03/2018
ms.keywords: GetExecutingProcessorType, GetExecutingProcessorType method [Windows Debugging], GetExecutingProcessorType method [Windows Debugging],IDebugControl interface, GetExecutingProcessorType method [Windows Debugging],IDebugControl2 interface, GetExecutingProcessorType method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetExecutingProcessorType method, IDebugControl.GetExecutingProcessorType, IDebugControl2 interface [Windows Debugging],GetExecutingProcessorType method, IDebugControl2::GetExecutingProcessorType, IDebugControl3 interface [Windows Debugging],GetExecutingProcessorType method, IDebugControl3::GetExecutingProcessorType, IDebugControl::GetExecutingProcessorType, IDebugControl_b2aad495-5a68-4888-bedb-da76edbfbe7a.xml, dbgeng/IDebugControl2::GetExecutingProcessorType, dbgeng/IDebugControl3::GetExecutingProcessorType, dbgeng/IDebugControl::GetExecutingProcessorType, debugger.getexecutingprocessortype
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
-	IDebugControl.GetExecutingProcessorType
-	IDebugControl2.GetExecutingProcessorType
-	IDebugControl3.GetExecutingProcessorType
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl::GetExecutingProcessorType


## -description


The <b>GetExecutingProcessorType</b> method returns the executing processor type for the processor for which the last event occurred.


## -parameters




### -param Type [out]

Receives the processor type.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff545572">GetActualProcessorType</a> for a list of possible values this parameter can receive.


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



For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558860">Target Information</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545572">GetActualProcessorType</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>
 

 

