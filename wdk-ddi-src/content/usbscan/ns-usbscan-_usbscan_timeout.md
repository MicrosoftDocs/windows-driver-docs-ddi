---
UID: NS:usbscan._USBSCAN_TIMEOUT
title: "_USBSCAN_TIMEOUT"
author: windows-driver-content
description: The USBSCAN_TIMEOUT structure stores time-out values for USB bulk IN and bulk OUT operations, and interrupts.
old-location: image\usbscan_timeout.htm
old-project: image
ms.assetid: afa900fc-7297-425b-8308-18806d7d97d3
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: image.usbscan_timeout, stifnc_ebdd7bda-2eb0-446c-a52c-e9a80f6478da.xml, *PUSBSCAN_TIMEOUT, _USBSCAN_TIMEOUT, USBSCAN_TIMEOUT, PUSBSCAN_TIMEOUT structure pointer [Imaging Devices], PUSBSCAN_TIMEOUT, USBSCAN_TIMEOUT structure [Imaging Devices], usbscan/PUSBSCAN_TIMEOUT, usbscan/USBSCAN_TIMEOUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbscan.h
req.include-header: Usbscan.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	usbscan.h
apiname:
-	USBSCAN_TIMEOUT
product: Windows
targetos: Windows
req.typenames: "*PUSBSCAN_TIMEOUT, USBSCAN_TIMEOUT"
req.product: Windows 10 or later.
---

# _USBSCAN_TIMEOUT structure


## -description


The USBSCAN_TIMEOUT structure stores time-out values for USB bulk IN and bulk OUT operations, and interrupts.


## -syntax


````
typedef struct _USBSCAN_TIMEOUT {
  ULONG TimeoutRead;
  ULONG TimeoutWrite;
  ULONG TimeoutEvent;
} USBSCAN_TIMEOUT, *PUSBSCAN_TIMEOUT;
````


## -struct-fields




### -field TimeoutRead

Specifies the number of seconds to wait for a read operation to time out.


### -field TimeoutWrite

Specifies the number of seconds to wait for a write operation to time out.


### -field TimeoutEvent

Specifies the number of seconds to wait for an interrupt to occur.


## -remarks


A value of zero means to wait forever for the read or write operation or interrupt.

The USBSCAN_TIMEOUT structure is used as a parameter to <a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a>, when the specified I/O control code is <a href="..\usbscan\ni-usbscan-ioctl_set_timeout.md">IOCTL_SET_TIMEOUT</a>.



## -see-also

<a href="..\usbscan\ni-usbscan-ioctl_set_timeout.md">IOCTL_SET_TIMEOUT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20USBSCAN_TIMEOUT structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

