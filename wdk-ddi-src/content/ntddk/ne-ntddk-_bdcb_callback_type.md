---
UID: NE:ntddk._BDCB_CALLBACK_TYPE
title: _BDCB_CALLBACK_TYPE
author: windows-driver-content
description: The BDCB_CALLBACK_TYPE enumeration specifies whether the callback being passed to a BOOT_DRIVER_CALLBACK_FUNCTION routine is a status update or a boot-start driver initialization notification.
old-location: kernel\bdcb_callback_type.htm
old-project: kernel
ms.assetid: 22698DF4-7B8C-40B8-9B07-EEDCC03D0D0F
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _BDCB_CALLBACK_TYPE, *PBDCB_CALLBACK_TYPE, BDCB_CALLBACK_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with  Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BDCB_CALLBACK_TYPE
req.alt-loc: ntddk.h
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
req.typenames: *PBDCB_CALLBACK_TYPE, BDCB_CALLBACK_TYPE
---

# _BDCB_CALLBACK_TYPE enumeration



## -description
The BDCB_CALLBACK_TYPE enumeration specifies  whether the callback being passed to a <a href="..\ntddk\nf-ntddk-ioregisterbootdrivercallback.md">BOOT_DRIVER_CALLBACK_FUNCTION</a> routine is a status update or a boot-start driver initialization notification.



## -syntax

````
typedef enum _BDCB_CALLBACK_TYPE { 
  BdCbStatusUpdate,
  BdCbInitializeImage
} BDCB_CALLBACK_TYPE;
````


## -enum-fields

### -field BdCbStatusUpdate

A status update provided by the system to a boot-start driver.


### -field BdCbInitializeImage

A boot image is about to be initialized. During this callback, boot-start drivers may classify a boot image as a known good image or a known bad image.


## -remarks
The two callback types have unique context structures that provide additional information specific to the callback.

BdCbStatusUpdate


<a href="..\ntddk\ne-ntddk-_bdcb_status_update_type.md">BDCB_STATUS_UPDATE_TYPE</a>


BdCbInitializeImage


<a href="..\ntddk\ne-ntddk-_bdcb_classification.md">BDCB_CLASSIFICATION</a>



## -see-also
<dl>
<dt>
<a href="..\ntddk\nf-ntddk-ioregisterbootdrivercallback.md">BOOT_DRIVER_CALLBACK_FUNCTION</a>
</dt>
<dt>
<a href="..\ntddk\ne-ntddk-_bdcb_status_update_type.md">BDCB_STATUS_UPDATE_TYPE</a>
</dt>
<dt>
<a href="..\ntddk\ne-ntddk-_bdcb_classification.md">BDCB_CLASSIFICATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20BDCB_CALLBACK_TYPE enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

