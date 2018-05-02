---
UID: NF:wdm.IoIs32bitProcess
title: IoIs32bitProcess function
author: windows-driver-content
description: The IoIs32bitProcess routine checks whether the originator of the current I/O request is a 32-bit user-mode application.
old-location: kernel\iois32bitprocess.htm
old-project: kernel
ms.assetid: a2de12d5-ed9e-42ac-b3e8-a3a567e4ab4a
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: IoIs32bitProcess, IoIs32bitProcess routine [Kernel-Mode Driver Architecture], k104_8380b2cb-114a-41bc-a32e-8fb60b18c133.xml, kernel.iois32bitprocess, wdm/IoIs32bitProcess
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in 64-bit versions of Microsoft Windows XP and later 64-bit versions of the Windows operating system.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoIs32bitProcess
product: Windows
targetos: Windows
req.typenames: 
---

# IoIs32bitProcess function


## -description


The <b>IoIs32bitProcess</b> routine checks whether the originator of the current I/O request is a 32-bit user-mode application.


## -parameters




### -param Irp [in, optional]

Optional pointer to the IRP containing the current I/O request. Note that this must be the original IRP that was issued by the I/O manager. If the caller is a fast I/O dispatch routine (and thus there is no IRP), the caller should set this parameter to <b>NULL</b>.


## -returns



<b>IoIs32bitProcess</b> returns <b>TRUE</b> if the originator of the current I/O request is a 32-bit user-mode process. Otherwise, it returns <b>FALSE</b>. 




## -remarks



Drivers call <b>IoIs32bitProcess</b> to determine whether an I/O request is likely to contain data elements that need to be converted, or "thunked," before they can be used in a 64-bit driver.

If the <i>Irp</i> parameter is <b>NULL</b>, and the caller is running in the context of a user-mode process, <b>IoIs32bitProcess</b> returns <b>TRUE</b> if this process is a 32-bit process.

If the <i>Irp</i> parameter is not <b>NULL</b>, it must point to an IRP that was issued by the I/O manager on behalf of a user-mode process. <b>IoIs32bitProcess</b> cannot be used to check driver-allocated IRPs. Driver-allocated IRPs, as well as kernel-mode drivers, are assumed to be 64-bit-ready.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff559923">Programming Issues for 64-Bit Drivers</a>.



