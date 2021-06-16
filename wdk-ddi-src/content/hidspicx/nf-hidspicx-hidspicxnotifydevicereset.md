---
UID: NF:hidspicx.HidSpiCxNotifyDeviceReset
tech.root: hid
title: HidSpiCxNotifyDeviceReset
ms.date: 06/14/2021
targetos: Windows
description: 
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: hidspicx.h
req.idl: 
req.include-header: 
req.irql: DISPATCH_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: WIN10_NEXT
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - hidspicx.h
api_name:
 - HidSpiCxNotifyDeviceReset
f1_keywords:
 - HidSpiCxNotifyDeviceReset
 - hidspicx/HidSpiCxNotifyDeviceReset
dev_langs:
 - c++
---

## -description

Informs the class extension of a requirement to reset the device.

## -parameters

### -param Device

A handle to a framework device object the client driver obtained from a previous call to [WdfDeviceCreate](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

## -remarks

The client driver may call the **HidSpiCxNotifyDeviceReset** function at any time when the device is in, or transitioning to D0. The class extension then calls the [EVT_HIDSPICX_RESETDEVICE](nc-hidspicx-evt_hidspicx_resetdevice.md) callback for the device. The device is then reinitialized by the class extension.

## -see-also

[WdfDeviceCreate](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md)

[EVT_HIDSPICX_RESETDEVICE](nc-hidspicx-evt_hidspicx_resetdevice.md)
