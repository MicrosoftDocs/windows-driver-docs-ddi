---
UID: NS:ksmedia.tagKS_BITMAPINFOHEADER
title: tagKS_BITMAPINFOHEADER
author: windows-driver-content
description: The KS_BITMAPINFOHEADER structure describes details about the video stream, such as image dimensions and pixel depth.
old-location: stream\ks_bitmapinfoheader.htm
old-project: stream
ms.assetid: 77101494-97bb-4049-8c6c-cdb4ee82f312
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: tagKS_BITMAPINFOHEADER, KS_BITMAPINFOHEADER, *PKS_BITMAPINFOHEADER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KS_BITMAPINFOHEADER
req.alt-loc: ksmedia.h
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
req.typenames: KS_BITMAPINFOHEADER, *PKS_BITMAPINFOHEADER
---

# tagKS_BITMAPINFOHEADER structure



## -description
The KS_BITMAPINFOHEADER structure describes details about the video stream, such as image dimensions and pixel depth. 



## -syntax

````
typedef struct tagKS_BITMAPINFOHEADER {
  DWORD biSize;
  LONG  biWidth;
  LONG  biHeight;
  WORD  biPlanes;
  WORD  biBitCount;
  DWORD biCompression;
  DWORD biSizeImage;
  LONG  biXPelsPerMeter;
  LONG  biYPelsPerMeter;
  DWORD biClrUsed;
  DWORD biClrImportant;
} KS_BITMAPINFOHEADER, *PKS_BITMAPINFOHEADER;
````


## -struct-fields

### -field biSize

Specifies the size of the structure in bytes.


### -field biWidth

Specifies the width of the bitmap in pixels.


### -field biHeight

Specifies the height of the bitmap in pixels.


### -field biPlanes

Specifies the number of planes. This is always set to 1.


### -field biBitCount

Specifies the color bits per pixel. For example, 1, 4, 8, or 24.


### -field biCompression

Specifies the compression scheme.


### -field biSizeImage

Specifies the size of bitmap bits in bytes. (Only required if using compression.)


### -field biXPelsPerMeter

Specifies the horizontal resolution in pixels per meter.


### -field biYPelsPerMeter

Specifies the vertical resolution in pixels per meter.


### -field biClrUsed

Specifies the number of colors used in the image.


### -field biClrImportant

Specifies the number of important colors in the image.


## -remarks
This is the same structure as the user-mode GDI bitmap header (BITMAPINFOHEADER) structure.</p>