---
UID: NF:dbgeng.IDebugSystemObjects3.GetSystemIdsByIndex
title: IDebugSystemObjects3::GetSystemIdsByIndex method
author: windows-driver-content
description: The GetSystemIdsByIndex method returns the engine target IDs for the specified targets.
old-location: debugger\getsystemidsbyindex.htm
old-project: debugger
ms.assetid: 7b2dcb75-f674-4a66-a483-8c3f644390c1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetSystemIdsByIndex method [Windows Debugging], GetSystemIdsByIndex method [Windows Debugging], IDebugSystemObjects3 interface, GetSystemIdsByIndex method [Windows Debugging], IDebugSystemObjects4 interface, GetSystemIdsByIndex,IDebugSystemObjects3.GetSystemIdsByIndex, IDebugSystemObjects3, IDebugSystemObjects3 interface [Windows Debugging], GetSystemIdsByIndex method, IDebugSystemObjects3::GetSystemIdsByIndex, IDebugSystemObjects4 interface [Windows Debugging], GetSystemIdsByIndex method, IDebugSystemObjects4::GetSystemIdsByIndex, IDebugSystemObjects_d1d7e689-407b-4d84-b1ce-75736b761089.xml, dbgeng/IDebugSystemObjects3::GetSystemIdsByIndex, dbgeng/IDebugSystemObjects4::GetSystemIdsByIndex, debugger.getsystemidsbyindex
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugSystemObjects3.GetSystemIdsByIndex
-	IDebugSystemObjects4.GetSystemIdsByIndex
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSystemObjects3::GetSystemIdsByIndex method


## -description


The <b>GetSystemIdsByIndex</b> method returns the engine target IDs for the specified targets.


## -syntax


````
HRESULT GetSystemIdsByIndex(
  [in]  ULONG  Start,
  [in]  ULONG  Count,
  [out] PULONG Ids
);
````


## -parameters




### -param Start [in]

Specifies the index of the first target whose target ID is requested.


### -param Count [in]

Specifies the number of processes whose IDs are requested.


### -param Ids [out]

Receives the engine target IDs.  If <i>Ids</i> is <b>NULL</b>, this information is not returned; otherwise, <i>Ids</i> is treated as an array of <i>Count</i> ULONG values.


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



The index of the first target is zero.  The index of the last target is the number of targets returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff547978">GetNumberSystems</a> minus one.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541386">Debugging Session and Execution Model</a>



<a href="..\dbgeng\nn-dbgeng-idebugsystemobjects4.md">IDebugSystemObjects4</a>



<a href="..\dbgeng\nn-dbgeng-idebugsystemobjects3.md">IDebugSystemObjects3</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSystemObjects3::GetSystemIdsByIndex method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

