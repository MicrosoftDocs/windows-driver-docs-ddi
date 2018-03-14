---
UID: NF:dbgeng.IDebugDataSpaces3.EndEnumTagged
title: IDebugDataSpaces3::EndEnumTagged method
author: windows-driver-content
description: The EndEnumTagged method releases the resources used by the specified enumeration.
old-location: debugger\endenumtagged.htm
old-project: debugger
ms.assetid: 6a456b8c-aec6-443d-8db4-21e7715ab818
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: EndEnumTagged method [Windows Debugging], EndEnumTagged method [Windows Debugging], IDebugDataSpaces3 interface, EndEnumTagged method [Windows Debugging], IDebugDataSpaces4 interface, EndEnumTagged,IDebugDataSpaces3.EndEnumTagged, IDebugDataSpaces3, IDebugDataSpaces3 interface [Windows Debugging], EndEnumTagged method, IDebugDataSpaces3::EndEnumTagged, IDebugDataSpaces4 interface [Windows Debugging], EndEnumTagged method, IDebugDataSpaces4::EndEnumTagged, IDebugDataSpaces_a6366d17-1a38-43ca-af52-3c7e2b73be9e.xml, dbgeng/IDebugDataSpaces3::EndEnumTagged, dbgeng/IDebugDataSpaces4::EndEnumTagged, debugger.endenumtagged
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
-	IDebugDataSpaces3.EndEnumTagged
-	IDebugDataSpaces4.EndEnumTagged
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugDataSpaces3::EndEnumTagged method


## -description


The <b>EndEnumTagged</b> method releases the resources used by the specified enumeration.


## -syntax


````
HRESULT EndEnumTagged(
  [in] ULONG64 Handle
);
````


## -parameters




### -param Handle [in]

Specifies the handle identifying the enumeration.  This is the handle returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff558801">StartEnumTagged</a>.


## -returns



This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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



After a handle has been passed to this method it is no longer valid and must not be used again.



