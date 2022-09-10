---
UID: NS:iddcx.IDDCX_ENDPOINT_DIAGNOSTIC_INFO
title: IDDCX_ENDPOINT_DIAGNOSTIC_INFO (iddcx.h)
description: Gives information about the video data endpoint.
old-location: display\iddcx_endpoint_diagnostic_info.htm
tech.root: display
ms.date: 08/08/2022
keywords: ["IDDCX_ENDPOINT_DIAGNOSTIC_INFO structure"]
ms.keywords: IDDCX_ENDPOINT_DIAGNOSTIC_INFO, IDDCX_ENDPOINT_DIAGNOSTIC_INFO structure [Display Devices], display.iddcx_endpoint_diagnostic_info, iddcx/IDDCX_ENDPOINT_DIAGNOSTIC_INFO
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
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
 - IDDCX_ENDPOINT_DIAGNOSTIC_INFO
 - iddcx/IDDCX_ENDPOINT_DIAGNOSTIC_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDDCX_ENDPOINT_DIAGNOSTIC_INFO
---

# IDDCX_ENDPOINT_DIAGNOSTIC_INFO structure

## -description

The **IDDCX_ENDPOINT_DIAGNOSTIC_INFO** provides information about the video data endpoint.

## -struct-fields

### -field Size

Total size of this structure, in bytes.

### -field TransmissionType

A [**IDDCX_TRANSMISSION_TYPE**](ne-iddcx-iddcx_transmission_type.md) value that describes the type of link the video data is being transmitted over.

### -field pEndPointFriendlyName

Pointer to a string with the friendly name of the endpoint, if one exists. This is applicable if the user can give the device a name and is NULL if a friendly name does not exist.

### -field pEndPointModelName

Pointer to a string with the model name of the endpoint. Must be a non-empty string.

### -field pEndPointManufacturerName

Pointer to a string with the manufacturer name of the endpoint. Must be a non-empty string.

### -field pHardwareVersion

Pointer to a [**IDDCX_ENDPOINT_VERSION**](ns-iddcx-iddcx_endpoint_version.md) structure that contains the version info for the endpoint hardware.

### -field pFirmwareVersion

Pointer to a [**IDDCX_ENDPOINT_VERSION**](ns-iddcx-iddcx_endpoint_version.md) structure that contains the version info for the endpoint firmware.

### -field GammaSupport

 A [**IDDCX_FEATURE_IMPLEMENTATION**](ne-iddcx-iddcx_feature_implementation.md) value that indicates how gamma is implemented.

## -see-also

[**IDDCX_ADAPTER_CAPS**](ns-iddcx-iddcx_adapter_caps.md)

[**IDDCX_ENDPOINT_VERSION**](ns-iddcx-iddcx_endpoint_version.md)

[**IDDCX_FEATURE_IMPLEMENTATION**](ne-iddcx-iddcx_feature_implementation.md)

[**IDDCX_TRANSMISSION_TYPE**](ne-iddcx-iddcx_transmission_type.md)
