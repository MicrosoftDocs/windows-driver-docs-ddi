---
UID: NC:acxpin.EVT_ACX_PIN_DISCONNECTED
tech.root: audio
title: EVT_ACX_PIN_DISCONNECTED
ms.date: 10/13/2021
targetos: Windows
description: 
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

The identifier of the pin in the *TargetCicuit* from which the *Pin* was disconnected.

## -remarks

## -see-also
