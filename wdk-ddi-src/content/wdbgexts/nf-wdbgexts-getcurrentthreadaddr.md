---
UID: NF:wdbgexts.GetCurrentThreadAddr
title: GetCurrentThreadAddr function
author: windows-driver-content
description: The GetCurrentThreadAddr function returns the location of the system data that describes the current thread.
old-location: debugger\getcurrentthreadaddr.htm
old-project: debugger
ms.assetid: 0664199b-da65-4b07-958e-d7972b39cefd
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetCurrentThreadAddr, GetCurrentThreadAddr function [Windows Debugging], WdbgExts_Ref_03db8f68-2e64-4530-bf35-df2a6f0d7736.xml, debugger.getcurrentthreadaddr, wdbgexts/GetCurrentThreadAddr
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdbgexts.h
api_name:
-	GetCurrentThreadAddr
product: Windows
targetos: Windows
req.typenames: EXT_TDOP
req.product: Windows 10 or later.
---

# GetCurrentThreadAddr function


## -description


The <b>GetCurrentThreadAddr</b> function returns the location of the system data that describes the current thread.


## -parameters




### -param Processor

Specifies the index of the thread whose system data will be returned.

In kernel-mode debugging, this is the index of a virtual thread, which is the index of a processor on the target computer.


### -param Address

Receives the location of the system data for the thread.


## -returns



None




## -remarks



In user-mode debugging, <b>GetCurrentThreadAddr</b> returns the location of the thread's Thread Environment Block (TEB).  This is the same location that <a href="https://msdn.microsoft.com/library/windows/hardware/ff549267">GetTebAddress</a> returns.

In kernel-mode debugging, <b>GetCurrentThreadAddr</b> returns the location of the KTHREAD structure of the operating system thread that was executing on the processor when the last event occurred.

For details on the KTHREAD and TEB structures, see <i>Microsoft Windows Internals</i> by David Solomon and Mark Russinovich.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549267">GetTebAddress</a>
 

 

