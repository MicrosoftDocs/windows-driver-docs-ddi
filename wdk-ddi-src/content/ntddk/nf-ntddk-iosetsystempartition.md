---
UID: NF:ntddk.IoSetSystemPartition
title: IoSetSystemPartition function
author: windows-driver-content
description: The IoSetSystemPartition routine sets the boot partition for the system.
old-location: kernel\iosetsystempartition.htm
old-project: kernel
ms.assetid: f1606881-da8b-4034-bbdf-53c75e594032
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: k104_b0beef8e-9d45-4125-a722-0a7189876308.xml, IoSetSystemPartition, kernel.iosetsystempartition, ntddk/IoSetSystemPartition, IoSetSystemPartition routine [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoSetSystemPartition
product: Windows
targetos: Windows
req.typenames: "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---

# IoSetSystemPartition function


## -description


The <b>IoSetSystemPartition</b> routine sets the boot partition for the system.


## -syntax


````
NTSTATUS IoSetSystemPartition(
  _In_ PUNICODE_STRING VolumeNameString
);
````


## -parameters




### -param VolumeNameString [in]

Pointer to a Unicode string that specifies the MS-DOS name of the system partition. 


## -returns



STATUS_SUCCESS if the boot partition can be set, or an error code on failure. 




## -remarks



The specified partition must contain the boot loader.



