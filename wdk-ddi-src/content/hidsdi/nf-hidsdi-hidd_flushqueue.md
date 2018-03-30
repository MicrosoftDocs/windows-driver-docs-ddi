---
UID: NF:hidsdi.HidD_FlushQueue
title: HidD_FlushQueue function
author: windows-driver-content
description: The HidD_FlushQueue routine deletes all pending input reports in a top-level collection's input queue.
old-location: hid\hidd_flushqueue.htm
old-project: hid
ms.assetid: 4ddc2d50-4828-4764-a690-27d4d5bd7c74
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: HidD_FlushQueue, HidD_FlushQueue routine [Human Input Devices], hid.hidd_flushqueue, hidfunc_3709367d-c7ad-4754-a4bc-c8ccf2752188.xml, hidsdi/HidD_FlushQueue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hidsdi.h
req.include-header: Hidsdi.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
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
req.lib: Hid.lib
req.dll: Hid.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Hid.dll
api_name:
-	HidD_FlushQueue
product: Windows
targetos: Windows
req.typenames: HID_MINIDRIVER_REGISTRATION, *PHID_MINIDRIVER_REGISTRATION
---

# HidD_FlushQueue function


## -description


The <b>HidD_FlushQueue</b> routine deletes all pending input reports in a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection's</a> input queue.


## -parameters




### -param HidDeviceObject [in]

Specifies an open handle to the top-level collection whose input queue is flushed.


## -returns



<b>HidD_FlushQueue</b> returns <b>TRUE</b> if it successfully flushes the queue. Otherwise, it returns <b>FALSE</b>.




## -remarks



Only user-mode applications can call <b>HidD_FlushQueue</b>. Kernel-mode drivers can use an <a href="https://msdn.microsoft.com/library/windows/hardware/ff541083">IOCTL_HID_FLUSH_QUEUE</a> request.

For more information, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541083">IOCTL_HID_FLUSH_QUEUE</a>
 

 

