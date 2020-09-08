---
UID: NS:ks._KSSTREAM_POINTER_OFFSET
title: _KSSTREAM_POINTER_OFFSET (ks.h)
description: The KSSTREAM_POINTER_OFFSET structure indexes bytes or mappings within a frame.
old-location: stream\ksstream_pointer_offset.htm
tech.root: stream
ms.assetid: ccbe77ee-2377-45d9-b8bf-714680c1920a
ms.date: 04/23/2018
keywords: ["KSSTREAM_POINTER_OFFSET structure"]
ms.keywords: "*PKSSTREAM_POINTER_OFFSET, KSSTREAM_POINTER_OFFSET, KSSTREAM_POINTER_OFFSET structure [Streaming Media Devices], PKSSTREAM_POINTER_OFFSET, PKSSTREAM_POINTER_OFFSET structure pointer [Streaming Media Devices], _KSSTREAM_POINTER_OFFSET, avstruct_e210364b-520e-4d21-98ea-e22f5468e911.xml, ks/KSSTREAM_POINTER_OFFSET, ks/PKSSTREAM_POINTER_OFFSET, stream.ksstream_pointer_offset"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.
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
req.typenames: KSSTREAM_POINTER_OFFSET, *PKSSTREAM_POINTER_OFFSET
f1_keywords:
 - _KSSTREAM_POINTER_OFFSET
 - ks/_KSSTREAM_POINTER_OFFSET
 - PKSSTREAM_POINTER_OFFSET
 - ks/PKSSTREAM_POINTER_OFFSET
 - KSSTREAM_POINTER_OFFSET
 - ks/KSSTREAM_POINTER_OFFSET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KSSTREAM_POINTER_OFFSET
---

# _KSSTREAM_POINTER_OFFSET structure


## -description

The KSSTREAM_POINTER_OFFSET structure indexes bytes or mappings within a frame.

## -struct-fields

### -field Mappings

A pointer to the first element in an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksmapping">KSMAPPING</a> structures. Specify <b>Mappings</b> if the minidriver sets the KSPIN_FLAG_GENERATE_MAPPINGS flag in the <b>Flags</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin_descriptor_ex">KSPIN_DESCRIPTOR_EX</a>. In this case, the <b>Mappings</b> array describes contiguous chunks of physical memory that the client can use to set up a scatter/gather DMA operation with hardware.

### -field Data

A pointer to a buffer containing input data or a buffer to which data is to be output. Specify <b>Data</b> if the minidriver does not set the KSPIN_FLAG_GENERATE_MAPPINGS flag in the <b>Flags</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin_descriptor_ex">KSPIN_DESCRIPTOR_EX</a>.

### -field Alignment

### -field Count

If <b>Data</b> is specified above, <b>Count</b> contains the total number of bytes of data available in the <b>Data</b> buffer. If <b>Mappings</b> is specified above, <b>Count</b> contains the total number of mappings in the <b>Mappings</b> table. <b>Count</b> does not change unless the stream pointer moves to a different <i>Frame</i>.

### -field Remaining

This member specifies a value of type ULONG that indicates the number of bytes or mappings remaining at and ahead of the given stream pointer. This value is equal to <b>Count</b> minus the number of bytes or mappings that have been processed. <b>Remaining</b> starts equal to <b>Count</b> and decreases as the stream pointer moves forward.

## -remarks

See also <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avstream-dma-services">AVStream DMA Services</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksmapping">KSMAPPING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksstream_pointer">KSSTREAM_POINTER</a>

