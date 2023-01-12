---
UID: NF:wia_lh.IWiaSegmentationFilter.DetectRegions
title: IWiaSegmentationFilter::DetectRegions (wia_lh.h)
description: The IWiaSegmentationFilter::DetectRegions method determines the subregions of an image laid out on the flatbed platen so that each subregion can be acquired into a separate image item.
tech.root: image
ms.date: 11/10/2022
keywords: ["IWiaSegmentationFilter::DetectRegions"]
ms.keywords: DetectRegions, DetectRegions method [Imaging Devices], DetectRegions method [Imaging Devices],IWiaSegmentationFilter interface, IWiaSegmentationFilter interface [Imaging Devices],DetectRegions method, IWiaSegmentationFilter.DetectRegions, IWiaSegmentationFilter::DetectRegions, image.iwiasegmentationfilter_detectregions, iwiasegmentationfilter_d819daf8-a36c-448c-a566-bb3c864cea40.xml, wia_lh/IWiaSegmentationFilter::DetectRegions
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
 - IWiaSegmentationFilter::DetectRegions
 - wia_lh/IWiaSegmentationFilter::DetectRegions
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - wia_lh.h
api_name:
 - IWiaSegmentationFilter::DetectRegions
---

## -description

The **IWiaSegmentationFilter::DetectRegions** method determines the subregions of an image laid out on the flatbed platen so that each subregion can be acquired into a separate image item.

## -parameters

### -param lFlags [in]

Currently unused. Should be set to zero.

### -param pInputStream [in, optional]

Specifies a pointer to the [**IStream**](/windows/win32/api/objidl/nn-objidl-istream) preview image.

### -param pWiaItem2 [in, optional]

Specifies a pointer to the [**IWiaItem2**](/windows/win32/wia/-wia-iwiaitem2) item for which *pInputStream* was acquired. The segmentation filter creates child items for this item.

## -returns

Returns S_OK if successful, or a standard COM error value otherwise.

## -remarks

This method determines the subregions of the image represented by *pInputStream*. For each subregion that it detects, it creates a child item for the **IWiaItem2**] item pointed to by the *pWiaItem2* parameter. For each child item, the segmentation filter must set values for the bounding rectangle of the area to scan, using the following WIA scanner item properties:

[WIA_IPS_XPOS](/windows-hardware/drivers/image/wia-ips-xpos)

[WIA_IPS_YPOS](/windows-hardware/drivers/image/wia-ips-ypos)

[WIA_IPS_XEXTENT](/windows-hardware/drivers/image/wia-ips-xextent)

[WIA_IPS_YEXTENT](/windows-hardware/drivers/image/wia-ips-yextent)

A more advanced filter might also require other scanner item properties, such as [WIA_IPS_DESKEW_X](/windows-hardware/drivers/image/wia-ips-deskew-x) and [WIA_IPS_DESKEW_Y](/windows-hardware/drivers/image/wia-ips-deskew-y), if the driver supports deskewing.

If an application calls **IWiaSegmentationFilter::DetectRegions** more than once, the application must first delete the child items created by the last call to the **IWiaSegmentationFilter::DetectRegions** method.

If an application changes any properties into *pWiaItem2*, between acquiring the image into *pInputStream* and its call to **IWiaSegmentationFilter::DetectRegions**, the original property settings (the property settings the item had when the stream was acquired) must be restored. This can be done using [**IWiaPropertyStorage::GetPropertyStream**](/windows/win32/api/wia_xp/nf-wia_xp-iwiapropertystorage-getpropertystream) and [**IWiaPropertyStorage::SetPropertyStream**](/windows/win32/api/wia_xp/nf-wia_xp-iwiapropertystorage-setpropertystream).

The application must reset the **IStream** preview if its call passes the same stream into the segmentation filter more than once. The application must also reset the stream after the initial download and before calling **IWiaSegmentationFilter::DetectRegions**.

## -see-also

[**IStream**](/windows/win32/api/objidl/nn-objidl-istream)

[**IWiaItem2**](/windows/win32/wia/-wia-iwiaitem2)

[**IWiaPropertyStorage**](/windows/win32/api/wia_xp/nn-wia_xp-iwiapropertystorage)
