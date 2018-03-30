---
UID: NF:wdbgexts.GetCurrentProcessAddr
title: GetCurrentProcessAddr function
author: windows-driver-content
description: The GetCurrentProcessAddr function returns the location of the system data that describes the current process.
old-location: debugger\getcurrentprocessaddr.htm
old-project: debugger
ms.assetid: 31fada1c-53eb-4e55-bf5f-bf852a8df3ad
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetCurrentProcessAddr, GetCurrentProcessAddr function [Windows Debugging], WdbgExts_Ref_cf956b74-b0e4-43fa-911f-289b01dbf8c8.xml, debugger.getcurrentprocessaddr, wdbgexts/GetCurrentProcessAddr
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
-	GetCurrentProcessAddr
product: Windows
targetos: Windows
req.typenames: EXT_TDOP
req.product: Windows 10 or later.
---

# GetCurrentProcessAddr function


## -description


The <b>GetCurrentProcessAddr</b> function returns the location of the system data that describes the current process.


## -parameters




### -param Processor

Specifies the index of the processor or virtual thread that was running the current thread when the last event occurred.  <i>Processor</i> is only used in kernel-mode debugging; and, only if <i>CurrentThread</i> is <b>NULL</b>.


### -param CurrentThread

Specifies the location of the system data for the current thread.  This is the location returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff545889">GetCurrentThreadAddr</a>.

In kernel-mode debugging, <i>CurrentThread</i> can be <b>NULL</b>, in which case <i>Processor</i> is used instead.


### -param Address

Receives the location of the system data that describes the current process.


## -returns



None




## -remarks



In user-mode debugging, <b>GetCurrentProcessAddr</b> returns the location of the process's Process Environment Block (PEB).  This is the same location that <a href="https://msdn.microsoft.com/library/windows/hardware/ff548122">GetPebAddress</a> returns.

In kernel-mode debugging, <b>GetCurrentProcessAddr</b> returns the location of the KPROCESS structure of the current process.

For details on the KPROCESS and PEB structures, see <i>Microsoft Windows Internals</i> by David Solomon and Mark Russinovich.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545889">GetCurrentThreadAddr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548122">GetPebAddress</a>
 

 

