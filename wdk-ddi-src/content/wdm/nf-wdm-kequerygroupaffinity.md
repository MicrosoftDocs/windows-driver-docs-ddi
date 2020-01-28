---
UID: NF:wdm.KeQueryGroupAffinity
title: KeQueryGroupAffinity function (wdm.h)
description: The KeQueryGroupAffinity routine returns an affinity mask that identifies the active logical processors in a specified group in a multiprocessor system.
old-location: kernel\kequerygroupaffinity.htm
tech.root: kernel
ms.assetid: 235ec93e-5b3c-4a19-876f-f668271a56a5
ms.date: 04/30/2018
ms.keywords: KeQueryGroupAffinity, KeQueryGroupAffinity routine [Kernel-Mode Driver Architecture], k105_9116eade-e2ed-47f4-a204-c21d456371b0.xml, kernel.kequerygroupaffinity, wdm/KeQueryGroupAffinity
f1_keywords:
 - "wdm/KeQueryGroupAffinity"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeQueryGroupAffinity
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeQueryGroupAffinity function


## -description


The <b>KeQueryGroupAffinity</b> routine returns an affinity mask that identifies the active logical processors in a specified group in a multiprocessor system.


## -parameters




### -param GroupNumber [in]

The group number. If a multiprocessor system contains <i>n</i> groups, the groups are numbered from 0 to <i>n</i>-1. To obtain the number of active groups in the system, call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kequeryactivegroupcount">KeQueryActiveGroupCount</a> routine. 


## -returns



<b>KeQueryGroupAffinity</b> returns a [**KAFFINITY**](https://docs.microsoft.com/windows-hardware/drivers/kernel/interrupt-affinity-and-priority#about-kaffinity) value that identifies the active logical processors in the specified group. If the <i>GroupNumber</i> parameter value is not a valid group number, the routine returns zero. 




## -remarks



A related routine, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kequeryactiveprocessors">KeQueryActiveProcessors</a>, returns an affinity mask that represents a set of active processors, but this routine, unlike <b>KeQueryGroupAffinity</b>, does not accept a group number as an input parameter. In Windows 7 and later versions of the Windows operating system, <b>KeQueryActiveProcessors</b> returns an affinity mask for the active processors in group 0, which is compatible with the behavior of this routine in earlier versions of Windows that do not support groups. This behavior ensures that existing drivers that call <b>KeQueryActiveProcessors</b> and that use no group-oriented features will run correctly in multiprocessor systems that have two or more groups. However, drivers that use any group-oriented features in Windows 7 and later versions of the Windows operating system should call <b>KeQueryGroupAffinity</b> instead of <b>KeQueryActiveProcessors</b>. 




## -see-also




[**KAFFINITY**](https://docs.microsoft.com/windows-hardware/drivers/kernel/interrupt-affinity-and-priority#about-kaffinity)



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kequeryactiveprocessors">KeQueryActiveProcessors</a>
 

 

