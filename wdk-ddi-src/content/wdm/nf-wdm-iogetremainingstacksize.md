---
UID: NF:wdm.IoGetRemainingStackSize
title: IoGetRemainingStackSize function (wdm.h)
description: The IoGetRemainingStackSize routine returns the current amount of available kernel-mode stack space.
old-location: kernel\iogetremainingstacksize.htm
tech.root: kernel
ms.assetid: 5e257b72-fe16-49a0-9232-9c791a88e903
ms.date: 04/30/2018
ms.keywords: IoGetRemainingStackSize, IoGetRemainingStackSize routine [Kernel-Mode Driver Architecture], k104_bc84d6dd-0874-440d-8f73-b403d18aa660.xml, kernel.iogetremainingstacksize, wdm/IoGetRemainingStackSize
ms.topic: function
f1_keywords:
 - "wdm/IoGetRemainingStackSize"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: See Remarks section.
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdm.h
api_name:
- IoGetRemainingStackSize
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoGetRemainingStackSize function


## -description


The <b>IoGetRemainingStackSize</b> routine returns the current amount of available kernel-mode stack space.


## -parameters






## -returns



<b>IoGetRemainingStackSize</b> returns the number of bytes of stack space in the current thread context.




## -remarks



Highest-level drivers, such as file systems, can call this routine, particularly drivers that use recursive code paths. Such a driver would call <b>IoGetRemainingStackSize</b> before launching a recursion to determine whether it should continue processing on an alternate code path.

For Windows Server 2003 Service Pack 1 (SP1) and later versions of Windows, callers of <b>IoGetRemainingStackSize</b> can be running at any IRQL. For earlier versions of Windows, the caller must be running at IRQL <= APC_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iogetinitialstack">IoGetInitialStack</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iogetstacklimits">IoGetStackLimits</a>
 

 

