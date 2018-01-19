---
UID: NS:wiautil._BMP_IMAGE_INFO
title: _BMP_IMAGE_INFO
author: windows-driver-content
description: The BMP_IMAGE_INFO structure contains information about a BMP image.
old-location: image\bmp_image_info.htm
old-project: image
ms.assetid: 953e2f00-2275-49a2-b1e5-def7763a8ab7
ms.author: windowsdriverdev
ms.date: 1/17/2018
ms.keywords: _BMP_IMAGE_INFO, BMP_IMAGE_INFO, *PBMP_IMAGE_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wiautil.h
req.include-header: Wiautil.h, Wiamindr.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows XP and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BMP_IMAGE_INFO
req.alt-loc: wiautil.h
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
req.typenames: BMP_IMAGE_INFO, *PBMP_IMAGE_INFO
req.product: Windows 10 or later.
---

# _BMP_IMAGE_INFO structure



## -description
The BMP_IMAGE_INFO structure contains information about a BMP image.



## -syntax

````
typedef struct _BMP_IMAGE_INFO {
  INT Width;
  INT Height;
  INT ByteWidth;
  INT Size;
} BMP_IMAGE_INFO, *PBMP_IMAGE_INFO;
````


## -struct-fields

### -field Width

Specifies the width of the image, in pixels.


### -field Height

Specifies the height of the image, in lines.


### -field ByteWidth

Specifies the width of the image, in bytes.


### -field Size

Specifies the total size of the image, including headers, in bytes.


## -remarks
