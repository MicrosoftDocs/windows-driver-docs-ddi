---
UID: NF:dbgeng.IDebugDataSpaces3.StartEnumTagged
title: IDebugDataSpaces3::StartEnumTagged method
author: windows-driver-content
description: The StartEnumTagged method initializes a enumeration over the tagged data associated with a debugger session.
old-location: debugger\startenumtagged.htm
old-project: debugger
ms.assetid: b79b1f09-baff-4071-a209-6fc399c9aef9
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugDataSpaces3, IDebugDataSpaces3 interface [Windows Debugging], StartEnumTagged method, IDebugDataSpaces3::StartEnumTagged, IDebugDataSpaces4 interface [Windows Debugging], StartEnumTagged method, IDebugDataSpaces4::StartEnumTagged, IDebugDataSpaces_bc6f5148-04e1-4912-8ca2-8c095519af8f.xml, StartEnumTagged method [Windows Debugging], StartEnumTagged method [Windows Debugging], IDebugDataSpaces3 interface, StartEnumTagged method [Windows Debugging], IDebugDataSpaces4 interface, StartEnumTagged,IDebugDataSpaces3.StartEnumTagged, dbgeng/IDebugDataSpaces3::StartEnumTagged, dbgeng/IDebugDataSpaces4::StartEnumTagged, debugger.startenumtagged
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
-	IDebugDataSpaces3.StartEnumTagged
-	IDebugDataSpaces4.StartEnumTagged
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugDataSpaces3::StartEnumTagged method


## -description


The <b>StartEnumTagged</b> method initializes a enumeration over the tagged data associated with a debugger session.


## -parameters




### -param Handle [out]

Receives the handle identifying the enumeration.  This handle can be passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547874">GetNextTagged</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff542978">EndEnumTagged</a>.


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



The resources held by an enumeration created with this method can be released using <a href="https://msdn.microsoft.com/library/windows/hardware/ff542978">EndEnumTagged</a>.



