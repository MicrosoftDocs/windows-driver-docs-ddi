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
 - 
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

The client driver may call the **HidSpiCxNotifyDeviceReset** function at any time when the device is in, or transitioning to D0, to inform the class extension of a requirement to reset the device. For example, due to an invalid packet, bus error or other unexpected failure in either the controller or the device necessitating a reset. The class extension will then call the provided EvtResetDevice callback, either before this function returns, or at a later time when appropriate. The device will then be reinitialized by the class extension.

## -parameters

### -param Device

WDF handle to the device object this method is being called for.

## -remarks

## -see-also
