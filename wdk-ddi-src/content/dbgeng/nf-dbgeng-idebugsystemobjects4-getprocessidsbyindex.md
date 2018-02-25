---
UID: NF:dbgeng.IDebugSystemObjects4.GetProcessIdsByIndex
title: IDebugSystemObjects4::GetProcessIdsByIndex method
author: windows-driver-content
description: The GetProcessIdsByIndex method returns the engine process ID and system process ID for the specified processes in the current target.
old-location: debugger\getprocessidsbyindex.htm
old-project: debugger
ms.assetid: 2ae042c5-9c2a-4de4-817c-c9b97f979684
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., 4, :, B, D, G, GetProcessIdsByIndex method [Windows Debugging], GetProcessIdsByIndex method [Windows Debugging], IDebugSystemObjects interface, GetProcessIdsByIndex method [Windows Debugging], IDebugSystemObjects2 interface, GetProcessIdsByIndex method [Windows Debugging], IDebugSystemObjects3 interface, GetProcessIdsByIndex method [Windows Debugging], IDebugSystemObjects4 interface, GetProcessIdsByIndex,IDebugSystemObjects.GetProcessIdsByIndex, GetProcessIdsByIndex,IDebugSystemObjects2.GetProcessIdsByIndex, GetProcessIdsByIndex,IDebugSystemObjects3.GetProcessIdsByIndex, GetProcessIdsByIndex,IDebugSystemObjects4.GetProcessIdsByIndex, I, IDebugSystemObjects, IDebugSystemObjects interface [Windows Debugging], GetProcessIdsByIndex method, IDebugSystemObjects2, IDebugSystemObjects2 interface [Windows Debugging], GetProcessIdsByIndex method, IDebugSystemObjects2::GetProcessIdsByIndex, IDebugSystemObjects3, IDebugSystemObjects3 interface [Windows Debugging], GetProcessIdsByIndex method, IDebugSystemObjects3::GetProcessIdsByIndex, IDebugSystemObjects4, IDebugSystemObjects4 interface [Windows Debugging], GetProcessIdsByIndex method, IDebugSystemObjects4::GetProcessIdsByIndex, IDebugSystemObjects::GetProcessIdsByIndex, IDebugSystemObjects_45309dcc-89bd-44a1-bafa-baabd10d54b0.xml, O, P, S, b, c, d, dbgeng/IDebugSystemObjects2::GetProcessIdsByIndex, dbgeng/IDebugSystemObjects3::GetProcessIdsByIndex, dbgeng/IDebugSystemObjects4::GetProcessIdsByIndex, dbgeng/IDebugSystemObjects::GetProcessIdsByIndex, debugger.getprocessidsbyindex, e, g, j, m, n, o, r, s, t, u, x, y"
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
-	IDebugSystemObjects.GetProcessIdsByIndex
-	IDebugSystemObjects2.GetProcessIdsByIndex
-	IDebugSystemObjects3.GetProcessIdsByIndex
-	IDebugSystemObjects4.GetProcessIdsByIndex
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSystemObjects4::GetProcessIdsByIndex method


## -description


The <b>GetProcessIdsByIndex</b> method returns the engine process ID and system process ID for the specified <a href="https://msdn.microsoft.com/6182ca34-ee5e-47e9-82fe-29266397e3a8">processes</a> in the current target.


## -syntax


````
HRESULT GetProcessIdsByIndex(
  [in]            ULONG  Start,
  [in]            ULONG  Count,
  [out, optional] PULONG Ids,
  [out, optional] PULONG SysIds
);
````


## -parameters




### -param Start [in]

Specifies the index of the first process whose ID is requested.


### -param Count [in]

Specifies the number of processes whose IDs are requested.


### -param Ids [out, optional]

Receives the engine process IDs.  If <i>Ids</i> is <b>NULL</b>, this information is not returned; otherwise, <i>Ids</i> is treated as an array of <i>Count</i> ULONG values.


### -param SysIds [out, optional]

Receives the system process IDs.  If <i>SysIds</i> is <b>NULL</b>, this information is not returned; otherwise, <i>SysIds</i> is treated as an array of <i>Count</i> ULONG values.


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



The index of the first process is zero.  The index of the last process is the number of processes returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff547946">GetNumberProcesses</a> minus one.

For more information about processes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.



