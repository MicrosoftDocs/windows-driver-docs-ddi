---
UID: NF:wia_lh.IWiaImageFilter.FilterPreviewImage
title: IWiaImageFilter::FilterPreviewImage (wia_lh.h)
description: The IWiaImageFilter::FilterPreviewImage method is called by the WIA Preview component, when an application calls the IWiaPreview::UpdatePreview method.
tech.root: image
ms.date: 11/10/2022
keywords: ["IWiaImageFilter::FilterPreviewImage"]
ms.keywords: FilterPreviewImage, FilterPreviewImage method [Imaging Devices], FilterPreviewImage method [Imaging Devices],IWiaImageFilter interface, IWiaErrorHandler_22a9ad6b-b9f4-49e5-9c62-2d32fbaf3d02.xml, IWiaImageFilter interface [Imaging Devices],FilterPreviewImage method, IWiaImageFilter.FilterPreviewImage, IWiaImageFilter::FilterPreviewImage, image.iwiaimagefilter_filterpreviewimage, wia_lh/IWiaImageFilter::FilterPreviewImage
req.header: wia_lh.h
req.include-header: Wia_lh.h
req.target-type: Desktop
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWiaImageFilter::FilterPreviewImage
 - wia_lh/IWiaImageFilter::FilterPreviewImage
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - wia_lh.h
api_name:
 - IWiaImageFilter::FilterPreviewImage
---

## -description

The **IWiaImageFilter::FilterPreviewImage** method is called by the WIA Preview component, when an application calls the [**IWiaPreview::UpdatePreview**](/windows/win32/wia/-wia-iwiapreview-updatepreview) method.

## -parameters

### -param lFlags

### -param pWiaChildItem2 [in]

Pointer to the item that the image process is to process. This item must be a child item of the item specified in the *pWiaItem2* parameter, which was passed into the [**IWiaImageFilter::InitializeFilter**](nf-wia_lh-iwiaimagefilter-initializefilter.md) method.

### -param InputImageExtents [in]

Structure that contains the upper-left and lower-right coordinates of a rectangle that represents the boundaries of the preview image on the flatbed's platen. This is also the coordinates for the image data that is passed into the *pInputStream* parameter .

### -param pInputStream [in]

Pointer to the [**IStream**](/windows/win32/api/objidl/nn-objidl-istream) preview image.

## -returns

Returns S_OK on success, or a standard COM error code on failure.

## -remarks

This method cannot be invoked directly by the application.
