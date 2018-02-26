---
UID: NF:ntddk.IoSetThreadHardErrorMode
title: IoSetThreadHardErrorMode function
author: windows-driver-content
description: The IoSetThreadHardErrorMode routine enables or disables hard error reporting for the current thread.
old-location: kernel\iosetthreadharderrormode.htm
old-project: kernel
ms.assetid: bedb6399-8f79-477a-9a90-4a7dec5c5dae
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , E, H, I, IoSetThreadHardErrorMode, IoSetThreadHardErrorMode routine [Kernel-Mode Driver Architecture], M, S, T, a, d, e, h, k104_6e0a2c29-8edf-4d7e-b672-11309231c45e.xml, kernel.iosetthreadharderrormode, ntddk/IoSetThreadHardErrorMode, o, r, t"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoSetThreadHardErrorMode
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# IoSetThreadHardErrorMode function


## -description


The <b>IoSetThreadHardErrorMode</b> routine enables or disables hard error reporting for the current thread.


## -syntax


````
BOOLEAN IoSetThreadHardErrorMode(
  _In_ BOOLEAN EnableHardErrors
);
````


## -parameters




### -param EnableHardErrors [in]

Specifies whether hard error reporting to the user should be enabled or disabled for this thread. A value of <b>TRUE</b> enables hard error reporting. <b>FALSE</b> disables it. 


## -returns



<b>IoSetThreadHardErrorMode</b> returns <b>TRUE</b> if hard errors were enabled from this thread before this routine completed execution. Otherwise, this routine returns <b>FALSE</b>. 




## -remarks



If hard errors are disabled for a given thread, calls to <b>IoRaiseHardError</b> will not display a message to the user indicating that a serious error has occurred. In addition, the IRP that is passed to <b>IoRaiseHardError </b>is completed without any data being copied into user buffers. Calling <b>IoRaiseInformationalHardError</b> after disabling hard errors causes that routine to always return <b>FALSE</b> for this thread.




## -see-also

<a href="..\ntddk\nf-ntddk-ioraiseinformationalharderror.md">IoRaiseInformationalHardError</a>



<a href="..\ntddk\nf-ntddk-ioraiseharderror.md">IoRaiseHardError</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoSetThreadHardErrorMode routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

