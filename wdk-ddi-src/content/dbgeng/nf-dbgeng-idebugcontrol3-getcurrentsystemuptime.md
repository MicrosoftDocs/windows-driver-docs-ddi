---
UID: NF:dbgeng.IDebugControl3.GetCurrentSystemUpTime
title: IDebugControl3::GetCurrentSystemUpTime (dbgeng.h)
description: The GetCurrentSystemUpTime method returns the number of seconds the current target's computer has been running since it was last started.
old-location: debugger\getcurrentsystemuptime.htm
tech.root: debugger
ms.assetid: 0009e11d-73d0-4ca2-afbc-5f2999e829ac
ms.date: 05/03/2018
keywords: ["IDebugControl3::GetCurrentSystemUpTime"]
ms.keywords: GetCurrentSystemUpTime, GetCurrentSystemUpTime method [Windows Debugging], GetCurrentSystemUpTime method [Windows Debugging],IDebugControl2 interface, GetCurrentSystemUpTime method [Windows Debugging],IDebugControl3 interface, IDebugControl2 interface [Windows Debugging],GetCurrentSystemUpTime method, IDebugControl2::GetCurrentSystemUpTime, IDebugControl3 interface [Windows Debugging],GetCurrentSystemUpTime method, IDebugControl3.GetCurrentSystemUpTime, IDebugControl3::GetCurrentSystemUpTime, IDebugControl_e10ddd31-60fe-4353-befe-45a04154615b.xml, dbgeng/IDebugControl2::GetCurrentSystemUpTime, dbgeng/IDebugControl3::GetCurrentSystemUpTime, debugger.getcurrentsystemuptime
f1_keywords:
 - "dbgeng/IDebugControl2.GetCurrentSystemUpTime"
 - "IDebugControl2.GetCurrentSystemUpTime"
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
- IDebugControl2.GetCurrentSystemUpTime
- IDebugControl3.GetCurrentSystemUpTime
targetos: Windows
req.typenames: 
---

# IDebugControl3::GetCurrentSystemUpTime


## -description


The <b>GetCurrentSystemUpTime</b> method returns the number of seconds the current target's computer has been running since it was last started.


## -parameters




### -param UpTime 
[out]
Receives the number of seconds the computer has been running, or <b>0</b> if the engine is unable to determine the running time.


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
The value of the variable <i>UpTime</i> is either the desired information or is <b>0</b>.

</td>
</tr>
</table>
 




## -remarks



For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/target-information">Target Information</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getcurrenttimedate">GetCurrentTimeDate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>
 

 

