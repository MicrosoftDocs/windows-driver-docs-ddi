---
UID: NS:avc._AVC_PIN_DESCRIPTOR
title: _AVC_PIN_DESCRIPTOR (avc.h)
description: The AVC_PIN_DESCRIPTOR structure describes a pin on an AV/C subunit device.
old-location: stream\avc_pin_descriptor.htm
tech.root: stream
ms.assetid: 6d404c47-01ae-496c-8252-32f180cf0fd3
ms.date: 04/23/2018
keywords: ["_AVC_PIN_DESCRIPTOR structure"]
ms.keywords: "*PAVC_PIN_DESCRIPTOR, AVC_PIN_DESCRIPTOR, AVC_PIN_DESCRIPTOR structure [Streaming Media Devices], PAVC_PIN_DESCRIPTOR, PAVC_PIN_DESCRIPTOR structure pointer [Streaming Media Devices], _AVC_PIN_DESCRIPTOR, avc/AVC_PIN_DESCRIPTOR, avc/PAVC_PIN_DESCRIPTOR, avcref_4207f0d3-ba1e-47ae-abdd-4eebccf094b9.xml, stream.avc_pin_descriptor"
f1_keywords:
 - "avc/AVC_PIN_DESCRIPTOR"
 - "AVC_PIN_DESCRIPTOR"
req.header: avc.h
req.include-header: Avc.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- avc.h
api_name:
- AVC_PIN_DESCRIPTOR
targetos: Windows
req.typenames: AVC_PIN_DESCRIPTOR, *PAVC_PIN_DESCRIPTOR
---

# _AVC_PIN_DESCRIPTOR structure

## -description

The AVC_PIN_DESCRIPTOR structure describes a pin on an AV/C subunit device.

## -struct-fields

### -field PinId

Specifies the offset (or ID) of the pin for which information is to be retrieved.

### -field PinDescriptor

Specifies a KSPIN_DESCRIPTOR structure. This structure is allocated in the nonpaged pool. The subunit driver must not free this pointer.

### -field IntersectHandler

An optional output parameter specifying a data range intersect handler associated with the **DataRanges** member of the **PinDescriptor** member.

### -field Context

An optional output parameter specifying a value to be passed to the **IntersectHandler** when it is called during format negotiation. For more information about what an intersect handler is, see [DataRange Intersections in AVStream](https://docs.microsoft.com/windows-hardware/drivers/stream/data-range-intersections-in-avstream).

## -remarks

This structure is used with the [AVC_FUNCTION_GET_PIN_DESCRIPTOR](https://docs.microsoft.com/windows-hardware/drivers/stream/avc-function-get-pin-descriptor) function code.

This structure is used only as a member inside the AVC_MULTIFUNC_IRB structure. It is not used by itself.

For information about building and sending an AV/C command, see [How to Use Avc.sys](https://docs.microsoft.com/windows-hardware/drivers/stream/using-avc-sys).

A description of the members of the **KSPIN_DESCRIPTOR** structure used in AVC_PIN_DESCRIPTOR follows:

```cpp
typedef struct {
    ULONG                   InterfacesCount;
    const KSPIN_INTERFACE*  Interfaces;
    ULONG                   MediumsCount;
    const KSPIN_MEDIUM*     Mediums;
    ULONG                   DataRangesCount;
    const PKSDATARANGE*     DataRanges;
    KSPIN_DATAFLOW          DataFlow;
    KSPIN_COMMUNICATION     Communication;
    const GUID*             Category;
    const GUID*             Name;
    union {
        LONGLONG            Reserved;
        struct {
            ULONG           ConstrainedDataRangesCount;
            PKSDATARANGE*   ConstrainedDataRanges;
        };
    };
} KSPIN_DESCRIPTOR, *PKSPIN_DESCRIPTOR;
```

## -see-also

[AV/C Intersect Handler](https://docs.microsoft.com/windows-hardware/drivers/ddi/avc/nc-avc-pfnavcintersecthandler)

[AVC_MULTIFUNC_IRB](https://docs.microsoft.com/windows-hardware/drivers/ddi/avc/ns-avc-_avc_multifunc_irb)

[KSPIN_DESCRIPTOR](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-kspin_descriptor)
