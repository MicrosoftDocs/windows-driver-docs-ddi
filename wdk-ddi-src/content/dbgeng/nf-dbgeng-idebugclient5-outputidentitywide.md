---
UID: NF:dbgeng.IDebugClient5.OutputIdentityWide
title: IDebugClient5::OutputIdentityWide method
author: windows-driver-content
description: The OutputIdentityWide method formats and outputs a string describing the computer and user this client represents.
old-location: debugger\outputidentitywide.htm
old-project: debugger
ms.assetid: e8f91713-ea1d-4262-bc0b-dd4e39d1c2c3
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: IDebugClient5, IDebugClient5 interface [Windows Debugging], OutputIdentityWide method, IDebugClient5::OutputIdentityWide, OutputIdentityWide method [Windows Debugging], OutputIdentityWide method [Windows Debugging], IDebugClient5 interface, OutputIdentityWide,IDebugClient5.OutputIdentityWide, dbgeng/IDebugClient5::OutputIdentityWide, debugger.outputidentitywide
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
-	IDebugClient5.OutputIdentityWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient5::OutputIdentityWide method


## -description


The <b>OutputIdentityWide</b> method formats and outputs a string describing the computer and user this client represents.


## -parameters




### -param OutputControl [in]

Specifies where to send the output.  For possible values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541517">DEBUG_OUTCTL_XXX</a>.


### -param Flags [in]

Set to zero.


### -param Format [in]

Specifies a format string similar to the <b>printf</b> format string.  However, this format string must only contain one formatting directive, <b>%s</b>, which will be replaced by a description of the computer and user this client represents.


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



The specific content of the string varies with the operating system.  If the client is remotely connected, some network information may also be present.

For more information about client objects, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539140">Client Objects</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546831">GetIdentity</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550497">IDebugClient5</a>
 

 

