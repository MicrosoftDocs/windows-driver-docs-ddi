---
UID: NF:wiamindr_lh.IWiaMiniDrv.drvLockWiaDevice
title: IWiaMiniDrv::drvLockWiaDevice (wiamindr_lh.h)
description: The IWiaMiniDrv::drvLockWiaDevice method locks the WIA hardware device so that only the current minidriver can access it.
old-location: image\iwiaminidrv_drvlockwiadevice.htm
tech.root: image
ms.assetid: 674e0a65-1763-41b0-896b-2ef9debc32a5
ms.date: 05/03/2018
ms.keywords: IWiaMiniDrv interface [Imaging Devices],drvLockWiaDevice method, IWiaMiniDrv.drvLockWiaDevice, IWiaMiniDrv::drvLockWiaDevice, MiniDrv_5ae2a5c5-524c-46ce-8ae4-d8edd5d76fcc.xml, drvLockWiaDevice, drvLockWiaDevice method [Imaging Devices], drvLockWiaDevice method [Imaging Devices],IWiaMiniDrv interface, image.iwiaminidrv_drvlockwiadevice, wiamindr_lh/IWiaMiniDrv::drvLockWiaDevice
f1_keywords:
 - "wiamindr_lh/IWiaMiniDrv.drvLockWiaDevice"
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
- IWiaMiniDrv.drvLockWiaDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWiaMiniDrv::drvLockWiaDevice

## -description

The **IWiaMiniDrv::drvLockWiaDevice** method locks the WIA hardware device so that only the current minidriver can access it.

## -parameters

### -param __MIDL__IWiaMiniDrv0030

lFlags [in]

- Is currently unused.

### -param __MIDL__IWiaMiniDrv0031

pWiasContext [in]

- Pointer to a WIA item context.

### -param __MIDL__IWiaMiniDrv0032

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

The **IWiaMiniDrv::drvLockWiaDevice** method is used to lock access to the device. This is typically done before properties are written to the device or before a data transfer. The **IWiaMiniDrv::drvLockWiaDevice** method should be implemented using the **IStiDevice** interface's lock device method, [IStiDevice::LockDevice](https://docs.microsoft.com/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-lockdevice).

## -see-also

[IWiaMiniDrv](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nn-wiamindr_lh-iwiaminidrv)

[IWiaMiniDrv::drvGetDeviceErrorStr](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvgetdeviceerrorstr)

[IWiaMiniDrv::drvUnLockWiaDevice](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvunlockwiadevice)
