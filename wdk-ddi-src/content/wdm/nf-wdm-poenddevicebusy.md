---
UID: NF:wdm.PoEndDeviceBusy
title: PoEndDeviceBusy function
author: windows-driver-content
description: The PoEndDeviceBusy routine marks the end of a period of time in which the device is busy.
old-location: kernel\poenddevicebusy.htm
old-project: kernel
ms.assetid: 5ba5cfe7-a745-497e-b5ce-8c7b3d4929f5
ms.author: windowsdriverdev
ms.date: 4/30/2018
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
req.typenames: 
---

# PoEndDeviceBusy function


## -description


The <b>PoEndDeviceBusy</b> routine marks the end of a period of time in which the device is busy.


## -parameters




### -param IdlePointer [in, out]

A pointer to an idle counter. This is a pointer value that was previously returned by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559721">PoRegisterDeviceForIdleDetection</a> routine. Because <b>PoRegisterDeviceForIdleDetection</b> might return a <b>NULL</b> pointer, the caller must verify that the pointer is non-<b>NULL</b> before it calls <b>PoEndDeviceBusy</b>.


## -returns



None




## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff559773">PoStartDeviceBusy</a> and <b>PoEndDeviceBusy</b> routines mark the start and end of a time period in which a device is busy. Each call to <b>PoStartDeviceBusy</b> must be followed by a corresponding call to <b>PoEndDeviceBusy</b>. For more information about how these routines work together, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff559773">PoStartDeviceBusy</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559721">PoRegisterDeviceForIdleDetection</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559773">PoStartDeviceBusy</a>
 

 

