---
UID: NF:hidsdi.HidD_FlushQueue
title: HidD_FlushQueue function (hidsdi.h)
description: The HidD_FlushQueue routine deletes all pending input reports in a top-level collection's input queue.
old-location: hid\hidd_flushqueue.htm
tech.root: hid
ms.date: 06/19/2019
keywords: ["HidD_FlushQueue function"]
ms.keywords: HidD_FlushQueue, HidD_FlushQueue routine [Human Input Devices], hid.hidd_flushqueue, hidfunc_3709367d-c7ad-4754-a4bc-c8ccf2752188.xml, hidsdi/HidD_FlushQueue
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
targetos: Windows
req.typenames: 
f1_keywords:
 - HidD_FlushQueue
 - hidsdi/HidD_FlushQueue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Hid.dll
api_name:
 - HidD_FlushQueue
---

# HidD_FlushQueue function


## -description

The <b>HidD_FlushQueue</b> routine deletes all pending input reports in a <a href="/windows-hardware/drivers/hid/top-level-collections">top-level collection's</a> input queue.

## -parameters

### -param HidDeviceObject 

[in]
Specifies an open handle to the top-level collection whose input queue is flushed.

## -returns

<b>HidD_FlushQueue</b> returns <b>TRUE</b> if it successfully flushes the queue. Otherwise, it returns <b>FALSE</b>. Use [**GetLastError**](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) to get extended error information.

## -remarks

Only user-mode applications can call <b>HidD_FlushQueue</b>. Kernel-mode drivers can use an <a href="/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_flush_queue">IOCTL_HID_FLUSH_QUEUE</a> request.

For more information, see <a href="/windows-hardware/drivers/hid/hid-collections">HID Collections</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_flush_queue">IOCTL_HID_FLUSH_QUEUE</a>
