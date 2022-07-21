---
UID: NF:acxpin.AcxPinAddStreamBridges
tech.root: audio
title: AcxPinAddStreamBridges
ms.date: 03/25/2022
targetos: Windows
description: The AcxPinAddStreamBridges function adds stream bridges to the specified pin.
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
 - AcxPinAddStreamBridges
f1_keywords:
 - AcxPinAddStreamBridges
 - acxpin/AcxPinAddStreamBridges
dev_langs:
 - c++
---

## -description

The **AcxPinAddStreamBridges** function adds an array of stream bridges to the specified pin.

## -parameters

### -param Pin [in]

The pin to which the stream bridges are added.

### -param StreamBridges [in, reads(StreamBridgesCount)]

A pointer to an array of **ACXSTREAMBRIDGE** objects to add to the specified *Pin*.

### -param StreamBridgesCount [in]

The number of **ACXSTREAMBRIDGE** objects in the *StreamBridges* array.

## -returns

The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) error code.

## -remarks

## -see-also

- [acxpin.h header](index.md)

READY2GO

EDITCOMPLETE
