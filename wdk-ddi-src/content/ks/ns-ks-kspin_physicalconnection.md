---
UID: NS:ks.__unnamed_struct_34
title: KSPIN_PHYSICALCONNECTION (ks.h)
description: A structure of type KSPIN_PHYSICALCONNECTION is returned in response to a KSPROPERTY_PIN_PHYSICALCONNECTION request.
old-location: stream\kspin_physicalconnection.htm
tech.root: stream
ms.assetid: e11c6e8d-a338-4427-af04-bdb07b9e9a73
ms.date: 04/23/2018
keywords: ["KSPIN_PHYSICALCONNECTION structure"]
ms.keywords: "*PKSPIN_PHYSICALCONNECTION, KSPIN_PHYSICALCONNECTION, KSPIN_PHYSICALCONNECTION structure [Streaming Media Devices], PKSPIN_PHYSICALCONNECTION, PKSPIN_PHYSICALCONNECTION structure pointer [Streaming Media Devices], ks-struct_7b9a3e0f-2cd9-4822-8e8a-03355dc522ed.xml, ks/KSPIN_PHYSICALCONNECTION, ks/PKSPIN_PHYSICALCONNECTION, stream.kspin_physicalconnection"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: KSPIN_PHYSICALCONNECTION, *PKSPIN_PHYSICALCONNECTION
f1_keywords:
 - PKSPIN_PHYSICALCONNECTION
 - ks/PKSPIN_PHYSICALCONNECTION
 - KSPIN_PHYSICALCONNECTION
 - ks/KSPIN_PHYSICALCONNECTION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KSPIN_PHYSICALCONNECTION
---

# KSPIN_PHYSICALCONNECTION structure


## -description

A structure of type KSPIN_PHYSICALCONNECTION is returned in response to a <a href="/windows-hardware/drivers/stream/ksproperty-pin-physicalconnection">KSPROPERTY_PIN_PHYSICALCONNECTION</a> request.

## -struct-fields

### -field Size

Specifies the size of the structure. Note that the structure contains a dynamic array.

### -field Pin

Specifies the PinId of the connected pin on the other filter. (Pin 2 of Wave is connected to Pin 1 of Topology.)

### -field SymbolicLinkName

Specifies a string containing the symbolic link name of the connected filter

## -remarks

This structure is used with port class only.

## -see-also

<a href="/windows-hardware/drivers/stream/ksproperty-pin-physicalconnection">KSPROPERTY_PIN_PHYSICALCONNECTION</a>