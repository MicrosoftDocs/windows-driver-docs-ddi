---
UID: NF:wiamindr_lh.IWiaMiniDrv.drvUnLockWiaDevice
title: IWiaMiniDrv::drvUnLockWiaDevice (wiamindr_lh.h)
description: The IWiaMiniDrv::drvUnLockWiaDevice method unlocks the WIA hardware device so that any minidriver can access it.
old-location: image\iwiaminidrv_drvunlockwiadevice.htm
tech.root: image
ms.assetid: 134d224a-d472-4d74-be3e-069dbb46a65c
ms.date: 05/03/2018
keywords: ["IWiaMiniDrv::drvUnLockWiaDevice"]
ms.keywords: IWiaMiniDrv interface [Imaging Devices],drvUnLockWiaDevice method, IWiaMiniDrv.drvUnLockWiaDevice, IWiaMiniDrv::drvUnLockWiaDevice, MiniDrv_596d3499-1e4a-4147-838f-db4f56f30716.xml, drvUnLockWiaDevice, drvUnLockWiaDevice method [Imaging Devices], drvUnLockWiaDevice method [Imaging Devices],IWiaMiniDrv interface, image.iwiaminidrv_drvunlockwiadevice, wiamindr_lh/IWiaMiniDrv::drvUnLockWiaDevice
f1_keywords:
 - "wiamindr_lh/IWiaMiniDrv.drvUnLockWiaDevice"
 - "IWiaMiniDrv.drvUnLockWiaDevice"
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
- IWiaMiniDrv.drvUnLockWiaDevice
targetos: Windows
req.typenames: 
---

# IWiaMiniDrv::drvUnLockWiaDevice

## -description

The **IWiaMiniDrv::drvUnLockWiaDevice** method unlocks the WIA hardware device so that any minidriver can access it.

## -parameters

### -param __MIDL__IWiaMiniDrv0033

lFlags [in]

- Is currently unused.

### -param __MIDL__IWiaMiniDrv0034

pWiasContext [in]

- Pointer to a WIA item context.

### -param __MIDL__IWiaMiniDrv0035

plDevErrVal [out]

- Points to a memory location that will receive a status code for this method. If this method returns S_OK, the value stored will be zero. Otherwise, a minidriver-specific error code will be stored at the location pointed to by this parameter.

#### - lFlags [in]

Is currently unused.

#### - pWiasContext [in]

Pointer to a WIA item context.

#### - plDevErrVal [out]

Points to a memory location that will receive a status code for this method. If this method returns S_OK, the value stored will be zero. Otherwise, a minidriver-specific error code will be stored at the location pointed to by this parameter.

## -returns

On success, the method should return S_OK and clear the device error value pointed to by *plDevErrVal*. If the method fails, it should return a standard COM error code and place a minidriver-specific error code value in the memory pointed to by *plDevErrVal*.

The value pointed to by *plDevErrVal* can be converted to a string by calling [IWiaMiniDrv::drvGetDeviceErrorStr](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvgetdeviceerrorstr).

## -remarks

The method **IWiaMiniDrv::drvUnLockWiaDevice** is used to allow access to the device after the lock is no longer needed. It is typically called by the WIA service after properties are written to the device or after a data transfer.

The minidriver's implementation of the **IWiaMiniDrv::drvUnLockWiaDevice** method should use the STI unlock device method [IStiDevice::UnLockDevice](https://docs.microsoft.com/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-unlockdevice).

## -see-also

[IWiaMiniDrv](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nn-wiamindr_lh-iwiaminidrv)

[IWiaMiniDrv::drvGetDeviceErrorStr](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvgetdeviceerrorstr)

[IWiaMiniDrv::drvLockWiaDevice](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvlockwiadevice)
