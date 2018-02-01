---
UID: NF:wdm.IoDisconnectInterruptEx
title: IoDisconnectInterruptEx function
author: windows-driver-content
description: For more information, see the WdmlibIoDisconnectInterruptEx function.#define IoDisconnectInterruptEx WdmlibIoDisconnectInterruptEx
old-location: kernel\iodisconnectinterruptex.htm
old-project: kernel
ms.assetid: 6c538468-2f7c-48b0-90f8-deb975c85970
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/IoDisconnectInterruptEx, kernel.iodisconnectinterruptex, IoDisconnectInterruptEx routine [Kernel-Mode Driver Architecture], IoDisconnectInterruptEx, WdmlibIoDisconnectInterruptEx, k104_3bfae096-0af6-4f61-ae4b-4c83e748b071.xml, wdm/WdmlibIoDisconnectInterruptEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista. Drivers that must also work Microsoft Windows 2000, Windows XP, or Windows Server 2003 can instead link to Iointex.lib to use the routine.
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
req.lib: NtosKrnl.lib; Iointex.lib
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
-	IoDisconnectInterruptEx
-	WdmlibIoDisconnectInterruptEx
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoDisconnectInterruptEx function


## -description


For more information, see the <a href="..\iointex\nf-iointex-wdmlibiodisconnectinterruptex.md">WdmlibIoDisconnectInterruptEx</a> function.

<code>#define IoDisconnectInterruptEx WdmlibIoDisconnectInterruptEx</code>


## -syntax


````
VOID IoDisconnectInterruptEx(
  _Inout_ PIO_DISCONNECT_INTERRUPT_PARAMETERS Parameters
);
````


## -parameters




### -param Parameters [in, out]

For more information, see the <a href="..\iointex\nf-iointex-wdmlibiodisconnectinterruptex.md">WdmlibIoDisconnectInterruptEx</a> function.


## -returns


For more information, see the <a href="..\iointex\nf-iointex-wdmlibiodisconnectinterruptex.md">WdmlibIoDisconnectInterruptEx</a> function.



## -see-also

<a href="..\iointex\nf-iointex-wdmlibiodisconnectinterruptex.md">WdmlibIoDisconnectInterruptEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoDisconnectInterruptEx routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

