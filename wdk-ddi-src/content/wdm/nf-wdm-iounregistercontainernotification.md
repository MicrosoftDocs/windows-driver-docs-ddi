---
UID: NF:wdm.IoUnregisterContainerNotification
title: IoUnregisterContainerNotification function
author: windows-driver-content
description: The IoUnregisterContainerNotification routine cancels a container notification registration that was previously created by the IoRegisterContainerNotification routine.
old-location: kernel\iounregistercontainernotification.htm
old-project: kernel
ms.assetid: e8c1dee9-515f-4844-aa3e-8deab660bd33
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoUnregisterContainerNotification routine [Kernel-Mode Driver Architecture], k104_92c44631-4032-4538-bc1b-6463c3ae3c76.xml, kernel.iounregistercontainernotification, wdm/IoUnregisterContainerNotification, IoUnregisterContainerNotification
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating system.
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
-	IoUnregisterContainerNotification
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoUnregisterContainerNotification function


## -description


The <b>IoUnregisterContainerNotification</b> routine cancels a container notification registration that was previously created by the <a href="..\wdm\nf-wdm-ioregistercontainernotification.md">IoRegisterContainerNotification</a> routine.


## -syntax


````
VOID IoUnregisterContainerNotification(
  _In_ PVOID CallbackRegistration
);
````


## -parameters




### -param CallbackRegistration [in]

A pointer to a callback registration object that was created by a previous call to <b>IoRegisterContainerNotification</b>.


## -returns


None



## -remarks


After this routine returns, the <i>CallbackRegistration</i> pointer value is no longer valid.



## -see-also

<a href="..\wdm\nf-wdm-ioregistercontainernotification.md">IoRegisterContainerNotification</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoUnregisterContainerNotification routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

