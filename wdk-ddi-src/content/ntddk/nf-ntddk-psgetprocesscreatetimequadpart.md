---
UID: NF:ntddk.PsGetProcessCreateTimeQuadPart
title: PsGetProcessCreateTimeQuadPart function (ntddk.h)
description: The PsGetProcessCreateTimeQuadPart routine returns a LONGLONG value that represents the time at which the process was created.
old-location: kernel\psgetprocesscreatetimequadpart.htm
tech.root: kernel
ms.assetid: d202b6d9-9964-4c95-acd3-f641e8f9d879
ms.date: 04/30/2018
ms.keywords: PsGetProcessCreateTimeQuadPart, PsGetProcessCreateTimeQuadPart routine [Kernel-Mode Driver Architecture], k108_57bcfbb5-501b-41bf-964c-14c2b90548ea.xml, kernel.psgetprocesscreatetimequadpart, ntddk/PsGetProcessCreateTimeQuadPart
ms.topic: function
f1_keywords:
 - "ntddk/PsGetProcessCreateTimeQuadPart"
req.header: ntddk.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
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
req.lib: Ntoskrnl.lib
req.dll: Ntoskrnl.exe
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Ntoskrnl.exe
api_name:
- PsGetProcessCreateTimeQuadPart
product:
- Windows
targetos: Windows
req.typenames: 
---

# PsGetProcessCreateTimeQuadPart function


## -description


The <b>PsGetProcessCreateTimeQuadPart</b> routine returns a LONGLONG value that represents the time at which the process was created. 


## -parameters




### -param Process [in]

A pointer to the EPROCESS structure that represents the process. Drivers can use the [PsGetCurrentProcess](https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer#psgetcurrentprocess) and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obreferenceobjectbyhandle">ObReferenceObjectByHandle</a> routines to obtain a pointer to the EPROCESS structure for a process. 


## -returns



<b>PsGetProcessCreateTimeQuadPart</b> returns the process creation time, in 100-nanosecond intervals, since January 1, 1601. The return value is the same as the value that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kequerysystemtime">KeQuerySystemTime</a> routine returns when the process was created. (Note that if the system time is changed, the value that <b>PsGetProcessCreateTimeQuadPart</b> returns is unaffected.) 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kequerysystemtime">KeQuerySystemTime</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obreferenceobjectbyhandle">ObReferenceObjectByHandle</a>



[PsGetCurrentProcess](https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer#psgetcurrentprocess)
 

 

