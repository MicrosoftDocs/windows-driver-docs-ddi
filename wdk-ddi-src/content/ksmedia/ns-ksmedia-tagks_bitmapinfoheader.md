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
ms.keywords: vidcapstruct_14e65a26-c943-4fad-949a-87aaf584e50c.xml, PKS_BITMAPINFOHEADER structure pointer [Streaming Media Devices], ksmedia/KS_BITMAPINFOHEADER, KS_BITMAPINFOHEADER, *PKS_BITMAPINFOHEADER, KS_BITMAPINFOHEADER structure [Streaming Media Devices], PKS_BITMAPINFOHEADER, ksmedia/PKS_BITMAPINFOHEADER, tagKS_BITMAPINFOHEADER, stream.ks_bitmapinfoheader
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
-	ksmedia.h
apiname:
-	KS_BITMAPINFOHEADER
product: Windows
targetos: Windows
req.typenames: "*PKS_BITMAPINFOHEADER, KS_BITMAPINFOHEADER"
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




#### - biSize

Specifies the size of the structure in bytes.


#### - biWidth

Specifies the width of the bitmap in pixels.


#### - biHeight

Specifies the height of the bitmap in pixels.


#### - biPlanes

Specifies the number of planes. This is always set to 1.


#### - biBitCount

Specifies the color bits per pixel. For example, 1, 4, 8, or 24.


#### - biCompression

Specifies the compression scheme.


#### - biSizeImage

Specifies the size of bitmap bits in bytes. (Only required if using compression.)


#### - biXPelsPerMeter

Specifies the horizontal resolution in pixels per meter.


#### - biYPelsPerMeter

Specifies the vertical resolution in pixels per meter.


#### - biClrUsed

Specifies the number of colors used in the image.


#### - biClrImportant

Specifies the number of important colors in the image.


## -remarks


This is the same structure as the user-mode GDI bitmap header (BITMAPINFOHEADER) structure.


