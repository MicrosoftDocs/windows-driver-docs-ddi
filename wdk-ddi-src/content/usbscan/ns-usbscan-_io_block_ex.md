---
UID: NS:usbscan._IO_BLOCK_EX
title: "_IO_BLOCK_EX"
author: windows-driver-content
description: The IO_BLOCK_EX structure is used as a parameter to DeviceIoControl, when the specified I/O control code is IOCTL_SEND_USB_REQUEST.
old-location: image\io_block_ex.htm
old-project: image
ms.assetid: 2474a49b-e275-4b4d-b762-c296b92bab4c
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: stifnc_6b21356d-4f1a-4b8d-a54e-767f46e5b1b3.xml, PIO_BLOCK_EX, PIO_BLOCK_EX structure pointer [Imaging Devices], *PIO_BLOCK_EX, usbscan/PIO_BLOCK_EX, IO_BLOCK_EX structure [Imaging Devices], _IO_BLOCK_EX, usbscan/IO_BLOCK_EX, IO_BLOCK_EX, image.io_block_ex
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
-	IO_BLOCK_EX
product: Windows
targetos: Windows
req.typenames: "*PIO_BLOCK_EX, IO_BLOCK_EX"
req.product: Windows 10 or later.
---

# _IO_BLOCK_EX structure


## -description


The IO_BLOCK_EX structure is used as a parameter to <a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a>, when the specified I/O control code is <a href="..\usbscan\ni-usbscan-ioctl_send_usb_request.md">IOCTL_SEND_USB_REQUEST</a>. Values contained in structure members are used to create a USB Device Request (described in the <i>Universal Serial Bus Specification</i>).


## -syntax


````
typedef struct _IO_BLOCK_EX {
  unsigned uOffset;
  unsigned uLength;
  PUCHAR   pbyData;
  unsigned uIndex;
  UCHAR    bRequest;
  UCHAR    bmRequestType;
  UCHAR    fTransferDirectionIn;
} IO_BLOCK_EX, *PIO_BLOCK_EX;
````


## -struct-fields




#### - uOffset

Used as the <b>Value</b> field of a USB Device Request.


#### - uLength

Length of the buffer to transfer.


#### - pbyData

Pointer to a data buffer with a length of <b>uLength</b>.


#### - uIndex

Used as the <b>Index</b> field of a USB Device Request.


#### - bRequest

Used as the <b>bRequest</b> field of a USB Device Request.


#### - bmRequestType

Used as the <b>bmRequestType</b> field of a USB Device Request.


#### - fTransferDirectionIn

<b>TRUE</b> for transfers from device to host; <b>FALSE</b> for transfers from host to device.

