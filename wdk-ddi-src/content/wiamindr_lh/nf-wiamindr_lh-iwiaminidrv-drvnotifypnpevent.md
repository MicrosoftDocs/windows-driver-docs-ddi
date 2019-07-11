---
UID: NF:wiamindr_lh.IWiaMiniDrv.drvNotifyPnpEvent
title: IWiaMiniDrv::drvNotifyPnpEvent (wiamindr_lh.h)
description: The IWiaMiniDrv::drvNotifyPnpEvent method responds to the event received from the WIA service.
old-location: image\iwiaminidrv_drvnotifypnpevent.htm
tech.root: image
ms.assetid: 55d6d93b-c20f-435b-ba99-2df26bd17240
ms.date: 05/03/2018
ms.keywords: IWiaMiniDrv interface [Imaging Devices],drvNotifyPnpEvent method, IWiaMiniDrv.drvNotifyPnpEvent, IWiaMiniDrv::drvNotifyPnpEvent, MiniDrv_7684a7e5-7ca5-4d20-a1a8-fc38400815ce.xml, drvNotifyPnpEvent, drvNotifyPnpEvent method [Imaging Devices], drvNotifyPnpEvent method [Imaging Devices],IWiaMiniDrv interface, image.iwiaminidrv_drvnotifypnpevent, wiamindr_lh/IWiaMiniDrv::drvNotifyPnpEvent
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
- IWiaMiniDrv.drvNotifyPnpEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWiaMiniDrv::drvNotifyPnpEvent

## -description

The **IWiaMiniDrv::drvNotifyPnpEvent** method responds to the event received from the WIA service.

## -parameters

### -param pEventGUID

### -param bstrDeviceID [in]

Specifies a string containing the device's unique identifier.

### -param ulReserved [in]

Is reserved for system use.

#### - pEventGuid [in]

Points to a GUID identifying the event.

## -returns

On success, the method should return S_OK. If the method fails, it should return a standard COM error code.

## -remarks

The WIA service notifies a WIA minidriver of a supported device event by calling the **IWiaMiniDrv::drvNotifyPnpEvent** method. In this method the minidriver implements the device-specific functionality needed to respond to the event.

If this method is called with **pEventGuid* set to [WIA_EVENT_CANCEL_IO](https://docs.microsoft.com/windows/win32/wia/-wia-wia-event-identifiers) device event, it should cancel all current I/O operations as soon as possible.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nn-wiamindr_lh-iwiaminidrv">IWiaMiniDrv</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvgetcapabilities">IWiaMiniDrv::drvGetCapabilities</a>
