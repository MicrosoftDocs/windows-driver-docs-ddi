---
UID: NF:wiamindr_lh.IWiaMiniDrv.drvDeviceCommand
title: IWiaMiniDrv::drvDeviceCommand (wiamindr_lh.h)
description: The IWiaMiniDrv::drvDeviceCommand method issues a command to a WIA device.
old-location: image\iwiaminidrv_drvdevicecommand.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["IWiaMiniDrv::drvDeviceCommand"]
ms.keywords: IWiaMiniDrv interface [Imaging Devices],drvDeviceCommand method, IWiaMiniDrv.drvDeviceCommand, IWiaMiniDrv::drvDeviceCommand, MiniDrv_a65ceaef-73bf-4fd1-9d56-2a4b208f54a3.xml, drvDeviceCommand, drvDeviceCommand method [Imaging Devices], drvDeviceCommand method [Imaging Devices],IWiaMiniDrv interface, image.iwiaminidrv_drvdevicecommand, wiamindr_lh/IWiaMiniDrv::drvDeviceCommand
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
 - IWiaMiniDrv::drvDeviceCommand
 - wiamindr_lh/IWiaMiniDrv::drvDeviceCommand
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - wiamindr_lh.h
api_name:
 - IWiaMiniDrv.drvDeviceCommand
---

# IWiaMiniDrv::drvDeviceCommand


## -description

The **IWiaMiniDrv::drvDeviceCommand** method issues a command to a WIA device.

## -parameters

### -param __MIDL__IWiaMiniDrv0043

lFlags [in]

- Is currently unused.

### -param __MIDL__IWiaMiniDrv0044

pWiasContext [in]

- Pointer to a WIA item context.

### -param __MIDL__IWiaMiniDrv0045

plCommand [in]

- Points to a WIA command GUID.

### -param __MIDL__IWiaMiniDrv0046

plDevErrVal [out]

- Points to a memory location that will receive a status code for this method. If this method returns S_OK, the value stored will be zero. Otherwise, a minidriver-specific error code will be stored at the location pointed to by this parameter.

### -param __MIDL__IWiaMiniDrv0047

ppWiaDrvItem [out, optional]

- Points to a memory location that can receive a pointer to an [IWiaDrvItem Interface](./nn-wiamindr_lh-iwiadrvitem.md). See Remarks.

#### - lFlags [in]

Is currently unused.

#### - pWiasContext [in]

Pointer to a WIA item context.

#### - plCommand [in]

Points to a WIA command GUID.

#### - plDevErrVal [out]

Points to a memory location that will receive a status code for this method. If this method returns S_OK, the value stored will be zero. Otherwise, a minidriver-specific error code will be stored at the location pointed to by this parameter.

#### - ppWiaDrvItem [out, optional]

Points to a memory location that can receive a pointer to an [IWiaDrvItem Interface](./nn-wiamindr_lh-iwiadrvitem.md). See Remarks.

## -returns

On success, the method should return S_OK and clear the device error value pointed to by *plDevErrVal*. If the method fails, it should return a standard COM error code and place a minidriver-specific error code value in the memory pointed to by *plDevErrVal*.

The value pointed to by *plDevErrVal* can be converted to a string by calling [IWiaMiniDrv::drvGetDeviceErrorStr](./nf-wiamindr_lh-iwiaminidrv-drvgetdeviceerrorstr.md).

## -remarks

The method **IWiaMiniDrv::drvDeviceCommand** is called by the WIA service to issue a WIA service or application generated command to the device. The WIA service only calls the **IWiaMiniDrv::drvDeviceCommand **method for a command that the device can support in the method [IWiaMiniDrv::drvGetCapabilities](./nf-wiamindr_lh-iwiaminidrv-drvgetcapabilities.md).

The *ppWiaDrvItem* parameter should be considered to be optional, since the minidriver does not normally set the memory location it points to. For certain commands, however, the minidriver places the address of a newly created item in the location pointed to by this parameter. For example, if the command to take a picture is issued (*plCommand* is set to WIA_CMD_TAKE_PICTURE), the device produces a new image, causing the minidriver to create a new item in the driver item tree, and sets **ppWiaDrvItem* to the address of the new item. This informs the WIA service that a new item was created.

The minidriver may include a list of custom commands the device can support in the method [IWiaMiniDrv::drvGetCapabilities](./nf-wiamindr_lh-iwiaminidrv-drvgetcapabilities.md).

The WIA service does not write any properties before calling this method. If the command relies on property settings, the minidriver should call [IWiaMiniDrv::drvWriteItemProperties](./nf-wiamindr_lh-iwiaminidrv-drvwriteitemproperties.md) before issuing the command. For example, the command to take a picture, WIA_CMD_TAKE_PICTURE, might rely on shutter speed and aperture settings, which need to be written to the device before the command is issued.

## -see-also

[IWiaMiniDrv](./nn-wiamindr_lh-iwiaminidrv.md)

[IWiaMiniDrv::drvGetCapabilities](./nf-wiamindr_lh-iwiaminidrv-drvgetcapabilities.md)

[IWiaMiniDrv::drvWriteItemProperties](./nf-wiamindr_lh-iwiaminidrv-drvwriteitemproperties.md)
