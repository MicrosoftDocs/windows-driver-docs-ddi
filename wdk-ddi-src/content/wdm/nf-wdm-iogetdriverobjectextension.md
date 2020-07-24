---
UID: NF:wdm.IoGetDriverObjectExtension
title: IoGetDriverObjectExtension function (wdm.h)
description: The IoGetDriverObjectExtension routine retrieves a previously allocated per-driver context area.
old-location: kernel\iogetdriverobjectextension.htm
tech.root: kernel
ms.assetid: ce983953-53fc-4a32-8072-8a9f74d11ae3
ms.date: 04/30/2018
keywords: ["IoGetDriverObjectExtension function"]
ms.keywords: IoGetDriverObjectExtension, IoGetDriverObjectExtension routine [Kernel-Mode Driver Architecture], k104_37d4bd5d-6090-49b8-ab45-c898871f22e8.xml, kernel.iogetdriverobjectextension, wdm/IoGetDriverObjectExtension
f1_keywords:
 - "wdm/IoGetDriverObjectExtension"
 - "IoGetDriverObjectExtension"
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoGetDriverObjectExtension
targetos: Windows
req.typenames: 
---

# IoGetDriverObjectExtension function


## -description


The <b>IoGetDriverObjectExtension</b> routine retrieves a previously allocated per-driver context area.


## -parameters




### -param DriverObject [in]

Specifies the driver object with which the context area is associated.


### -param ClientIdentificationAddress [in]

Specifies the unique identifier, provided when it was allocated, of the context area to be retrieved.


## -returns



<b>IoGetDriverObjectExtension</b> returns a pointer to the context area, if any or returns <b>NULL</b>.




## -remarks



Drivers call <b>IoGetDriverObjectExtension</b> to retrieve a pointer to a previously allocated extension area. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocatedriverobjectextension">IoAllocateDriverObjectExtension</a>
 

 

