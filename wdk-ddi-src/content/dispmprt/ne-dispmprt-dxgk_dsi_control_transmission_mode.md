---
UID: NE:dispmprt._DXGK_DSI_CONTROL_TRANSMISSION_MODE
title: DXGK_DSI_CONTROL_TRANSMISSION_MODE
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
description: Describes an override for the transmission mode, allowing the OEM panel driver to specify whether low power or high performance mode should be used for write packets in the transmission to mitigate cases where a panel only supports one of the modes.
tech.root: display
req.construct-type: enumeration
req.ddi-compliance: 
req.header: dispmprt.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGK_DSI_CONTROL_TRANSMISSION_MODE
 - DXGK_DSI_CONTROL_TRANSMISSION_MODE
f1_keywords:
 - dispmprt/_DXGK_DSI_CONTROL_TRANSMISSION_MODE
 - dispmprt//DXGK_DSI_CONTROL_TRANSMISSION_MODE
 - DXGK_DSI_CONTROL_TRANSMISSION_MODE
dev_langs:
 - c++
---

# DXGK_DSI_CONTROL_TRANSMISSION_MODE enumeration

## -description

Describes an override for the transmission mode, allowing the OEM panel driver to specify whether low power or high performance mode should be used for write packets in the transmission to mitigate cases where a panel only supports one of the modes.

## -enum-fields

### -field DXGK_DCT_DEFAULT

Graphics driver selects transmission mode based on size of payload, current transmission mode and host capabilities. This allows the driver to use the most optimal mode of transmission so should be used unless the OEM panel driver has hardware limitations which the graphics driver is not expected to be aware of which require one specific transmission mode.

### -field DXGK_DCT_FORCE_LOW_POWER

Write packets should use low-power transmission mode or failed if that is not available.

### -field DXGK_DCT_FORCE_HIGH_SPEED

Write packets should use high-speed transmission mode or failed if that is not available.

## -remarks

## -see-also
