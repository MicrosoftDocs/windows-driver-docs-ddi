---
UID: NF:wdbgexts.GetCurrentProcessAddr
title: GetCurrentProcessAddr function (wdbgexts.h)
description: The GetCurrentProcessAddr function returns the location of the system data that describes the current process.
old-location: debugger\getcurrentprocessaddr.htm
tech.root: debugger
ms.assetid: 31fada1c-53eb-4e55-bf5f-bf852a8df3ad
ms.date: 05/03/2018
keywords: ["GetCurrentProcessAddr function"]
ms.keywords: GetCurrentProcessAddr, GetCurrentProcessAddr function [Windows Debugging], WdbgExts_Ref_cf956b74-b0e4-43fa-911f-289b01dbf8c8.xml, debugger.getcurrentprocessaddr, wdbgexts/GetCurrentProcessAddr
f1_keywords:
 - "wdbgexts/GetCurrentProcessAddr"
 - "GetCurrentProcessAddr"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdbgexts.h
api_name:
- GetCurrentProcessAddr
targetos: Windows
req.typenames: 
---

# GetCurrentProcessAddr function


## -description


The <b>GetCurrentProcessAddr</b> function returns the location of the system data that describes the current process.


## -parameters




### -param Processor

Specifies the index of the processor or virtual thread that was running the current thread when the last event occurred.  <i>Processor</i> is only used in kernel-mode debugging; and, only if <i>CurrentThread</i> is <b>NULL</b>.


### -param CurrentThread

Specifies the location of the system data for the current thread.  This is the location returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/nf-wdbgexts-getcurrentthreadaddr">GetCurrentThreadAddr</a>.

In kernel-mode debugging, <i>CurrentThread</i> can be <b>NULL</b>, in which case <i>Processor</i> is used instead.


### -param Address

Receives the location of the system data that describes the current process.


## -remarks



In user-mode debugging, <b>GetCurrentProcessAddr</b> returns the location of the process's Process Environment Block (PEB).  This is the same location that <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/nf-wdbgexts-getpebaddress">GetPebAddress</a> returns.

In kernel-mode debugging, <b>GetCurrentProcessAddr</b> returns the location of the KPROCESS structure of the current process.

For details on the KPROCESS and PEB structures, see <i>Microsoft Windows Internals</i> by David Solomon and Mark Russinovich.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/nf-wdbgexts-getcurrentthreadaddr">GetCurrentThreadAddr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/nf-wdbgexts-getpebaddress">GetPebAddress</a>
 

 

