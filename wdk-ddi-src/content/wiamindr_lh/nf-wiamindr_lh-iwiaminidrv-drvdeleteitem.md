---
UID: NF:wiamindr_lh.IWiaMiniDrv.drvDeleteItem
title: IWiaMiniDrv::drvDeleteItem (wiamindr_lh.h)
description: The IWiaMiniDrv::drvDeleteItem method deletes the current driver item.
old-location: image\iwiaminidrv_drvdeleteitem.htm
tech.root: image
ms.assetid: 616a0edd-d769-411d-bc94-57ba18a00c4d
ms.date: 05/03/2018
ms.keywords: IWiaMiniDrv interface [Imaging Devices],drvDeleteItem method, IWiaMiniDrv.drvDeleteItem, IWiaMiniDrv::drvDeleteItem, MiniDrv_7e3949ae-f170-4ccc-a139-fecaf2e97e41.xml, drvDeleteItem, drvDeleteItem method [Imaging Devices], drvDeleteItem method [Imaging Devices],IWiaMiniDrv interface, image.iwiaminidrv_drvdeleteitem, wiamindr_lh/IWiaMiniDrv::drvDeleteItem
ms.topic: method
f1_keywords:
 - "wiamindr_lh/IWiaMiniDrv.drvDeleteItem"
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
- IWiaMiniDrv.drvDeleteItem
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWiaMiniDrv::drvDeleteItem

## -description

The **IWiaMiniDrv::drvDeleteItem** method deletes the current driver item.

## -parameters

### -param __MIDL__IWiaMiniDrv0053

lFlags [in]

- Is currently unused.

### -param __MIDL__IWiaMiniDrv0054

pWiasContext [in]

- Pointer to a WIA item context.

### -param __MIDL__IWiaMiniDrv0055

plDevErrVal [out]

- Points to a memory location that will receive a status code for this method. If this method returns S_OK, the value stored will be zero. Otherwise, a minidriver-specific error code will be stored at the location pointed to by this parameter.

#### - lFlags [in]

Is currently unused.

#### - pWiasContext [in]

Pointer to a WIA item context.

#### - plDevErrVal [out]

Points to a memory location that will receive a status code for this method. If this method returns S_OK, the value stored will be zero. Otherwise, a minidriver-specific error code will be stored at the location pointed to by this parameter.

## -returns

On success, the method should return S_OK and clear the device error value pointed to by *plDevErrVal*. If the method fails, it should return a standard COM error code and place a minidriver-specific error code value in the memory pointed to by *plDevErrVal*. The value pointed to by *plDevErrVal* can be converted to a string by calling [IWiaMiniDrv::drvGetDeviceErrorStr](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvgetdeviceerrorstr).

## -remarks

In order to delete a driver item, the WIA service will call the minidriver method **IWiaMiniDrv::drvDeleteItem**. In this method, the minidriver will attempt to delete the item pointed to by the WIA service context parameter *pWiasContext*. If the item is successfully deleted, the method returns S_OK and sets the device error value parameter *plDevErrVal* to zero. If a device error occurs, the method returns E_FAIL and a device-specific error value in the device error value parameter *plDevErrVal*.

Before the WIA service calls this method, it verifies the following:

- The item is not the root item.

- If the item is a folder, it does not have any children.

- The item's access rights allow deletion.

Since the WIA service verifies these conditions, it is not necessary for the minidriver to also verify them.

## -see-also

[IWiaMiniDrv](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nn-wiamindr_lh-iwiaminidrv)

[IWiaMiniDrv::drvGetDeviceErrorStr](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvgetdeviceerrorstr)
