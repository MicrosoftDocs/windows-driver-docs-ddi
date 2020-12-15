---
UID: NF:wdm.PsGetVersion
title: PsGetVersion function (wdm.h)
description: This function is obsolete in Windows XP and later versions of the Windows operating system. Use RtlGetVersion instead.PsGetVersion returns caller-selected information about the current version of the NT-based operating system.
old-location: kernel\psgetversion.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PsGetVersion function"]
ms.keywords: PsGetVersion, PsGetVersion function [Kernel-Mode Driver Architecture], k108_3c73c1e7-3f02-4598-adae-43c378dcfb08.xml, kernel.psgetversion, wdm/PsGetVersion
req.header: wdm.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlPsPassive, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PsGetVersion
 - wdm/PsGetVersion
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - PsGetVersion
---

# PsGetVersion function


## -description

This function is <u>obsolete</u> in Windows XP and later versions of the Windows operating system. Use <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlgetversion">RtlGetVersion</a> instead.

## -parameters

### -param MajorVersion 

[out, optional]

### -param MinorVersion 

[out, optional]

### -param BuildNumber 

[out, optional]

### -param CSDVersion 

[out, optional]

## -returns

## -remarks
