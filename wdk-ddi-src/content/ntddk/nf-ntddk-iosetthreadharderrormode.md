---
UID: NF:ntddk.IoSetThreadHardErrorMode
title: IoSetThreadHardErrorMode function (ntddk.h)
description: The IoSetThreadHardErrorMode routine enables or disables hard error reporting for the current thread.
old-location: kernel\iosetthreadharderrormode.htm
tech.root: kernel
ms.assetid: bedb6399-8f79-477a-9a90-4a7dec5c5dae
ms.date: 04/30/2018
ms.keywords: IoSetThreadHardErrorMode, IoSetThreadHardErrorMode routine [Kernel-Mode Driver Architecture], k104_6e0a2c29-8edf-4d7e-b672-11309231c45e.xml, kernel.iosetthreadharderrormode, ntddk/IoSetThreadHardErrorMode
ms.topic: function
f1_keywords:
 - "ntddk/IoSetThreadHardErrorMode"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows 2000 and later versions of Windows.
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoSetThreadHardErrorMode
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoSetThreadHardErrorMode function


## -description


The <b>IoSetThreadHardErrorMode</b> routine enables or disables hard error reporting for the current thread.


## -parameters




### -param EnableHardErrors [in]

Specifies whether hard error reporting to the user should be enabled or disabled for this thread. A value of <b>TRUE</b> enables hard error reporting. <b>FALSE</b> disables it. 


## -returns



<b>IoSetThreadHardErrorMode</b> returns <b>TRUE</b> if hard errors were enabled from this thread before this routine completed execution. Otherwise, this routine returns <b>FALSE</b>. 




## -remarks



If hard errors are disabled for a given thread, calls to <b>IoRaiseHardError</b> will not display a message to the user indicating that a serious error has occurred. In addition, the IRP that is passed to <b>IoRaiseHardError </b>is completed without any data being copied into user buffers. Calling <b>IoRaiseInformationalHardError</b> after disabling hard errors causes that routine to always return <b>FALSE</b> for this thread.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ioraiseharderror">IoRaiseHardError</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ioraiseinformationalharderror">IoRaiseInformationalHardError</a>
 

 

