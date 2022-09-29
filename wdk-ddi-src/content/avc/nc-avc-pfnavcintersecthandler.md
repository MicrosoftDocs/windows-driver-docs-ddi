---
UID: NC:avc.PFNAVCINTERSECTHANDLER
title: PFNAVCINTERSECTHANDLER (avc.h)
description: The AV/C intersect handler determines if the data ranges are compatible.
old-location: stream\av_c_intersect_handler.htm
tech.root: stream
ms.date: 07/22/2022
keywords: ["PFNAVCINTERSECTHANDLER callback"]
ms.keywords: PFNAVCINTERSECTHANDLER, PFNAVCINTERSECTHANDLER function pointer [Streaming Media Devices], avc/PFNAVCINTERSECTHANDLER, avcref_6aa55400-08b6-4a96-af38-23e69fed1621.xml, stream.av_c_intersect_handler
req.header: avc.h
req.include-header: Avc.h
req.target-type: Desktop
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
req.typenames: KBUGCHECK_DATA, *PKBUGCHECK_DATA
f1_keywords:
 - PFNAVCINTERSECTHANDLER
 - avc/PFNAVCINTERSECTHANDLER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - avc.h
api_name:
 - PFNAVCINTERSECTHANDLER
---

# PFNAVCINTERSECTHANDLER callback

## -description

The AV/C intersect handler determines if the data ranges are compatible. This is a user-defined function based on the following prototype:

## -parameters

### -param Context [in]

An optional value expected by the intersect handler. This value is either provided by the subunit driver (if the subunit driver provides the intersect handler), or by the lower driver providing the intersect handler.

### -param PinId [in]

Specifies the offset (or ID) of the pin for which the intersection is being done.

### -param DataRange [in]

### -param MatchingDataRange [in]

### -param DataBufferSize [in]

The size of the buffer passed by the **Data** member. If this is nonzero, then the intersect handler should attempt to return the data format resulting from a matching pair of data ranges. If this is zero, then the intersect handler should provide the required buffer size in **ReportedDataSize**, and return STATUS_BUFFER_OVERFLOW.

### -param Data [out, optional]

An optional buffer to receive the data format resulting from a matching pair of data ranges. This member is ignored if **DataBufferSize** is zero.

### -param DataSize [out]

## -returns

The intersect handler should return STATUS_SUCCESS if the data ranges are compatible, and there was enough buffer space to return the resulting format.

| Return code | Description |
|--|--|
| **STATUS_NO_MATCH** | The data ranges are not compatible. |
| **STATUS_INTERNAL_ERROR** | There was an unexpected format size mismatch. |
| **STATUS_BUFFER_OVERFLOW** | The intersect handler returns the required buffer size through the **ReportedDataSize** member. |
| **STATUS_BUFFER_TOO_SMALL** | The intersect handler was not provided with a buffer large enough to hold the resulting format. The intersect handler must be called again with the **DataBufferSize** set to zero to determine the required buffer size. |
| **STATUS_INSUFFICIENT_RESOURCES** | An internal buffer allocation failed. |

## -syntax

```cpp
typedef NTSTATUS ( *PFNAVCINTERSECTHANDLER)(
  _In_      PVOID        Context,
  _In_      ULONG        PinId,
  _In_      PKSDATARANGE CallerDataRange,
  _In_      PKSDATARANGE DescriptorDataRange,
  _In_      ULONG        DataBufferSize,
  _Out_opt_ PVOID        Data,
  _Out_     PULONG       ReportedDataSize
);
```

## -remarks

The AV/C intersect handler is user-defined, based on the function prototype above.

The handler is used in conjunction with the **AVC_FUNCTION_GET_PIN_DESCRIPTOR** function code. The purpose of the handler  is to match identical pin data formats and return them to the caller.

## -see-also

- [AVC_FUNCTION_GET_PIN_DESCRIPTOR](/windows-hardware/drivers/stream/avc-function-get-pin-descriptor)
- [AVC_PIN_DESCRIPTOR](..\avc\ns-avc-_avc_pin_descriptor.md)
- [AVStrMiniIntersectHandlerEx](..\ks\nc-ks-pfnksintersecthandlerex.md)
- [DataRange Intersections in AVStream](/windows-hardware/drivers/stream/data-range-intersections-in-avstream)
