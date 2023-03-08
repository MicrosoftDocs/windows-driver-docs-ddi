---
UID: NS:ksproxy._KSSTREAM_SEGMENT
title: _KSSTREAM_SEGMENT (ksproxy.h)
description: The KSSTREAM_SEGMENT structure contains information that describes an I/O operation occurring on a stream.
tech.root: stream
ms.date: 03/07/2023
keywords: ["KSSTREAM_SEGMENT structure"]
ms.keywords: "*PKSSTREAM_SEGMENT, KSSTREAM_SEGMENT, KSSTREAM_SEGMENT structure [Streaming Media Devices], PKSSTREAM_SEGMENT, PKSSTREAM_SEGMENT structure pointer [Streaming Media Devices], _KSSTREAM_SEGMENT, ksproxy/KSSTREAM_SEGMENT, ksproxy/PKSSTREAM_SEGMENT, ksproxy_ce88ef52-d88e-4dc8-952d-53dce519518f.xml, stream.ksstream_segment"
req.header: ksproxy.h
req.include-header: Ksproxy.h
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
req.typenames: "*PKSSTREAM_SEGMENT, KSSTREAM_SEGMENT"
f1_keywords:
 - _KSSTREAM_SEGMENT
 - ksproxy/_KSSTREAM_SEGMENT
 - PKSSTREAM_SEGMENT
 - ksproxy/PKSSTREAM_SEGMENT
 - KSSTREAM_SEGMENT
 - ksproxy/KSSTREAM_SEGMENT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksproxy.h
api_name:
 - _KSSTREAM_SEGMENT
 - PKSSTREAM_SEGMENT
 - KSSTREAM_SEGMENT
---

## -description

The **KSSTREAM_SEGMENT** structure contains information that describes an I/O operation occurring on a stream.

## -struct-fields

### -field KsInterfaceHandler

Pointer to a [IKsInterfaceHandler](/windows-hardware/drivers/ddi/ksproxy/nn-ksproxy-iksinterfacehandler) interface for the I/O operation.

### -field KsDataTypeHandler

Pointer to a [IKsDataTypeHandler](/windows-hardware/drivers/ddi/ksproxy/nn-ksproxy-iksdatatypehandler) interface for the I/O operation.

### -field IoOperation

Value that specifies the type of I/O operation. This value can be one of the following values from the KSIOOPERATION enumerated type:

| Value | Description |
|---|---|
| **KsIoOperation_Write** | Write data to stream. |
| **KsIoOperation_Read** | Read data from stream. |

### -field CompletionEvent

Handle to an event that is used to signal that the I/O operation completed.

## -see-also

[IKsDataTypeHandler](/windows-hardware/drivers/ddi/ksproxy/nn-ksproxy-iksdatatypehandler)

[IKsInterfaceHandler](/windows-hardware/drivers/ddi/ksproxy/nn-ksproxy-iksinterfacehandler)

[IKsInterfaceHandler::KsCompleteIo](/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksinterfacehandler-kscompleteio)

[IKsInterfaceHandler::KsProcessMediaSamples](/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksinterfacehandler-ksprocessmediasamples)

[IKsPin::KsMediaSamplesCompleted](/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-ikspin-ksmediasamplescompleted)
