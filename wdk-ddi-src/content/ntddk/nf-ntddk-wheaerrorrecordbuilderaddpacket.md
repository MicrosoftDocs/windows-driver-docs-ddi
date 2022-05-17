---
UID: NF:ntddk.WheaErrorRecordBuilderAddPacket
tech.root: kernel
title: WheaErrorRecordBuilderAddPacket
ms.date: 03/25/2022
targetos: Windows
description: This routine adds a packet into an error record.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ntddk.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 22H2
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - WheaErrorRecordBuilderAddPacket
f1_keywords:
 - WheaErrorRecordBuilderAddPacket
 - ntddk/WheaErrorRecordBuilderAddPacket
dev_langs:
 - c++
helpviewer_keywords:
 - WheaErrorRecordBuilderAddPacket
---

## -description

This routine adds a packet into an error record.

## -parameters

### -param Record [in, out]

Supplies a buffer for error record data.

### -param Packet [in, out]

Supplies a buffer holding the error packet data.

### -param MaxSectionCount [in]

Defines the **UINT32** parameter *MaxSectionCount*.

## -returns

Returns a pointer to the added section. Returns NULL if not added.

## -remarks

## -see-also
