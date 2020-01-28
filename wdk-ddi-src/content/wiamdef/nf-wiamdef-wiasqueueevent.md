---
UID: NF:wiamdef.wiasQueueEvent
title: wiasQueueEvent function (wiamdef.h)
description: The wiasQueueEvent function informs the service that the device generated an event.
old-location: image\wiasqueueevent.htm
tech.root: image
ms.assetid: 1ea82b64-e0e0-445b-8200-70cd6920d29b
ms.date: 05/03/2018
ms.keywords: image.wiasqueueevent, wiamdef/wiasQueueEvent, wiasFncs_a853cdf1-8d80-4bb6-9c41-c7190e9e9202.xml, wiasQueueEvent, wiasQueueEvent function [Imaging Devices]
f1_keywords:
 - "wiamdef/wiasQueueEvent"
req.header: wiamdef.h
req.include-header: Wiamdef.h
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
req.lib: Wiaservc.lib
req.dll: Wiaservc.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Wiaservc.dll
api_name:
- wiasQueueEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# wiasQueueEvent function

## -description

The **wiasQueueEvent** function informs the service that the device generated an event.

## -parameters

### -param bstrDeviceId [in]

Specifies the device ID. This is the value passed to the minidriver in the call to the [IWiaMiniDrv::drvInitializeWia](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvinitializewia) method.

### -param pEventGUID [in]

Pointer to a buffer that contains the GUID for the event.

### -param bstrFullItemName [in, optional]

Specifies the full item name, including path information.

## -returns

On success, the function returns S_OK.

If the function fails, it returns a standard COM error or one of the [WIA error codes](https://docs.microsoft.com/windows/win32/wia/-wia-error-codes).

## -remarks

This method should be used whenever the device must signal that an event of some type occurred. The device does this by placing the event on the event queue. For example, when a camera takes a new picture, it should generate a WIA_EVENT_ITEM_CREATED event after adding a new driver item to its tree. The camera can place this event on the event queue in this way:

```cpp
hr = wiasQueueEvent(bstrMyDeviceId,
                    &WIA_EVENT_ITEM_CREATED,
                    bstrDescriptionString);
```

See the Windows SDK documentation for a complete list of WIA event identifiers.

## -see-also

[IWiaMiniDrv::drvInitializeWia](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvinitializewia)
