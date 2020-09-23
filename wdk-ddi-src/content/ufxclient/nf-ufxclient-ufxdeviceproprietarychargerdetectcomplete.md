---
UID: NF:ufxclient.UfxDeviceProprietaryChargerDetectComplete
title: UfxDeviceProprietaryChargerDetectComplete function (ufxclient.h)
description: Notifies UFX about a detected proprietary port/charger type.
old-location: buses\ufxdeviceproprietarychargerdetectcomplete.htm
tech.root: usbref
ms.assetid: 5E85D80B-4C0F-4C91-A1B5-565E09FD3743
ms.date: 05/07/2018
keywords: ["UfxDeviceProprietaryChargerDetectComplete function"]
ms.keywords: UfxDeviceProprietaryChargerDetectComplete, UfxDeviceProprietaryChargerDetectComplete method [Buses], buses.ufxdeviceproprietarychargerdetectcomplete, ufxclient/UfxDeviceProprietaryChargerDetectComplete
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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
req.lib: ufxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - UfxDeviceProprietaryChargerDetectComplete
 - ufxclient/UfxDeviceProprietaryChargerDetectComplete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ufxclient.h
api_name:
 - UfxDeviceProprietaryChargerDetectComplete
---

# UfxDeviceProprietaryChargerDetectComplete function


## -description

Notifies UFX about a detected proprietary port/charger type.

## -parameters

### -param UfxDevice 

[in]
A handle to a UFX device object that the driver created by calling <a href="/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdevicecreate">UfxDeviceCreate</a>.

### -param DetectedCharger 

[in]
A  pointer to a <a href="/windows-hardware/drivers/ddi/ufxproprietarycharger/ns-ufxproprietarycharger-_ufx_proprietary_charger">UFX_PROPRIETARY_CHARGER</a> structure.

## -remarks

The client driver calls <b>UfxDeviceProprietaryChargerDetectComplete</b> after attempting to detect a proprietary charger on the upstream port, typically from within its <a href="/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function.

  Do not call <b>UfxDeviceProprietaryChargerDetectComplete</b>  before UFX calls the client driver's <a href="/windows-hardware/drivers/ddi/ufxclient/nc-ufxclient-evt_ufx_device_proprietary_charger_detect">EVT_UFX_DEVICE_DETECT_PROPRIETARY_CHARGER</a> callback function.

The following snippet shows how a client driver calls <b>UfxDeviceProprietaryChargerDetectComplete</b>:


```
    UfxDeviceProprietaryChargerDetectComplete(
        ChargerContext->UfxDevice,
        &pControllerData->DetectedCharger);

```