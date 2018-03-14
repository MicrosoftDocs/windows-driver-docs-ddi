---
UID: NF:dbgeng.IDebugControl2.GetCurrentTimeDate
title: IDebugControl2::GetCurrentTimeDate method
author: windows-driver-content
description: The GetCurrentTimeDate method returns the time of the current target.
old-location: debugger\getcurrenttimedate.htm
old-project: debugger
ms.assetid: 2b3c5a9d-32a9-4c2a-9f99-694b652c5653
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetCurrentTimeDate method [Windows Debugging], GetCurrentTimeDate method [Windows Debugging], IDebugControl2 interface, GetCurrentTimeDate method [Windows Debugging], IDebugControl3 interface, GetCurrentTimeDate,IDebugControl2.GetCurrentTimeDate, IDebugControl2, IDebugControl2 interface [Windows Debugging], GetCurrentTimeDate method, IDebugControl2::GetCurrentTimeDate, IDebugControl3 interface [Windows Debugging], GetCurrentTimeDate method, IDebugControl3::GetCurrentTimeDate, IDebugControl_166ad959-02b4-4b42-8acd-1456d224f9e7.xml, dbgeng/IDebugControl2::GetCurrentTimeDate, dbgeng/IDebugControl3::GetCurrentTimeDate, debugger.getcurrenttimedate
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
-	IDebugControl2.GetCurrentTimeDate
-	IDebugControl3.GetCurrentTimeDate
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl2::GetCurrentTimeDate method


## -description


The <b>GetCurrentTimeDate</b> method returns the time of the current target.


## -syntax


````
HRESULT GetCurrentTimeDate(
  [out] PULONG TimeDate
);
````


## -parameters




### -param TimeDate [out]

Receives the time and date.  This is the number of seconds since the beginning of 1970, or <b>0</b> if the current time could not be determined.


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
The value of the variable <i>TimeDate</i> is either the desired information or is <b>0</b>.

</td>
</tr>
</table>
 




## -remarks



For live debugging sessions, this will be the current time as reported by the target's computer.  For static debugging sessions, such as crash dump files, this will be the time the crash dump file was created.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558860">Target Information</a>.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545883">GetCurrentSystemUpTime</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



 

 


