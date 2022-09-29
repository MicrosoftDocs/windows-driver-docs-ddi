---
UID: NC:acxpin.EVT_ACX_PIN_DISCONNECTED
tech.root: audio
title: EVT_ACX_PIN_DISCONNECTED
ms.date: 03/25/2022
targetos: Windows
description: The EVT_ACX_PIN_DISCONNECTED callback function is implemented by the driver and is called when the circuit bridge pin is disconnected from the pin of another circuit.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxpin.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - acxpin.h
api_name:
 - EVT_ACX_PIN_DISCONNECTED
f1_keywords:
 - EVT_ACX_PIN_DISCONNECTED
 - acxpin/EVT_ACX_PIN_DISCONNECTED
dev_langs:
 - c++
---

## -description

The **EVT_ACX_PIN_DISCONNECTED** callback function is implemented by the driver and is called when the circuit bridge pin is disconnected from the pin of another circuit.

## -parameters

### -param Pin

An [ACXPIN](index.md) object representing the specific pin that was disconnected.

### -param TargetCircuit

An **ACXTARGETCIRCUIT** object representing the circuit from which the *Pin* was disconnected.

### -param TargetPinId

The identifier of the pin in the *TargetCircuit* from which the *Pin* was disconnected.

## -remarks

This callback is not guaranteed to be called in the following scenarios:

- This device is removed or surprised-removed.
- This device is disabled (query-removed and removed) via device manager.

A driver must not rely on this callback as its only resource cleanup.

The specified ACXTARGETCIRCUIT may be already in its stop state b/c the target circuit may already be gone.

Driver can still access its ACXTARGETCIRCUIT context.

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxpin.h header](index.md)


