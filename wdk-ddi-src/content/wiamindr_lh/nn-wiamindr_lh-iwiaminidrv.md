---
UID: NN:wiamindr_lh.IWiaMiniDrv
title: IWiaMiniDrv (wiamindr_lh.h)
description: The IWiaMiniDrv interface provides the methods that are the entry points for all communication between the minidriver and the WIA service. These methods allow the WIA service to control the device.
old-location: image\iwiaminidrv_interface.htm
tech.root: image
ms.assetid: 15068d10-5e24-427c-9684-24ce67b75ada
ms.date: 05/03/2018
ms.keywords: IWiaMiniDrv, IWiaMiniDrv interface [Imaging Devices], IWiaMiniDrv interface [Imaging Devices],described, MiniDrv_8a22bfee-13f8-4efc-b31d-8dd9fabfe131.xml, image.iwiaminidrv_interface, wiamindr_lh/IWiaMiniDrv
ms.topic: interface
f1_keywords:
 - "wiamindr_lh/IWiaMiniDrv"
req.header: wiamindr_lh.h
req.include-header: 
req.target-type: Windows
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
- IWiaMiniDrv
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWiaMiniDrv interface

## -description

The **IWiaMiniDrv** interface provides the methods that are the entry points for all communication between the minidriver and the WIA service. These methods allow the WIA service to control the device.

A WIA minidriver writer must implement each method in this interface, although the implementations are not required to do anything more than return E_NOTIMPL (for [IWiaMiniDrv::drvAnalyzeItem](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvanalyzeitem) and [IWiaMiniDrv::drvGetDeviceErrorStr](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvgetdeviceerrorstr)) or S_OK (for the other methods in this interface).

## -inheritance

## -members

The **IWiaMiniDrv** interface has these methods.

| Method | Description |
| --- | --- |
| [drvAcquireItemData](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvacquireitemdata) | The **IWiaMiniDrv::drvAcquireItemData** method is called by the WIA service to transfer data from the device to an application. |
| [drvAnalyzeItem](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvanalyzeitem) | The **IWiaMiniDrv::drvAnalyzeItem** method inspects an item, and creates subitems, if necessary. |
| [drvDeleteItem](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvdeleteitem) | The **IWiaMiniDrv::drvDeleteItem** method deletes the current driver item. |
| [drvDeviceCommand](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvdevicecommand) | The **IWiaMiniDrv::drvDeviceCommand** method issues a command to a WIA device. |
| [drvFreeDrvItemContext](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvfreedrvitemcontext) | The **IWiaMiniDrv::drvFreeDrvItemContext** method frees a device-specific context. |
| [drvGetCapabilities](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvgetcapabilities) | The **IWiaMiniDrv::drvGetCapabilities** method returns an array of events and commands that a device supports. |
| [drvGetDeviceErrorStr](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvgetdeviceerrorstr) | The **IWiaMiniDrv::drvGetDeviceErrorStr **method maps an error code to a Unicode string that describes the error. |
| [drvGetWiaFormatInfo](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvgetwiaformatinfo) | The **IWiaMiniDrv::drvGetWiaFormatInfo** method finds the image formats and media types that the WIA hardware device supports. |
| [drvInitializeWia](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvinitializewia) | The **IWiaMiniDrv::drvInitializeWia** method initializes the minidriver and builds the driver item tree representing the device. |
| [drvInitItemProperties](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvinititemproperties) | The **IWiaMiniDrv::drvInitItemProperties** method initializes WIA driver item properties for each item in an application item tree. |
| [drvLockWiaDevice](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvlockwiadevice) | The **IWiaMiniDrv::drvLockWiaDevice** method locks the WIA hardware device so that only the current minidriver can access it. |
| [drvNotifyPnpEvent](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvnotifypnpevent) | The **IWiaMiniDrv::drvNotifyPnpEvent** method responds to the event received from the WIA service. |
| [drvReadItemProperties](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvreaditemproperties) | The **IWiaMiniDrv::drvReadItemProperties** method reads the driver item properties that need to be updated. |
| [drvUnInitializeWia](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvuninitializewia) | The **IWiaMiniDrv::drvUnInitializeWia** method releases resources held by the minidriver. |
| [drvUnLockWiaDevice](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvunlockwiadevice) | The **IWiaMiniDrv::drvUnLockWiaDevice** method unlocks the WIA hardware device so that any minidriver can access it. |
| [drvValidateItemProperties](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvvalidateitemproperties) | The **IWiaMiniDrv::drvValidateItemProperties** method validates an item's properties against the set of valid values for each property and will update those properties if necessary. |
| [drvWriteItemProperties](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvwriteitemproperties) | The **IWiaMiniDrv::drvWriteItemProperties** method writes driver item properties to a WIA hardware device. |
