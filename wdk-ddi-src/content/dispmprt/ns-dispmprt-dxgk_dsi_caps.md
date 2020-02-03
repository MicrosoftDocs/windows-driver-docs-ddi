---
UID: NS:dispmprt._DXGK_DSI_CAPS
title: DXGK_DSI_CAPS
ms.date: 01/30/2020
ms.topic: language-reference
targetos: Windows
description: The DXGK_DSI_CAPS structure is used to identify the MIPI Display Serial Interface (DSI) capabilities of a device.
tech.root: display
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: dispmprt.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: The next version of Windows 10
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGK_DSI_CAPS, *PDXGK_DSI_CAPS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGK_DSI_CAPS
 - DXGK_DSI_CAPS
f1_keywords:
 - dispmprt/_DXGK_DSI_CAPS
 - dispmprt/DXGK_DSI_CAPS
dev_langs:
 - c++
---

# DXGK_DSI_CAPS structure

## -description

The DXGK_DSI_CAPS structure is used to identify the MIPI Display Serial Interface (DSI) capabilities of a device.

## -struct-fields

### -field DSITypeMajor

The major number of the version of the DSI standard supported by this target (e.g. 2,0 for DSI 2, or 1,0 for DSI 1).

### -field DSITypeMinor

The minor number of the version of the DSI standard supported by this target (e.g. 2,0 for DSI 2, or 1,0 for DSI 1). Currently DSI does not have minor versions for the high-level type, but the `DSITypeMinor` is kept for future-proofing.

### -field SpecVersionMajor

The major number of the spec version of the DSI standard supported by this target (e.g. 1,3,1 for spec version 1.3.1).

### -field SpecVersionMinor

The minor number of the spec version of the DSI standard supported by this target (e.g. 1,3,1 for spec version 1.3.1).

### -field SpecVersionPatch

The patch number of the spec version of the DSI standard supported by this target (e.g. 1,3,1 for spec version 1.3.1).

### -field TargetMaximumReturnPacketSize

The maximum packet size that the OEM panel driver can request in a transmission for a long read.  The graphics driver controls the size conveyed to the peripheral based on its own needs so may need to change the size for an OEM panel transmission however the graphics driver may have a maximum size it can support.

### -field ResultCodeFlags

### -field ResultCodeStatus

### -field Revision

### -field Level

### -field DeviceClassHi

### -field DeviceClassLo

### -field ManufacturerHi

### -field ManufacturerLo

### -field ProductHi

### -field ProductLo

### -field LengthHi

### -field LengthLo

## -remarks

The remaining fields are the Level 1 DDB data, defined in the MIPI-DDB spec in section 5.2.1.1 DdbL1Data. The fields are in the same order with no padding so the data may be copied directly from what is returned by the peripheral.

A DXGK_DSI_CAPS structure is provided to a graphics driver's [*DxgkDsiCaps*](nc-dispmprt-dxgkddi_dsicaps.md) callback function.

## -see-also

[*DxgkDsiCaps*](nc-dispmprt-dxgkddi_dsicaps.md)
