---
UID: NF:wdm.PoGetSystemWake
title: PoGetSystemWake function
author: windows-driver-content
description: The PoGetSystemWake routine determines whether a specified IRP has been marked as waking the system from a sleeping state.
old-location: kernel\pogetsystemwake.htm
tech.root: kernel
ms.assetid: f2e6bcd6-ed6b-4c88-af96-768284bddb24
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: PoGetSystemWake, PoGetSystemWake routine [Kernel-Mode Driver Architecture], kernel.pogetsystemwake, portn_0762df5c-0956-4561-9984-83c680bdd764.xml, wdm/PoGetSystemWake
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	PoGetSystemWake
product:
- Windows
targetos: Windows
req.typenames: 
---

# PoGetSystemWake function


## -description


The <b>PoGetSystemWake</b> routine determines whether a specified IRP has been marked as waking the system from a sleeping state.


## -parameters




### -param Irp [in]

A pointer to an IRP.


## -returns



<b>PoGetSystemWake</b> returns one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b><b>TRUE</b></b></dt>
</dl>
</td>
<td width="60%">
The specified IRP did cause the system to wake.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b><b>FALSE</b></b></dt>
</dl>
</td>
<td width="60%">
The specified IRP did not cause the system to wake.

</td>
</tr>
</table>
 




## -remarks



A driver calls <b>PoGetSystemWake</b> to determine if a specified IRP contributed to waking the system from a sleep state.

A driver in a wait/wake chain should call <b>PoGetSystemWake</b> on its own wait/wake IRP at completion to determine if the driver should also call <a href="https://msdn.microsoft.com/library/windows/hardware/ff559770">PoSetSystemWake</a> for child wait/wake IRPs that the driver is about to complete. This ensures that system wake information properly propagates throughout the entire wait/wake chain.

It is possible that several IRPs are causing the system to wake. In this case, <b>PoGetSystemWake </b>would return <b>TRUE</b> for all of the IRPs contributing to the wake event.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559770">PoSetSystemWake</a>
 

 

