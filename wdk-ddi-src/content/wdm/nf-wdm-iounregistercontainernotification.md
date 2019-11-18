---
UID: NF:wdm.IoUnregisterContainerNotification
title: IoUnregisterContainerNotification function (wdm.h)
description: The IoUnregisterContainerNotification routine cancels a container notification registration that was previously created by the IoRegisterContainerNotification routine.
old-location: kernel\iounregistercontainernotification.htm
tech.root: kernel
ms.assetid: e8c1dee9-515f-4844-aa3e-8deab660bd33
ms.date: 04/30/2018
ms.keywords: IoUnregisterContainerNotification, IoUnregisterContainerNotification routine [Kernel-Mode Driver Architecture], k104_92c44631-4032-4538-bc1b-6463c3ae3c76.xml, kernel.iounregistercontainernotification, wdm/IoUnregisterContainerNotification
ms.topic: function
f1_keywords:
 - "wdm/IoUnregisterContainerNotification"
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoUnregisterContainerNotification
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoUnregisterContainerNotification function


## -description


The <b>IoUnregisterContainerNotification</b> routine cancels a container notification registration that was previously created by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioregistercontainernotification">IoRegisterContainerNotification</a> routine.


## -parameters




### -param CallbackRegistration [in]

A pointer to a callback registration object that was created by a previous call to <b>IoRegisterContainerNotification</b>.


## -remarks



After this routine returns, the <i>CallbackRegistration</i> pointer value is no longer valid.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioregistercontainernotification">IoRegisterContainerNotification</a>
 

 

