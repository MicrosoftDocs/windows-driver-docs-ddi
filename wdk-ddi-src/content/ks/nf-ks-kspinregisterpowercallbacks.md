---
UID: NF:ks.KsPinRegisterPowerCallbacks
title: KsPinRegisterPowerCallbacks function (ks.h)
description: The KsPinRegisterPowerCallbacks function registers power management callbacks for Pin.
old-location: stream\kspinregisterpowercallbacks.htm
tech.root: stream
ms.assetid: e498a907-8d20-4d00-9411-8e82030af223
ms.date: 04/23/2018
keywords: ["KsPinRegisterPowerCallbacks function"]
ms.keywords: KsPinRegisterPowerCallbacks, KsPinRegisterPowerCallbacks function [Streaming Media Devices], avfunc_2e133cdb-6afa-47a7-8d3b-8293b63428b5.xml, ks/KsPinRegisterPowerCallbacks, stream.kspinregisterpowercallbacks
f1_keywords:
 - "ks/KsPinRegisterPowerCallbacks"
 - "KsPinRegisterPowerCallbacks"
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
targetos: Windows
req.typenames: 
---

# KsPinRegisterPowerCallbacks function


## -description


The<b> KsPinRegisterPowerCallbacks </b>function registers power management callbacks for <i>Pin</i>.


## -parameters




### -param Pin [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a> structure for which to register power callbacks. Note that the pin must actually process (be pin-centric) in order to receive power notification messages.


### -param Sleep [in, optional]

This parameter supplies the address of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnkspinpower">AVStrMiniPinPower</a>  function that handles sleep requests for the device. Optional.


### -param Wake [in, optional]

This parameter supplies the address of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnkspinpower">AVStrMiniPinPower</a>  function that handles wake requests for the device. Optional.


## -remarks



<div class="alert"><b>Warning</b>  <i>Do not attempt to obtain the filter control mutex</i> from within either the Sleep or Wake callback, or deadlock may occur. For more information about mutexes, read <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/mutexes-in-avstream">Mutexes in AVStream</a>.</div>
<div> </div>
At least one of the callbacks must be specified when calling <b>KsPinRegisterPowerCallbacks</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnkspinpower">AVStrMiniPinPower</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfilterregisterpowercallbacks">KsFilterRegisterPowerCallbacks</a>
 

 

