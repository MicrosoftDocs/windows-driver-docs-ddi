---
UID: NF:wiamindr_lh.IWiaMiniDrv.drvValidateItemProperties
title: IWiaMiniDrv::drvValidateItemProperties (wiamindr_lh.h)
description: The IWiaMiniDrv::drvValidateItemProperties method validates an item's properties against the set of valid values for each property and will update those properties if necessary.
old-location: image\iwiaminidrv_drvvalidateitemproperties.htm
tech.root: image
ms.assetid: 12052128-9ea7-41cd-bb75-be7175e26c12
ms.date: 05/03/2018
keywords: ["IWiaMiniDrv::drvValidateItemProperties"]
ms.keywords: IWiaMiniDrv interface [Imaging Devices],drvValidateItemProperties method, IWiaMiniDrv.drvValidateItemProperties, IWiaMiniDrv::drvValidateItemProperties, MiniDrv_b288e05c-a142-452a-9ac7-ffb2dfcae4cf.xml, drvValidateItemProperties, drvValidateItemProperties method [Imaging Devices], drvValidateItemProperties method [Imaging Devices],IWiaMiniDrv interface, image.iwiaminidrv_drvvalidateitemproperties, wiamindr_lh/IWiaMiniDrv::drvValidateItemProperties
f1_keywords:
 - "wiamindr_lh/IWiaMiniDrv.drvValidateItemProperties"
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
- IWiaMiniDrv.drvValidateItemProperties
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWiaMiniDrv::drvValidateItemProperties

## -description

The **IWiaMiniDrv::drvValidateItemProperties** method validates an item's properties against the set of valid values for each property and will update those properties if necessary.

## -parameters

### -param __MIDL__IWiaMiniDrv0016

lFlags [in]

- Is reserved. Set to zero.

### -param __MIDL__IWiaMiniDrv0017

nPropSpec [in]

- Indicates the number of items n the *pPropSpec* array.

### -param __MIDL__IWiaMiniDrv0018

pPropSpec [in]

- Points to the first element of an array of **PROPSPEC** structures.

### -param __MIDL__IWiaMiniDrv0019

pWiasContext [in]

- Pointer to a WIA item context.

### -param __MIDL__IWiaMiniDrv0020

plDevErrVal [out]

- Points to a memory location that will receive a status code for this method. If this method returns **S_OK**, the value stored will be zero. Otherwise, a minidriver-specific error code will be stored at the location pointed to by this parameter.

#### - lFlags [in]

Is reserved. Set to zero.

#### - nPropSpec [in]

Indicates the number of items n the *pPropSpec* array.

#### - pPropSpec [in]

Points to the first element of an array of **PROPSPEC** structures.

#### - pWiasContext [in]

Pointer to a WIA item context.

#### - plDevErrVal [out]

Points to a memory location that will receive a status code for this method. If this method returns **S_OK**, the value stored will be zero. Otherwise, a minidriver-specific error code will be stored at the location pointed to by this parameter.

## -returns

On success, the method should return **S_OK** and clear the device error value pointed to by *plDevErrVal*. If the method fails, it should return a standard COM error code and place a minidriver-specific error code value in the memory pointed to by *plDevErrVal*.

The value pointed to by *plDevErrVal* can be converted to a string by calling [IWiaMiniDrv::drvGetDeviceErrorStr](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvgetdeviceerrorstr).

## -see-also

[IWiaMiniDrv](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nn-wiamindr_lh-iwiaminidrv)

[IWiaMiniDrv::drvGetDeviceErrorStr](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvgetdeviceerrorstr)

[wiasGetItemType](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasgetitemtype)

[wiasValidateItemProperties](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasvalidateitemproperties)
