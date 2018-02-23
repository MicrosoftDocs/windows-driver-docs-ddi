---
UID: NF:wdbgexts.GetCurrentThreadAddr
title: GetCurrentThreadAddr function
author: windows-driver-content
description: The GetCurrentThreadAddr function returns the location of the system data that describes the current thread.
old-location: debugger\getcurrentthreadaddr.htm
old-project: Debugger
ms.assetid: 0664199b-da65-4b07-958e-d7972b39cefd
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: GetCurrentThreadAddr function [Windows Debugging], WdbgExts_Ref_03db8f68-2e64-4530-bf35-df2a6f0d7736.xml, wdbgexts/GetCurrentThreadAddr, debugger.getcurrentthreadaddr, GetCurrentThreadAddr
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdbgexts.h
apiname:
-	GetCurrentThreadAddr
product: Windows
targetos: Windows
req.typenames: EXT_TDOP
req.product: Windows 10 or later.
---

# GetCurrentThreadAddr function


## -description


The <b>GetCurrentThreadAddr</b> function returns the location of the system data that describes the current thread.


## -syntax


````
__inline VOID GetCurrentThreadAddr(
   DWORD    Processor,
   PULONG64 Address
);
````


## -parameters




### -param Processor

Specifies the index of the thread whose system data will be returned.

In kernel-mode debugging, this is the index of a virtual thread, which is the index of a processor on the target computer.


### -param Address

Receives the location of the system data for the thread.


## -returns



None




## -remarks



In user-mode debugging, <b>GetCurrentThreadAddr</b> returns the location of the thread's Thread Environment Block (TEB).  This is the same location that <a href="..\wdbgexts\nf-wdbgexts-gettebaddress.md">GetTebAddress</a> returns.

In kernel-mode debugging, <b>GetCurrentThreadAddr</b> returns the location of the KTHREAD structure of the operating system thread that was executing on the processor when the last event occurred.

For details on the KTHREAD and TEB structures, see <i>Microsoft Windows Internals</i> by David Solomon and Mark Russinovich.




## -see-also

<a href="..\wdbgexts\nf-wdbgexts-gettebaddress.md">GetTebAddress</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20GetCurrentThreadAddr function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

