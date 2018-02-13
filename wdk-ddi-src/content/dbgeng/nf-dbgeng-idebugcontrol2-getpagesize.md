---
UID: NF:dbgeng.IDebugControl2.GetPageSize
title: IDebugControl2::GetPageSize method
author: windows-driver-content
description: The GetPageSize method returns the page size for the effective processor mode.
old-location: debugger\getpagesize.htm
old-project: debugger
ms.assetid: 26f11dfb-3fc3-4804-a294-2dfc674b4a73
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugControl2, debugger.getpagesize, IDebugControl3 interface [Windows Debugging], GetPageSize method, dbgeng/IDebugControl2::GetPageSize, IDebugControl_b38e4c0a-5992-4afe-b684-2eb65b3a0271.xml, GetPageSize method [Windows Debugging], dbgeng/IDebugControl3::GetPageSize, IDebugControl::GetPageSize, dbgeng/IDebugControl::GetPageSize, IDebugControl2 interface [Windows Debugging], GetPageSize method, IDebugControl, IDebugControl3::GetPageSize, GetPageSize method [Windows Debugging], IDebugControl2 interface, IDebugControl2::GetPageSize, GetPageSize method [Windows Debugging], IDebugControl interface, GetPageSize method [Windows Debugging], IDebugControl3 interface, IDebugControl interface [Windows Debugging], GetPageSize method, GetPageSize
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
-	IDebugControl.GetPageSize
-	IDebugControl2.GetPageSize
-	IDebugControl3.GetPageSize
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugControl2::GetPageSize method


## -description


The <b>GetPageSize</b> method returns the page size for the effective processor mode.


## -syntax


````
HRESULT GetPageSize(
  [out] PULONG Size
);
````


## -parameters




### -param Size [out]

Receives the page size.


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
 



