---
UID: NF:wiamindr_lh.IWiaMiniDrv.drvInitItemProperties
title: IWiaMiniDrv::drvInitItemProperties (wiamindr_lh.h)
description: The IWiaMiniDrv::drvInitItemProperties method initializes WIA driver item properties for each item in an application item tree.
old-location: image\iwiaminidrv_drvinititemproperties.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["IWiaMiniDrv::drvInitItemProperties"]
ms.keywords: IWiaMiniDrv interface [Imaging Devices],drvInitItemProperties method, IWiaMiniDrv.drvInitItemProperties, IWiaMiniDrv::drvInitItemProperties, MiniDrv_88720847-db1d-475a-b8c4-62fdb376953a.xml, drvInitItemProperties, drvInitItemProperties method [Imaging Devices], drvInitItemProperties method [Imaging Devices],IWiaMiniDrv interface, image.iwiaminidrv_drvinititemproperties, wiamindr_lh/IWiaMiniDrv::drvInitItemProperties
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
 - IWiaMiniDrv::drvInitItemProperties
 - wiamindr_lh/IWiaMiniDrv::drvInitItemProperties
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - wiamindr_lh.h
api_name:
 - IWiaMiniDrv::drvInitItemProperties
---

# IWiaMiniDrv::drvInitItemProperties


## -description

The **IWiaMiniDrv::drvInitItemProperties** method initializes WIA driver item properties for each item in an application item tree.

## -parameters

### -param __MIDL__IWiaMiniDrv0013

lFlags [in]

- Is reserved. Set to zero.

### -param __MIDL__IWiaMiniDrv0014

pWiasContext [in]

- Pointer to a WIA item context.

### -param __MIDL__IWiaMiniDrv0015

plDevErrVal [out]

- Points to a memory location that will receive a status code for this method. If this method returns S_OK, the value stored will be zero. Otherwise, a minidriver-specific error code will be stored at the location pointed to by this parameter.

#### - lFlags [in]

Is reserved. Set to zero.

#### - pWiasContext [in]

Pointer to a WIA item context.

#### - plDevErrVal [out]

Points to a memory location that will receive a status code for this method. If this method returns S_OK, the value stored will be zero. Otherwise, a minidriver-specific error code will be stored at the location pointed to by this parameter.

## -returns

On success, the method should return S_OK and clear the device error value pointed to by *plDevErrVal*. If the method fails, it should return a standard COM error code and place a minidriver-specific error code value in the memory pointed to by *plDevErrVal*.

The value pointed to by *plDevErrVal* can be converted to a string by calling [IWiaMiniDrv::drvGetDeviceErrorStr](./nf-wiamindr_lh-iwiaminidrv-drvgetdeviceerrorstr.md).

## -remarks

The **IWiaMiniDrv::drvInitItemProperties** method is called once per application for each item in the item tree.

## -see-also

[IWiaMiniDrv](./nn-wiamindr_lh-iwiaminidrv.md)

[IWiaMiniDrv::drvGetDeviceErrorStr](./nf-wiamindr_lh-iwiaminidrv-drvgetdeviceerrorstr.md)

[wiasGetDrvItem](../wiamdef/nf-wiamdef-wiasgetdrvitem.md)

[wiasSetItemPropAttribs](../wiamdef/nf-wiamdef-wiassetitempropattribs.md)

[wiasSetItemPropNames](../wiamdef/nf-wiamdef-wiassetitempropnames.md)

[wiasWriteMultiple](../wiamdef/nf-wiamdef-wiaswritemultiple.md)

