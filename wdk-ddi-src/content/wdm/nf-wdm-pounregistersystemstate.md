---
UID: NF:wdm.PoUnregisterSystemState
title: PoUnregisterSystemState function (wdm.h)
description: The PoUnregisterSystemState routine cancels a system state registration created by PoRegisterSystemState.
old-location: kernel\pounregistersystemstate.htm
tech.root: kernel
ms.assetid: 5d82342e-c800-44ac-8618-468355d14dd0
ms.date: 04/30/2018
ms.keywords: PoUnregisterSystemState, PoUnregisterSystemState routine [Kernel-Mode Driver Architecture], kernel.pounregistersystemstate, portn_b6118bd0-5fe1-4e75-8c17-e81d1f26814c.xml, wdm/PoUnregisterSystemState
ms.topic: function
f1_keywords:
 - "wdm/PoUnregisterSystemState"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <=APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- PoUnregisterSystemState
product:
- Windows
targetos: Windows
req.typenames: 
---

# PoUnregisterSystemState function


## -description


The <b>PoUnregisterSystemState</b> routine cancels a system state registration created by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-poregistersystemstate">PoRegisterSystemState</a>.


## -parameters




### -param StateHandle [in, out]

A pointer to a handle previously returned by <b>PoRegisterSystemState</b>.


## -remarks



This routine cancels a system busy state registration established by <b>PoRegisterSystemState</b> and frees the associated <i>StateHandle</i>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-poregistersystemstate">PoRegisterSystemState</a>
 

 

