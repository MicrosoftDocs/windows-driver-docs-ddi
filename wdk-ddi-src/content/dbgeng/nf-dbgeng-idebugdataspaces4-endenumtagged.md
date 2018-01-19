---
UID: NF:dbgeng.IDebugDataSpaces4.EndEnumTagged
title: IDebugDataSpaces4::EndEnumTagged method
author: windows-driver-content
description: The EndEnumTagged method releases the resources used by the specified enumeration.
old-location: debugger\endenumtagged.htm
old-project: debugger
ms.assetid: 6a456b8c-aec6-443d-8db4-21e7715ab818
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugDataSpaces4, IDebugDataSpaces4::EndEnumTagged, EndEnumTagged
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
req.alt-api: IDebugDataSpaces3.EndEnumTagged,IDebugDataSpaces4.EndEnumTagged
req.alt-loc: dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugDataSpaces4::EndEnumTagged method



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
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
After a handle has been passed to this method it is no longer valid and must not be used again.</p>