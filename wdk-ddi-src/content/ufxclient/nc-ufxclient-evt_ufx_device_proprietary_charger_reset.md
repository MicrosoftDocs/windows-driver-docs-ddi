---
UID: NC:ufxclient.EVT_UFX_DEVICE_PROPRIETARY_CHARGER_RESET
title: EVT_UFX_DEVICE_PROPRIETARY_CHARGER_RESET (ufxclient.h)
description: The client driver's implementation to resets proprietary charger.
old-location: buses\evt_ufx_device_proprietary_charger_reset.htm
tech.root: usbref
ms.date: 01/19/2022
keywords: ["EVT_UFX_DEVICE_PROPRIETARY_CHARGER_RESET callback function"]
ms.keywords: EVT_UFX_DEVICE_PROPRIETARY_CHARGER_RESET, EVT_UFX_DEVICE_PROPRIETARY_CHARGER_RESET callback, EvtUfxDeviceProprietaryChargerReset, EvtUfxDeviceProprietaryChargerReset callback function [Buses], PFN_UFX_DEVICE_PROPRIETARY_CHARGER_RESET, PFN_UFX_DEVICE_PROPRIETARY_CHARGER_RESET callback function pointer [Buses], buses.evt_ufx_device_proprietary_charger_reset, ufxclient/EvtUfxDeviceProprietaryChargerReset
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_UFX_DEVICE_PROPRIETARY_CHARGER_RESET
 - ufxclient/EVT_UFX_DEVICE_PROPRIETARY_CHARGER_RESET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ufxclient.h
api_name:
 - EVT_UFX_DEVICE_PROPRIETARY_CHARGER_RESET
---

# EVT_UFX_DEVICE_PROPRIETARY_CHARGER_RESET callback function

## -description

The client driver's implementation to resets proprietary charger.

## -parameters

### -param unnamedParam1 [in]

The handle to a USB device object that the client driver received in a previous call to the [UfxDeviceCreate](nf-ufxclient-ufxdevicecreate.md) method.

## -remarks

*EVT_UFX_DEVICE_PROPRIETARY_CHARGER_RESET* is an optional event callback.

The USB function class extension (UFX) invokes this event callback to indicate that the USB device has been detached from the charger. The client driver initiates a request to the lower filter driver to reset the proprietary charger its initial state.

## -see-also

- [UfxDeviceCreate](nf-ufxclient-ufxdevicecreate.md)
- [UfxDeviceProprietaryChargerDetectComplete](nf-ufxclient-ufxdeviceproprietarychargerdetectcomplete.md)
