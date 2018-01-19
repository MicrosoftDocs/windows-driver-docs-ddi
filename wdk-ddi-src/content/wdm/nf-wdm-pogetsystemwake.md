---
UID: NF:wdm.PoGetSystemWake
title: PoGetSystemWake function
author: windows-driver-content
description: The PoGetSystemWake routine determines whether a specified IRP has been marked as waking the system from a sleeping state.
old-location: kernel\pogetsystemwake.htm
old-project: kernel
ms.assetid: f2e6bcd6-ed6b-4c88-af96-768284bddb24
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PoGetSystemWake
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
req.alt-api: PoGetSystemWake
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <=DISPATCH_LEVEL
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# PoGetSystemWake function



## -description
The <b>PoGetSystemWake</b> routine determines whether a specified IRP has been marked as waking the system from a sleeping state.



## -syntax

````
BOOLEAN PoGetSystemWake(
  _In_ PIRP Irp
);
````


## -parameters

### -param Irp [in]

A pointer to an IRP.


## -returns
<b>PoGetSystemWake</b> returns one of the following:
<dl>
<dt><b><b>TRUE</b></b></dt>
</dl>The specified IRP did cause the system to wake.
<dl>
<dt><b><b>FALSE</b></b></dt>
</dl>The specified IRP did not cause the system to wake.

 


## -remarks
A driver calls <b>PoGetSystemWake</b> to determine if a specified IRP contributed to waking the system from a sleep state.

A driver in a wait/wake chain should call <b>PoGetSystemWake</b> on its own wait/wake IRP at completion to determine if the driver should also call <a href="..\wdm\nf-wdm-posetsystemwake.md">PoSetSystemWake</a> for child wait/wake IRPs that the driver is about to complete. This ensures that system wake information properly propagates throughout the entire wait/wake chain.

It is possible that several IRPs are causing the system to wake. In this case, <b>PoGetSystemWake </b>would return <b>TRUE</b> for all of the IRPs contributing to the wake event.


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-posetsystemwake.md">PoSetSystemWake</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PoGetSystemWake routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

