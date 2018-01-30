---
UID: NF:wia_lh.IWiaImageFilter.FilterPreviewImage
title: IWiaImageFilter::FilterPreviewImage method
author: windows-driver-content
description: The IWiaImageFilter::FilterPreviewImage method is called by the WIA Preview component, when an application calls the IWiaPreview::UpdatePreview method.
old-location: image\iwiaimagefilter_filterpreviewimage.htm
old-project: image
ms.assetid: 92e4ea13-156b-4d5e-8268-ddb45f6d7b50
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: FilterPreviewImage method [Imaging Devices], IWiaImageFilter interface, image.iwiaimagefilter_filterpreviewimage, wia_lh/IWiaImageFilter::FilterPreviewImage, FilterPreviewImage, IWiaImageFilter, IWiaImageFilter::FilterPreviewImage, FilterPreviewImage method [Imaging Devices], IWiaImageFilter interface [Imaging Devices], FilterPreviewImage method, IWiaErrorHandler_22a9ad6b-b9f4-49e5-9c62-2d32fbaf3d02.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wia_lh.h
req.include-header: Wia_lh.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.lib: wia_lh.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	wia_lh.h
apiname:
-	IWiaImageFilter.FilterPreviewImage
product: Windows
targetos: Windows
req.typenames: BMP_IMAGE_INFO, *PBMP_IMAGE_INFO
req.product: Windows 10 or later.
---

# IWiaImageFilter::FilterPreviewImage method


## -description


The <b>IWiaImageFilter::FilterPreviewImage</b> method is called by the WIA Preview component, when an application calls the <b>IWiaPreview::UpdatePreview</b> method.


## -syntax


````
HRESULT  FilterPreviewImage(
  [in] IWiaItem2   *pWiaChildItem2,
  [in] RECT        InputImageExtents,
  [in] IStream     *pInputStream
    
);
````


## -parameters




### -param lFlags




### -param pWiaChildItem2 [in]

Pointer to the item that the image process is to process. This item must be a child item of the item specified in the pWiaItem2 parameter, which was passed into the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543916">IWiaImageFilter::InitializeFilter</a> method. 



### -param InputImageExtents [in]

Structure that contains the upper-left and lower-right coordinates of a rectangle that represents the boundaries of the preview image on the flatbed's platen. This is also the coordinates for the image data that is passed into the <i>pInputStream</i> parameter .


### -param pInputStream [in]

Pointer to the IStream preview image. 


## -returns


Returns S_OK on success, or a standard COM error code on failure.



## -remarks


This method cannot be invoked directly by the application.

The <b>IStream </b>and <b>IWiaPreview</b> interfaces are described in the Microsoft Windows SDK documentation.


