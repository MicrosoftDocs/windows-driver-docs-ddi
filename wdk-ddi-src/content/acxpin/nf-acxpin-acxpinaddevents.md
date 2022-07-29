---
UID: NF:acxpin.AcxPinAddEvents
tech.root: audio
title: AcxPinAddEvents
ms.date: 03/25/2022
targetos: Windows
description: The AcxPinAddEvents function adds an array of events to the specified pin.
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
 - AcxPinAddEvents
f1_keywords:
 - AcxPinAddEvents
 - acxpin/AcxPinAddEvents
dev_langs:
 - c++
---

## -description

The **AcxPinAddEvents** function adds an array of events to the specified pin.

## -parameters

### -param Pin [in]

The pin to which the events are added.

### -param Events [in, reads(EventsCount)]

A pointer to an array of **ACXEVENT** objects to add to the specified *Pin*.

### -param EventsCount [in]

The number of **ACXEVENT** objects in the *Events* array.

## -returns

The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) error code.

## -remarks

## -see-also

- [acxpin.h header](index.md)


