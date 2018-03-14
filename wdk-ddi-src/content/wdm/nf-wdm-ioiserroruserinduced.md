---
UID: NF:wdm.IoIsErrorUserInduced
title: IoIsErrorUserInduced macro
author: windows-driver-content
description: The IoIsErrorUserInduced routine determines whether an I/O error encountered while processing a request to a removable-media device was caused by the user.
old-location: kernel\ioiserroruserinduced.htm
old-project: kernel
ms.assetid: 6f5e54e8-c127-44d9-b1a6-e6f7ac3b3b51
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: IoIsErrorUserInduced, IoIsErrorUserInduced routine [Kernel-Mode Driver Architecture], k104_860a6f10-e6c0-44cd-9386-c09e356f3472.xml, kernel.ioiserroruserinduced, wdm/IoIsErrorUserInduced
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	IoIsErrorUserInduced
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoIsErrorUserInduced macro


## -description


The <b>IoIsErrorUserInduced</b> routine determines whether an I/O error encountered while processing a request to a removable-media device was caused by the user.


## -syntax


````
BOOLEAN IoIsErrorUserInduced(
  _In_ NTSTATUS Status
);
````


## -parameters




### -param Status [in]

Specifies the current NTSTATUS value, usually within the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff544079">DpcForIsr</a> routine.


## -remarks



This routine indicates whether an I/O request failed for one of the following user-correctable conditions:  

STATUS_DEVICE_NOT_READY

STATUS_IO_TIMEOUT

STATUS_MEDIA_WRITE_PROTECTED

STATUS_NO_MEDIA_IN_DEVICE

STATUS_UNRECOGNIZED_MEDIA

STATUS_VERIFY_REQUIRED

STATUS_WRONG_VOLUME

If <b>IoIsErrorUserInduced</b> returns <b>TRUE</b>, the removable-media driver must call <a href="..\ntddk\nf-ntddk-iosetharderrororverifydevice.md">IoSetHardErrorOrVerifyDevice</a> before completing the IRP. 




## -see-also

<a href="..\wdm\nf-wdm-iowriteerrorlogentry.md">IoWriteErrorLogEntry</a>



<a href="..\ntddk\nf-ntddk-iosetharderrororverifydevice.md">IoSetHardErrorOrVerifyDevice</a>



<a href="..\wdm\nf-wdm-ioallocateerrorlogentry.md">IoAllocateErrorLogEntry</a>



 

 


