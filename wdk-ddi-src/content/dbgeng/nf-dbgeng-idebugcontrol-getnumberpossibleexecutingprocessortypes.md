---
UID: NF:dbgeng.IDebugControl.GetNumberPossibleExecutingProcessorTypes
title: IDebugControl::GetNumberPossibleExecutingProcessorTypes
author: windows-driver-content
description: The GetNumberPossibleExecutingProcessorTypes method returns the number of processor types that are supported by the computer running the current target.
old-location: debugger\getnumberpossibleexecutingprocessortypes.htm
tech.root: debugger
ms.assetid: 9e4ca8a6-f33f-4403-a52f-f242ce40aac8
ms.date: 05/03/2018
ms.keywords: GetNumberPossibleExecutingProcessorTypes, GetNumberPossibleExecutingProcessorTypes method [Windows Debugging], GetNumberPossibleExecutingProcessorTypes method [Windows Debugging],IDebugControl interface, GetNumberPossibleExecutingProcessorTypes method [Windows Debugging],IDebugControl2 interface, GetNumberPossibleExecutingProcessorTypes method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetNumberPossibleExecutingProcessorTypes method, IDebugControl.GetNumberPossibleExecutingProcessorTypes, IDebugControl2 interface [Windows Debugging],GetNumberPossibleExecutingProcessorTypes method, IDebugControl2::GetNumberPossibleExecutingProcessorTypes, IDebugControl3 interface [Windows Debugging],GetNumberPossibleExecutingProcessorTypes method, IDebugControl3::GetNumberPossibleExecutingProcessorTypes, IDebugControl::GetNumberPossibleExecutingProcessorTypes, IDebugControl_62f066c6-6ffb-4323-ad82-786a8a763783.xml, dbgeng/IDebugControl2::GetNumberPossibleExecutingProcessorTypes, dbgeng/IDebugControl3::GetNumberPossibleExecutingProcessorTypes, dbgeng/IDebugControl::GetNumberPossibleExecutingProcessorTypes, debugger.getnumberpossibleexecutingprocessortypes
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
-	IDebugControl.GetNumberPossibleExecutingProcessorTypes
-	IDebugControl2.GetNumberPossibleExecutingProcessorTypes
-	IDebugControl3.GetNumberPossibleExecutingProcessorTypes
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl::GetNumberPossibleExecutingProcessorTypes


## -description


The <b>GetNumberPossibleExecutingProcessorTypes</b> method returns the number of processor types that are supported by the computer running the current target.


## -parameters




### -param Number [out]

Receives the number of processor types.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548130">GetPossibleExecutingProcessorTypes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>
 

 

