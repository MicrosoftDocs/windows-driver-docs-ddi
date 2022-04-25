---
UID: NC:acxpin.EVT_ACX_PIN_CONNECTED
tech.root: audio
title: EVT_ACX_PIN_CONNECTED
ms.date: 03/25/2022
targetos: Windows
description: The EVT_ACX_PIN_CONNECTED callback function is implemented by the driver and is called when the circuit bridge pin is connected to bridge pin of another circuit.
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
 - EVT_ACX_PIN_CONNECTED
f1_keywords:
 - EVT_ACX_PIN_CONNECTED
 - acxpin/EVT_ACX_PIN_CONNECTED
dev_langs:
 - c++
---

## -description

The **EVT_ACX_PIN_CONNECTED** callback function is implemented by the driver and is called when the circuit bridge pin is connected to bridge pin of another circuit.

## -parameters

### -param Pin

An [ACXPIN](index.md) object representing the specific pin that was connected.

### -param TargetCircuit

An **ACXTARGETCIRCUIT** object representing the circuit to which the *Pin* was connected.

### -param TargetPinId

The identifier of the pin in the *TargetCircuit* to which the *Pin* was connected.

## -remarks

This event happens when the composite circuit is fully initialized. From this point on, the *TargetCircuit* can be used to send [kernel streaming properties](/windows-hardware/drivers/stream/ks-properties) and [kernel streaming methods](/windows-hardware/drivers/stream/ks-methods) requests.

## -see-also

- [acxpin.h header](index.md)

READY2GO

EDITCOMPLETE
