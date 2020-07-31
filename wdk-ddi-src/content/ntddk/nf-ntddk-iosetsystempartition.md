---
UID: NF:ntddk.IoSetSystemPartition
title: IoSetSystemPartition function (ntddk.h)
description: The IoSetSystemPartition routine sets the boot partition for the system.
old-location: kernel\iosetsystempartition.htm
tech.root: kernel
ms.assetid: f1606881-da8b-4034-bbdf-53c75e594032
ms.date: 04/30/2018
keywords: ["IoSetSystemPartition function"]
ms.keywords: IoSetSystemPartition, IoSetSystemPartition routine [Kernel-Mode Driver Architecture], k104_b0beef8e-9d45-4125-a722-0a7189876308.xml, kernel.iosetsystempartition, ntddk/IoSetSystemPartition
f1_keywords:
 - "ntddk/IoSetSystemPartition"
 - "IoSetSystemPartition"
req.header: ntddk.h
req.include-header: Ntddk.h
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoSetSystemPartition
targetos: Windows
req.typenames: 
---

# IoSetSystemPartition function


## -description


The <b>IoSetSystemPartition</b> routine sets the boot partition for the system.


## -parameters




### -param VolumeNameString [in]

Pointer to a Unicode string that specifies the MS-DOS name of the system partition. 


## -returns



STATUS_SUCCESS if the boot partition can be set, or an error code on failure. 




## -remarks



The specified partition must contain the boot loader.



