---
UID: NF:wia_lh.IWiaImageFilter.FilterPreviewImage
title: IWiaImageFilter::FilterPreviewImage (wia_lh.h)
description: The IWiaImageFilter::FilterPreviewImage method is called by the WIA Preview component, when an application calls the IWiaPreview::UpdatePreview method.
old-location: image\iwiaimagefilter_filterpreviewimage.htm
tech.root: image
ms.assetid: 92e4ea13-156b-4d5e-8268-ddb45f6d7b50
ms.date: 05/03/2018
ms.keywords: FilterPreviewImage, FilterPreviewImage method [Imaging Devices], FilterPreviewImage method [Imaging Devices],IWiaImageFilter interface, IWiaErrorHandler_22a9ad6b-b9f4-49e5-9c62-2d32fbaf3d02.xml, IWiaImageFilter interface [Imaging Devices],FilterPreviewImage method, IWiaImageFilter.FilterPreviewImage, IWiaImageFilter::FilterPreviewImage, image.iwiaimagefilter_filterpreviewimage, wia_lh/IWiaImageFilter::FilterPreviewImage
f1_keywords:
 - "wia_lh/IWiaImageFilter.FilterPreviewImage"
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- wia_lh.h
api_name:
- IWiaImageFilter.FilterPreviewImage
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWiaImageFilter::FilterPreviewImage


## -description


The <b>IWiaImageFilter::FilterPreviewImage</b> method is called by the WIA Preview component, when an application calls the <b>IWiaPreview::UpdatePreview</b> method.


## -parameters




### -param lFlags




### -param pWiaChildItem2 [in]

Pointer to the item that the image process is to process. This item must be a child item of the item specified in the pWiaItem2 parameter, which was passed into the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wia_lh/nf-wia_lh-iwiaimagefilter-initializefilter">IWiaImageFilter::InitializeFilter</a> method. 



### -param InputImageExtents [in]

Structure that contains the upper-left and lower-right coordinates of a rectangle that represents the boundaries of the preview image on the flatbed's platen. This is also the coordinates for the image data that is passed into the <i>pInputStream</i> parameter .


### -param pInputStream [in]

Pointer to the IStream preview image. 


## -returns



Returns S_OK on success, or a standard COM error code on failure.




## -remarks



This method cannot be invoked directly by the application.

The <b>IStream </b>and <b>IWiaPreview</b> interfaces are described in the Microsoft Windows SDK documentation.



