---
UID: NF:wdm.IoConnectInterruptEx
title: IoConnectInterruptEx function
author: windows-driver-content
description: For more information, see the WdmlibIoConnectInterruptEx function.#define IoConnectInterruptEx WdmlibIoConnectInterruptEx
old-location: kernel\ioconnectinterruptex.htm
old-project: kernel
ms.assetid: f77a2701-bde2-42c2-8393-88a7e4576f1b
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: wdm/IoConnectInterruptEx, k104_17833453-ee13-4346-9c58-a1c47dccf636.xml, IoConnectInterruptEx routine [Kernel-Mode Driver Architecture], IoConnectInterruptEx, kernel.ioconnectinterruptex, WdmlibIoConnectInterruptEx, wdm/WdmlibIoConnectInterruptEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available on Windows Vista and later versions of the Windows operating system. Drivers that must also work on Windows 2000, Windows XP, or Windows Server 2003 can instead link to Iointex.lib to use the routine.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoConnectInterruptEx
-	WdmlibIoConnectInterruptEx
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoConnectInterruptEx function


## -description


For more information, see the <a href="..\iointex\nf-iointex-wdmlibioconnectinterruptex.md">WdmlibIoConnectInterruptEx</a> function.

<code>#define IoConnectInterruptEx WdmlibIoConnectInterruptEx</code>


## -syntax


````
NTSTATUS IoConnectInterruptEx(
  _Inout_ PIO_CONNECT_INTERRUPT_PARAMETERS Parameters
);
````


## -parameters




### -param Parameters [in, out]

For more information, see the <a href="..\iointex\nf-iointex-wdmlibioconnectinterruptex.md">WdmlibIoConnectInterruptEx</a> function.


## -returns



For more information, see the <a href="..\iointex\nf-iointex-wdmlibioconnectinterruptex.md">WdmlibIoConnectInterruptEx</a> function.




## -see-also

<a href="..\iointex\nf-iointex-wdmlibioconnectinterruptex.md">WdmlibIoConnectInterruptEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoConnectInterruptEx routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

