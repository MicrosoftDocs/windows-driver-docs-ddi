---
UID: NF:wdm.PoEndDeviceBusy
title: PoEndDeviceBusy function
author: windows-driver-content
description: The PoEndDeviceBusy routine marks the end of a period of time in which the device is busy.
old-location: kernel\poenddevicebusy.htm
old-project: kernel
ms.assetid: 5ba5cfe7-a745-497e-b5ce-8c7b3d4929f5
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PoEndDeviceBusy, PoEndDeviceBusy routine [Kernel-Mode Driver Architecture], kernel.poenddevicebusy, portn_edd72e85-e155-4a0c-9d6a-836ad448bb61.xml, wdm/PoEndDeviceBusy
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 7.
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	PoEndDeviceBusy
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# PoEndDeviceBusy function


## -description


The <b>PoEndDeviceBusy</b> routine marks the end of a period of time in which the device is busy.


## -syntax


````
VOID PoEndDeviceBusy(
  _Inout_ PULONG IdlePointer
);
````


## -parameters




### -param IdlePointer [in, out]

A pointer to an idle counter. This is a pointer value that was previously returned by the <a href="..\wdm\nf-wdm-poregisterdeviceforidledetection.md">PoRegisterDeviceForIdleDetection</a> routine. Because <b>PoRegisterDeviceForIdleDetection</b> might return a <b>NULL</b> pointer, the caller must verify that the pointer is non-<b>NULL</b> before it calls <b>PoEndDeviceBusy</b>.


## -returns



None




## -remarks



The <a href="..\wdm\nf-wdm-postartdevicebusy.md">PoStartDeviceBusy</a> and <b>PoEndDeviceBusy</b> routines mark the start and end of a time period in which a device is busy. Each call to <b>PoStartDeviceBusy</b> must be followed by a corresponding call to <b>PoEndDeviceBusy</b>. For more information about how these routines work together, see <a href="..\wdm\nf-wdm-postartdevicebusy.md">PoStartDeviceBusy</a>.




## -see-also

<a href="..\wdm\nf-wdm-postartdevicebusy.md">PoStartDeviceBusy</a>



<a href="..\wdm\nf-wdm-poregisterdeviceforidledetection.md">PoRegisterDeviceForIdleDetection</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PoEndDeviceBusy routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

