---
UID: NC:acxpin.EVT_ACX_PIN_DATAFORMAT_CHANGE_NOTIFICATION
tech.root: audio
title: EVT_ACX_PIN_DATAFORMAT_CHANGE_NOTIFICATION
ms.date: 09/08/2022
targetos: Windows
description: The EVT_ACX_PIN_DATAFORMAT_CHANGE_NOTIFICATION callback function is implemented by the driver and is called when a data format change occurs on the specified pin.
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
 - EVT_ACX_PIN_DATAFORMAT_CHANGE_NOTIFICATION
f1_keywords:
 - EVT_ACX_PIN_DATAFORMAT_CHANGE_NOTIFICATION
 - acxpin/EVT_ACX_PIN_DATAFORMAT_CHANGE_NOTIFICATION
dev_langs:
 - c++
helpviewer_keywords:
 - EVT_ACX_PIN_DATAFORMAT_CHANGE_NOTIFICATION
---

## -description

The **EVT_ACX_PIN_DATAFORMAT_CHANGE_NOTIFICATION** callback function is implemented by the driver and is called when a data format change occurs on the specified pin.

## -parameters

### -param Pin

An [ACXPIN](index.md) object representing the specific pin for which the data format change occurred.

### -param TargetCircuit

An **ACXTARGETCIRCUIT** object representing the circuit to which the *Pin* is connected.

### -param TargetPinId

The identifier of the pin in the *TargetCircuit* to which the *Pin* is connected.

## -remarks

## -see-also

- [acxpin.h header](index.md)
