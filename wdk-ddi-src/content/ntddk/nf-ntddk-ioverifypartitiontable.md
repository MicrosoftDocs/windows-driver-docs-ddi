---
UID: NF:ntddk.IoVerifyPartitionTable
title: IoVerifyPartitionTable function
author: windows-driver-content
description: The IoVerifyPartitionTable routine checks the validity of the partition table for a disk.
old-location: kernel\ioverifypartitiontable.htm
old-project: kernel
ms.assetid: dc7b543b-1fb5-477c-a612-c8e7381e637e
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: k104_d550806b-f911-45f6-b6ab-efbf05683c4d.xml, IoVerifyPartitionTable routine [Kernel-Mode Driver Architecture], kernel.ioverifypartitiontable, IoVerifyPartitionTable, ntddk/IoVerifyPartitionTable
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows XP.
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoVerifyPartitionTable
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# IoVerifyPartitionTable function


## -description


The <b>IoVerifyPartitionTable</b> routine checks the validity of the partition table 
   for a disk.


## -syntax


````
NTSTATUS IoVerifyPartitionTable(
  _In_ PDEVICE_OBJECT DeviceObject,
  _In_ BOOLEAN        FixErrors
);
````


## -parameters




### -param DeviceObject [in]

Specifies the device object of the disk to verify.


### -param FixErrors [in]

Specifies if the routine should correct any correctable errors in the partition table.


## -returns


The routine returns STATUS_SUCCESS if the partition table is error-free.

If the caller specifies <b>FALSE</b> for the <i>FixErrors</i> parameter 
       and the partition table has errors, the routine returns STATUS_DISK_CORRUPT_ERROR. If the caller specifies 
       <b>TRUE</b> for <i>FixErrors</i>, and the routine is able to correct all 
       errors in the partition table, it returns STATUS_SUCCESS. Otherwise it returns STATUS_DISK_CORRUPT_ERROR.

The routine might also return other NT status error codes.



## -remarks


<b>IoVerifyPartitionTable</b> must be used only by disk drivers.


