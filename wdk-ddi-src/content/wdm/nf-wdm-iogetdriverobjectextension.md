---
UID: NF:wdm.IoGetDriverObjectExtension
title: IoGetDriverObjectExtension function
author: windows-driver-content
description: The IoGetDriverObjectExtension routine retrieves a previously allocated per-driver context area.
old-location: kernel\iogetdriverobjectextension.htm
old-project: kernel
ms.assetid: ce983953-53fc-4a32-8072-8a9f74d11ae3
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoGetDriverObjectExtension, wdm/IoGetDriverObjectExtension, kernel.iogetdriverobjectextension, IoGetDriverObjectExtension routine [Kernel-Mode Driver Architecture], k104_37d4bd5d-6090-49b8-ab45-c898871f22e8.xml
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoGetDriverObjectExtension
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoGetDriverObjectExtension function


## -description


The <b>IoGetDriverObjectExtension</b> routine retrieves a previously allocated per-driver context area.


## -syntax


````
PVOID IoGetDriverObjectExtension(
  _In_ PDRIVER_OBJECT DriverObject,
  _In_ PVOID          ClientIdentificationAddress
);
````


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

<a href="..\wdm\nf-wdm-ioallocatedriverobjectextension.md">IoAllocateDriverObjectExtension</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoGetDriverObjectExtension routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

