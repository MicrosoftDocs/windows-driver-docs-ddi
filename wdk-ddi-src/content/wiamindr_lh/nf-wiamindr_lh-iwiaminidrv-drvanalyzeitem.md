---
UID: NF:wiamindr_lh.IWiaMiniDrv.drvAnalyzeItem
title: IWiaMiniDrv::drvAnalyzeItem (wiamindr_lh.h)
description: The IWiaMiniDrv::drvAnalyzeItem method inspects an item, and creates subitems, if necessary.
old-location: image\iwiaminidrv_drvanalyzeitem.htm
tech.root: image
ms.assetid: e742f898-e663-431d-870e-bb0fe7e89b5a
ms.date: 05/03/2018
ms.keywords: IWiaMiniDrv interface [Imaging Devices],drvAnalyzeItem method, IWiaMiniDrv.drvAnalyzeItem, IWiaMiniDrv::drvAnalyzeItem, MiniDrv_dfa93eeb-ea39-44b6-b465-5bff0f056763.xml, drvAnalyzeItem, drvAnalyzeItem method [Imaging Devices], drvAnalyzeItem method [Imaging Devices],IWiaMiniDrv interface, image.iwiaminidrv_drvanalyzeitem, wiamindr_lh/IWiaMiniDrv::drvAnalyzeItem
f1_keywords:
 - "wiamindr_lh/IWiaMiniDrv.drvAnalyzeItem"
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
- IWiaMiniDrv.drvAnalyzeItem
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWiaMiniDrv::drvAnalyzeItem

## -description

The **IWiaMiniDrv::drvAnalyzeItem** method inspects an item, and creates subitems, if necessary.

## -parameters

### -param __MIDL__IWiaMiniDrv0036

lFlags [in]

- Is currently unused.

### -param __MIDL__IWiaMiniDrv0037

pWiasContext [in]

- Pointer to a WIA item context.

### -param __MIDL__IWiaMiniDrv0038

plDevErrVal [in]

- Points to a memory location that will receive a status code for this method. If this method returns S_OK, the value stored will be zero. Otherwise, a minidriver-specific error code will be stored at the location pointed to by this parameter.

#### - lFlags [in]

Is currently unused.

#### - pWiasContext [in]

Pointer to a WIA item context.

#### - plDevErrVal [in]

Points to a memory location that will receive a status code for this method. If this method returns S_OK, the value stored will be zero. Otherwise, a minidriver-specific error code will be stored at the location pointed to by this parameter.

## -returns

On success, the method should return S_OK and clear the device error value pointed to by *plDevErrVal*. If the method is not fully implemented, it can return E_NOTIMPL. If the method fails, it should return a standard COM error code and place a minidriver-specific error code value in the memory pointed to by *plDevErrVal*.

The value pointed to by *plDevErrVal* can be converted to a string by calling [IWiaMiniDrv::drvGetDeviceErrorStr](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvgetdeviceerrorstr).

## -see-also

[IWiaMiniDrv](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nn-wiamindr_lh-iwiaminidrv)

[IWiaMiniDrv::drvGetDeviceErrorStr](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvgetdeviceerrorstr)
