---
UID: NF:hidsdi.HidD_FlushQueue
title: HidD_FlushQueue function
author: windows-driver-content
description: The HidD_FlushQueue routine deletes all pending input reports in a top-level collection's input queue.
old-location: hid\hidd_flushqueue.htm
old-project: hid
ms.assetid: 4ddc2d50-4828-4764-a690-27d4d5bd7c74
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: hid.hidd_flushqueue, HidD_FlushQueue, hidfunc_3709367d-c7ad-4754-a4bc-c8ccf2752188.xml, HidD_FlushQueue routine [Human Input Devices], hidsdi/HidD_FlushQueue
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	DllExport
apilocation: 
-	Hid.dll
apiname: 
-	HidD_FlushQueue
product: Windows
targetos: Windows
req.typenames: *PHID_MINIDRIVER_REGISTRATION, HID_MINIDRIVER_REGISTRATION
---

# HidD_FlushQueue function


## -description


The <b>HidD_FlushQueue</b> routine deletes all pending input reports in a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection's</a> input queue.


## -syntax


````
BOOLEAN __stdcall HidD_FlushQueue(
  _In_ HANDLE HidDeviceObject
);
````


## -parameters




### -param HidDeviceObject [in]

Specifies an open handle to the top-level collection whose input queue is flushed.


## -returns


<b>HidD_FlushQueue</b> returns <b>TRUE</b> if it successfully flushes the queue. Otherwise, it returns <b>FALSE</b>.



## -remarks


Only user-mode applications can call <b>HidD_FlushQueue</b>. Kernel-mode drivers can use an <a href="..\hidclass\ni-hidclass-ioctl_hid_flush_queue.md">IOCTL_HID_FLUSH_QUEUE</a> request.

For more information, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>.



## -see-also

<a href="..\hidclass\ni-hidclass-ioctl_hid_flush_queue.md">IOCTL_HID_FLUSH_QUEUE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HidD_FlushQueue routine%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

