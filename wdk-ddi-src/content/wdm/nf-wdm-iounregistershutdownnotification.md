---
UID: NF:wdm.IoUnregisterShutdownNotification
title: IoUnregisterShutdownNotification function
author: windows-driver-content
description: The IoUnregisterShutdownNotification routine removes a registered driver from the shutdown notification queue.
old-location: kernel\iounregistershutdownnotification.htm
old-project: kernel
ms.assetid: b48a38ff-60b9-4c01-ac71-4ae07010db1f
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IoUnregisterShutdownNotification, IoUnregisterShutdownNotification routine [Kernel-Mode Driver Architecture], k104_f242a3dc-8338-4d64-bad7-0cca78c30a45.xml, kernel.iounregistershutdownnotification, wdm/IoUnregisterShutdownNotification
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
req.ddi-compliance: IrqlIoPassive5, PowerIrpDDis, HwStorPortProhibitedDDIs
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
-	IoUnregisterShutdownNotification
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoUnregisterShutdownNotification function


## -description


The <b>IoUnregisterShutdownNotification</b> routine removes a registered driver from the shutdown notification queue.


## -syntax


````
VOID IoUnregisterShutdownNotification(
  _In_ PDEVICE_OBJECT DeviceObject
);
````


## -parameters




### -param DeviceObject [in]

Pointer to the driver's device object.


## -returns



None




## -remarks



<b>IoUnregisterShutdownNotification</b> can be called by a driver only if that driver previously called <a href="..\wdm\nf-wdm-ioregistershutdownnotification.md">IoRegisterShutdownNotification</a> or <a href="..\wdm\nf-wdm-ioregisterlastchanceshutdownnotification.md">IoRegisterLastChanceShutdownNotification</a> with the given <i>DeviceObject</i>. This routine is usually called from a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff564886">Unload</a> routine.

Calling <b>IoUnregisterShutdownNotification</b> cancels all shutdown notifications that have been registered for the given <i>DeviceObject</i>. 




## -see-also

<a href="..\wdm\nf-wdm-ioregistershutdownnotification.md">IoRegisterShutdownNotification</a>



<a href="..\wdm\nf-wdm-ioregisterlastchanceshutdownnotification.md">IoRegisterLastChanceShutdownNotification</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoUnregisterShutdownNotification routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

