---
UID: NF:ks.KsPinRegisterPowerCallbacks
title: KsPinRegisterPowerCallbacks function (ks.h)
description: The KsPinRegisterPowerCallbacks function registers power management callbacks for Pin.
tech.root: stream
ms.date: 11/16/2022
keywords: ["KsPinRegisterPowerCallbacks function"]
ms.keywords: KsPinRegisterPowerCallbacks, KsPinRegisterPowerCallbacks function [Streaming Media Devices], avfunc_2e133cdb-6afa-47a7-8d3b-8293b63428b5.xml, ks/KsPinRegisterPowerCallbacks, stream.kspinregisterpowercallbacks
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.lib: Ks.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - KsPinRegisterPowerCallbacks
 - ks/KsPinRegisterPowerCallbacks
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsPinRegisterPowerCallbacks
---

## -description

The KsPinRegisterPowerCallbacks function registers power management callbacks for *Pin*.

## -parameters

### -param Pin [in]

A pointer to the [**KSPIN**](/windows-hardware/drivers/ddi/ks/ns-ks-_kspin) structure for which to register power callbacks. Note that the pin must actually process (be pin-centric) in order to receive power notification messages.

### -param Sleep [in, optional]

This parameter supplies the address of a [AVStrMiniPinPower](/windows-hardware/drivers/ddi/ks/nc-ks-pfnkspinpower)  function that handles sleep requests for the device. Optional.

### -param Wake [in, optional]

This parameter supplies the address of a [AVStrMiniPinPower](/windows-hardware/drivers/ddi/ks/nc-ks-pfnkspinpower)  function that handles wake requests for the device. Optional.

## -remarks

> [!WARNING]
> Do not attempt to obtain the filter control mutex from within either the Sleep or Wake callback, or deadlock may occur. For more information about mutexes, read [Mutexes in AVStream](/windows-hardware/drivers/stream/mutexes-in-avstream).

At least one of the callbacks must be specified when calling KsPinRegisterPowerCallbacks.

## -see-also

[AVStrMiniPinPower](/windows-hardware/drivers/ddi/ks/nc-ks-pfnkspinpower)

[KsFilterRegisterPowerCallbacks](/windows-hardware/drivers/ddi/ks/nf-ks-ksfilterregisterpowercallbacks)
