---
UID: NF:dbgeng.IDebugControl.GetNumberSupportedProcessorTypes
title: IDebugControl::GetNumberSupportedProcessorTypes method
author: windows-driver-content
description: The GetNumberSupportedProcessorTypes method returns the number of processor types supported by the engine.
old-location: debugger\getnumbersupportedprocessortypes.htm
old-project: debugger
ms.assetid: 6057fd27-75be-403b-a939-7865de45e031
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetNumberSupportedProcessorTypes method [Windows Debugging], GetNumberSupportedProcessorTypes method [Windows Debugging], IDebugControl interface, GetNumberSupportedProcessorTypes method [Windows Debugging], IDebugControl2 interface, GetNumberSupportedProcessorTypes method [Windows Debugging], IDebugControl3 interface, GetNumberSupportedProcessorTypes,IDebugControl.GetNumberSupportedProcessorTypes, IDebugControl, IDebugControl interface [Windows Debugging], GetNumberSupportedProcessorTypes method, IDebugControl2 interface [Windows Debugging], GetNumberSupportedProcessorTypes method, IDebugControl2::GetNumberSupportedProcessorTypes, IDebugControl3 interface [Windows Debugging], GetNumberSupportedProcessorTypes method, IDebugControl3::GetNumberSupportedProcessorTypes, IDebugControl::GetNumberSupportedProcessorTypes, IDebugControl_5b3a8335-0e6f-4f83-9549-fa53ce9eb1d5.xml, dbgeng/IDebugControl2::GetNumberSupportedProcessorTypes, dbgeng/IDebugControl3::GetNumberSupportedProcessorTypes, dbgeng/IDebugControl::GetNumberSupportedProcessorTypes, debugger.getnumbersupportedprocessortypes
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
-	IDebugControl.GetNumberSupportedProcessorTypes
-	IDebugControl2.GetNumberSupportedProcessorTypes
-	IDebugControl3.GetNumberSupportedProcessorTypes
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl::GetNumberSupportedProcessorTypes method


## -description


The GetNumberSupportedProcessorTypes method returns the number of processor types supported by the engine.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548438">GetSupportedProcessorTypes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>
 

 

