---
UID: NF:wiamindr_lh.IWiaMiniDrv.drvReadItemProperties
title: IWiaMiniDrv::drvReadItemProperties (wiamindr_lh.h)
description: The IWiaMiniDrv::drvReadItemProperties method reads the driver item properties that need to be updated.
old-location: image\iwiaminidrv_drvreaditemproperties.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["IWiaMiniDrv::drvReadItemProperties"]
ms.keywords: IWiaMiniDrv interface [Imaging Devices],drvReadItemProperties method, IWiaMiniDrv.drvReadItemProperties, IWiaMiniDrv::drvReadItemProperties, MiniDrv_515d9cc7-c76a-4a15-9cc1-59be834382fe.xml, drvReadItemProperties, drvReadItemProperties method [Imaging Devices], drvReadItemProperties method [Imaging Devices],IWiaMiniDrv interface, image.iwiaminidrv_drvreaditemproperties, wiamindr_lh/IWiaMiniDrv::drvReadItemProperties
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWiaMiniDrv::drvReadItemProperties
 - wiamindr_lh/IWiaMiniDrv::drvReadItemProperties
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - wiamindr_lh.h
api_name:
 - IWiaMiniDrv::drvReadItemProperties
---

# IWiaMiniDrv::drvReadItemProperties


## -description

The **IWiaMiniDrv::drvReadItemProperties** method reads the driver item properties that need to be updated.

## -parameters

### -param __MIDL__IWiaMiniDrv0025

lFlags [in]

- Is reserved. Set to zero.

### -param __MIDL__IWiaMiniDrv0026

nPropSpec [in]

- Indicates the number of items in the *pPropSpec* array.

### -param __MIDL__IWiaMiniDrv0027

pPropSpec [in]

- Points to the first element of an array of [PROPSPEC](/windows/win32/api/propidlbase/ns-propidlbase-propspec) structures.

### -param __MIDL__IWiaMiniDrv0028

pWiasContext [in]

- Pointer to a WIA item context.

### -param __MIDL__IWiaMiniDrv0029

plDevErrVal [out]

- Points to a memory location that will receive a status code for this method. If this method returns S_OK, the value stored will be zero. Otherwise, a minidriver-specific error code will be stored at the location pointed to by this parameter.

#### - lFlags [in]

Is reserved. Set to zero.

#### - nPropSpec [in]

Indicates the number of items in the *pPropSpec* array.

#### - pPropSpec [in]

Points to the first element of an array of [PROPSPEC](/windows/win32/api/propidlbase/ns-propidlbase-propspec) structures.

#### - pWiasContext [in]

Pointer to a WIA item context.

#### - plDevErrVal [out]

Points to a memory location that will receive a status code for this method. If this method returns S_OK, the value stored will be zero. Otherwise, a minidriver-specific error code will be stored at the location pointed to by this parameter.

## -returns

On success, the method should return S_OK and clear the device error value pointed to by *plDevErrVal*. If the method fails, it should return a standard COM error code and place a minidriver-specific error code value in the memory pointed to by *plDevErrVal*.

The value pointed to by *plDevErrVal* can be converted to a string by calling [IWiaMiniDrv::drvGetDeviceErrorStr](./nf-wiamindr_lh-iwiaminidrv-drvgetdeviceerrorstr.md).

## -remarks

In this method, the minidriver should read the requested properties from the device.

## -see-also

[IWiaMiniDrv](./nn-wiamindr_lh-iwiaminidrv.md)

[IWiaMiniDrv::drvGetDeviceErrorStr](./nf-wiamindr_lh-iwiaminidrv-drvgetdeviceerrorstr.md)

[IWiaMiniDrv::drvWriteItemProperties](./nf-wiamindr_lh-iwiaminidrv-drvwriteitemproperties.md)

[wiasWriteMultiple](../wiamdef/nf-wiamdef-wiaswritemultiple.md)

[wiasWritePropBin](../wiamdef/nf-wiamdef-wiaswritepropbin.md)

[wiasWritePropFloat](../wiamdef/nf-wiamdef-wiaswritepropfloat.md)

[wiasWritePropGuid](../wiamdef/nf-wiamdef-wiaswritepropguid.md)

[wiasWritePropLong](../wiamdef/nf-wiamdef-wiaswriteproplong.md)

[wiasWritePropStr](../wiamdef/nf-wiamdef-wiaswritepropstr.md)

