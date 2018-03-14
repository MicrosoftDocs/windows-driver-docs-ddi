---
UID: NF:wdm.MmUnmapIoSpace
title: MmUnmapIoSpace function
author: windows-driver-content
description: The MmUnmapIoSpace routine unmaps a specified range of physical addresses previously mapped by MmMapIoSpace.
old-location: kernel\mmunmapiospace.htm
old-project: kernel
ms.assetid: 5963f34a-4315-46c3-9802-0b6a1b229e3f
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: MmUnmapIoSpace, MmUnmapIoSpace routine [Kernel-Mode Driver Architecture], k106_a56f91b1-7187-4836-a3d8-4b7d2918227a.xml, kernel.mmunmapiospace, wdm/MmUnmapIoSpace
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	MmUnmapIoSpace
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# MmUnmapIoSpace function


## -description


The <b>MmUnmapIoSpace</b> routine unmaps a specified range of physical addresses previously mapped by <b>MmMapIoSpace</b>.


## -syntax


````
VOID MmUnmapIoSpace(
  _In_ PVOID  BaseAddress,
  _In_ SIZE_T NumberOfBytes
);
````


## -parameters




### -param BaseAddress [in]

Pointer to the base virtual address to which the physical pages were mapped.


### -param NumberOfBytes [in]

Specifies the number of bytes that were mapped. 


## -returns



None




## -remarks



If a driver calls <b>MmMapIoSpace</b> during device start-up, it must call <b>MmUnmapIoSpace</b> when it receives a PnP stop-device or remove-device IRP for the same device object. 




## -see-also

<a href="..\wdm\nf-wdm-mmmapiospace.md">MmMapIoSpace</a>



 

 


