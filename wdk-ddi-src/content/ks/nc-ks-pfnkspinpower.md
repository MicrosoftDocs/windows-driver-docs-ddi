---
UID: NC:ks.PFNKSPINPOWER
title: PFNKSPINPOWER (ks.h)
description: An AVStream minidriver's AVStrMiniPinPower routine is called for pin-centric pins when the device is waking or entering a sleep state.
tech.root: stream
ms.date: 11/16/2022
keywords: ["PFNKSPINPOWER callback function"]
ms.keywords: AVStrMiniPinPower, AVStrMiniPinPower routine [Streaming Media Devices], PFNKSPINPOWER, avstclbk_fd047ae3-b574-4dad-a16b-2152193fb2cd.xml, ks/AVStrMiniPinPower, stream.avstrminipinpower
req.header: ks.h
req.include-header: Ks.h
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
 - PFNKSPINPOWER
 - ks/PFNKSPINPOWER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ks.h
api_name:
 - PFNKSPINPOWER
---

## -description

An AVStream minidriver's *AVStrMiniPinPower* routine is called for pin-centric pins when the device is waking or entering a sleep state.

## -parameters

### -param Pin [in]

Points to a pin-centric [**KSPIN**](./ns-ks-_kspin.md) structure for which to register the callback.

### -param State [in]

Specifies the device power state being requested. Set this parameter to one of the following **DEVICE_POWER_STATE** enumeration values: **PowerDeviceD0**, **PowerDeviceD1**, **PowerDeviceD2**, or **PowerDeviceD3**.

## -remarks

> [!WARNING]
> Do not attempt to obtain the filter control mutex from within either the Sleep or Wake callback. Doing so induces a risk of deadlock. For more information about mutexes, see [Mutexes in AVStream](/windows-hardware/drivers/stream/mutexes-in-avstream).

The minidriver specifies an address for routines of this type in the *Sleep* and/or *Wake* parameters of the [KsPinRegisterPowerCallbacks](./nf-ks-kspinregisterpowercallbacks.md) routine.

## -see-also

[KsFilterRegisterPowerCallbacks](./nf-ks-ksfilterregisterpowercallbacks.md)

[KsPinRegisterPowerCallbacks](./nf-ks-kspinregisterpowercallbacks.md)