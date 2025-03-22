---
UID: NE:d3dkmddi._DXGK_ENGINE_STATE
tech.root: display
title: DXGK_ENGINE_STATE
ms.date: 04/08/2024
targetos: Windows
description: Learn more about the DXGK_ENGINE_STATE enumeration.
prerelease: true
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_ENGINE_STATE
 - DXGK_ENGINE_STATE
f1_keywords:
 - _DXGK_ENGINE_STATE
 - d3dkmddi/_DXGK_ENGINE_STATE
 - DXGK_ENGINE_STATE
 - d3dkmddi/DXGK_ENGINE_STATE
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGK_ENGINE_STATE
---

# DXGK_ENGINE_STATE enumeration (d3dkmddi.h)

## -description

A **DXGK_ENGINE_STATE** enumeration value specifies the state of a GPU engine.

## -enum-fields

### -field DXGK_ENGINE_STATE_ACTIVE

The graphics engine is currently active.

### -field DXGK_ENGINE_STATE_TRANSITION_TO_F1

The graphics engine is in the process of transitioning to the F1 power state.

### -field DXGK_ENGINE_STATE_HUNG

The graphics engine is no longer responding as expected.

## -see-also

[**DXGK_INTERRUPT_TYPE**](ne-d3dkmddi-_dxgk_interrupt_type.md)

[**DXGKARGCB_NOTIFY_INTERRUPT_DATA**](/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkargcb_notify_interrupt_data)
