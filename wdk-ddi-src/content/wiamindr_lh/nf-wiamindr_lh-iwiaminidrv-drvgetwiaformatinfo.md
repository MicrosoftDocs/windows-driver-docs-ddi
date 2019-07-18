---
UID: NF:wiamindr_lh.IWiaMiniDrv.drvGetWiaFormatInfo
title: IWiaMiniDrv::drvGetWiaFormatInfo (wiamindr_lh.h)
description: The IWiaMiniDrv::drvGetWiaFormatInfo method finds the image formats and media types that the WIA hardware device supports.
old-location: image\iwiaminidrv_drvgetwiaformatinfo.htm
tech.root: image
ms.assetid: f0b7d982-735f-489c-b9f8-81a287f6722a
ms.date: 05/03/2018
ms.keywords: IWiaMiniDrv interface [Imaging Devices],drvGetWiaFormatInfo method, IWiaMiniDrv.drvGetWiaFormatInfo, IWiaMiniDrv::drvGetWiaFormatInfo, MiniDrv_6c0cb527-6884-4b7d-a7cc-0e09c1774b7f.xml, drvGetWiaFormatInfo, drvGetWiaFormatInfo method [Imaging Devices], drvGetWiaFormatInfo method [Imaging Devices],IWiaMiniDrv interface, image.iwiaminidrv_drvgetwiaformatinfo, wiamindr_lh/IWiaMiniDrv::drvGetWiaFormatInfo
ms.topic: method
req.header: wiamindr_lh.h
req.include-header: Wiamindr.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- wiamindr_lh.h
api_name:
- IWiaMiniDrv.drvGetWiaFormatInfo
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWiaMiniDrv::drvGetWiaFormatInfo

## -description

The **IWiaMiniDrv::drvGetWiaFormatInfo** method finds the image formats and media types that the WIA hardware device supports.

## -parameters

### -param __MIDL__IWiaMiniDrv0059

lFlags [in]

Is currently unused.

### -param __MIDL__IWiaMiniDrv0060

pWiasContext [in]

Pointer to a WIA item context.

### -param __MIDL__IWiaMiniDrv0061

pcelt [out]

Points to a memory location that will receive the number of items in the array pointed to by *ppwfi*.

### -param __MIDL__IWiaMiniDrv0062

plDevErrVal [out]

Points to a memory location that will receive a status code for this method. If this method returns S_OK, the value stored will be zero. Otherwise, a minidriver-specific error code will be stored at the location pointed to by this parameter.

### -param __MIDL__IWiaMiniDrv0063

ppwfi [out, optional]

Points to a memory location that will receive the address of the first element of an array of [WIA_FORMAT_INFO](https://docs.microsoft.com/windows/win32/api/wia_xp/ns-wia_xp-_wia_format_info) structures.

#### - lFlags [in]

Is currently unused.

#### - pWiasContext [in]

Pointer to a WIA item context.

#### - pcelt [out]

Points to a memory location that will receive the number of items in the array pointed to by *ppwfi*.

#### - plDevErrVal [out]

Points to a memory location that will receive a status code for this method. If this method returns S_OK, the value stored will be zero. Otherwise, a minidriver-specific error code will be stored at the location pointed to by this parameter.

#### - ppwfi [out, optional]

Points to a memory location that will receive the address of the first element of an array of [WIA_FORMAT_INFO](https://docs.microsoft.com/windows/win32/api/wia_xp/ns-wia_xp-_wia_format_info) structures.

## -returns

On success, the method should return S_OK and clear the device error value pointed to by *plDevErrVal*. If this method is called for items that do not contain any data, it should return E_INVALIDARG. If the method fails, it should return a standard COM error code and place a minidriver-specific error code value in the memory pointed to by *plDevErrVal*.

The value pointed to by *plDevErrVal* can be converted to a string by calling [IWiaMiniDrv::drvGetDeviceErrorStr](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvgetdeviceerrorstr).

## -remarks

This method creates an array of [WIA_FORMAT_INFO](https://docs.microsoft.com/windows/win32/api/wia_xp/ns-wia_xp-_wia_format_info) structures that describe the media types and image formats that the WIA hardware device supports. For each element in the array, the media type can be one of TYMED_CALLBACK, TYMED_MULTIPAGE_CALLBACK, TYMED_FILE, or TYMED_MULTIPAGE_FILE. Typical values for the image format include WiaImgFmt_JPEG, and WiaImgFmt_BMP, among others. For more information, see [Understanding TYMED](https://docs.microsoft.com/windows-hardware/drivers/image/understanding-tymed) and [WIA_IPA_FILENAME_EXTENSION](https://docs.microsoft.com/windows-hardware/drivers/image/wia-ipa-filename-extension).

The minidriver can define a global array to hold the WIA_FORMAT_INFO structures, or it can allocate memory for the array. The WIA service will not free the allocated memory, so the minidriver should store a pointer to that memory in the driver item context. The minidriver can then free this memory in a call to [IWiaMiniDrv::drvFreeDrvItemContext](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvfreedrvitemcontext).

## -see-also

[IWiaMiniDrv](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nn-wiamindr_lh-iwiaminidrv)

[IWiaMiniDrv::drvFreeDrvItemContext](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvfreedrvitemcontext)

[IWiaMiniDrv::drvGetDeviceErrorStr](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvgetdeviceerrorstr)
