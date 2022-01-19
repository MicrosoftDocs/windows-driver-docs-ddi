---
UID: NC:ufxclient.EVT_UFX_DEVICE_PROPRIETARY_CHARGER_DETECT
title: EVT_UFX_DEVICE_PROPRIETARY_CHARGER_DETECT (ufxclient.h)
description: The client driver's implementation to initiate proprietary charger detection.
old-location: buses\evt_ufx_device_detect_proprietary_charger.htm
tech.root: usbref
ms.date: 01/18/2022
keywords: ["EVT_UFX_DEVICE_PROPRIETARY_CHARGER_DETECT callback function"]
ms.keywords: EVT_UFX_DEVICE_DETECT_PROPRIETARY_CHARGER, EVT_UFX_DEVICE_PROPRIETARY_CHARGER_DETECT, EVT_UFX_DEVICE_PROPRIETARY_CHARGER_DETECT callback, EvtDeviceProprietaryChargerDetect, EvtUfxDeviceDetectProprietaryCharger, EvtUfxDeviceDetectProprietaryCharger callback function [Buses], PFN_UFX_DEVICE_PROPRIETARY_CHARGER_DETECT, PFN_UFX_DEVICE_PROPRIETARY_CHARGER_DETECT callback function pointer [Buses], buses.evt_ufx_device_detect_proprietary_charger, ufxclient/EvtUfxDeviceDetectProprietaryCharger
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
 - EVT_UFX_DEVICE_PROPRIETARY_CHARGER_DETECT
 - ufxclient/EVT_UFX_DEVICE_PROPRIETARY_CHARGER_DETECT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ufxclient.h
api_name:
 - EVT_UFX_DEVICE_PROPRIETARY_CHARGER_DETECT
---

# EVT_UFX_DEVICE_PROPRIETARY_CHARGER_DETECT callback function

## -description

The client driver's implementation to initiate proprietary charger detection.

## -parameters

### -param unnamedParam1 [in]

The handle to a USB device object that the client driver received in a previous call to the [UfxDeviceCreate](nf-ufxclient-ufxdevicecreate.md) method.

## -remarks

*EVT_UFX_DEVICE_DETECT_PROPRIETARY_CHARGER* is an optional event callback. The client driver is required to implement this event callback only if it supports proprietary charger detection. The driver indicates support in the [UfxDeviceCreate](nf-ufxclient-ufxdevicecreate.md) call by setting **PdcpSupported** to TRUE in [UFX_DEVICE_CAPABILITIES](../ufxbase/ns-ufxbase-_ufx_device_capabilities.md). If the client driver does not support the functionality, the **EvtDeviceProprietaryChargerDetect**, **EvtDeviceProprietaryChargerSetProperty**, and **EvtDeviceProprietaryChargerReset**
members of the [UFX_DEVICE_CALLBACKS](ns-ufxclient-_ufx_device_callbacks.md) structure must be set to NULL in **UfxDeviceCreate**.

The client driver indicates completion of this event by calling the [UfxDeviceProprietaryChargerDetectComplete](nf-ufxclient-ufxdeviceproprietarychargerdetectcomplete.md) method.

The client driver sends a request to the lower filter driver to determine if a proprietary charger is present. In response, the filter driver provides a GUID for each charger type it supports, and a list of that charger's properties. If a specific charger is configurable, the filter driver also provides a list of supported PropertyIDs and their possible values to configure the charger.

## -see-also

- [UfxDeviceCreate](nf-ufxclient-ufxdevicecreate.md)
- [UfxDeviceProprietaryChargerDetectComplete](nf-ufxclient-ufxdeviceproprietarychargerdetectcomplete.md)
