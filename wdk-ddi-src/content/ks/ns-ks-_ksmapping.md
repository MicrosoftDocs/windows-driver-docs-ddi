---
UID: NS:ks._KSMAPPING
title: _KSMAPPING (ks.h)
description: The KSMAPPING structure is used to describe a single contiguous chunk of physical memory for use in scatter/gather DMA operations.
old-location: stream\ksmapping.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KSMAPPING structure"]
ms.keywords: "*PKSMAPPING, KSMAPPING, KSMAPPING structure [Streaming Media Devices], PKSMAPPING, PKSMAPPING structure pointer [Streaming Media Devices], _KSMAPPING, avstruct_65f80fd5-14a6-431b-a1b6-e6c3d18302d3.xml, ks/KSMAPPING, ks/PKSMAPPING, stream.ksmapping"
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
req.typenames: KSMAPPING, *PKSMAPPING
f1_keywords:
 - _KSMAPPING
 - ks/_KSMAPPING
 - PKSMAPPING
 - ks/PKSMAPPING
 - KSMAPPING
 - ks/KSMAPPING
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - _KSMAPPING
 - PKSMAPPING
 - KSMAPPING
---

# _KSMAPPING structure


## -description

The KSMAPPING structure is used to describe a single contiguous chunk of physical memory for use in scatter/gather DMA operations.

## -struct-fields

### -field PhysicalAddress

This member contains the physical address of this piece of the data frame.

### -field ByteCount

This member contains the number of bytes of contiguous physical memory in this individual mapping.

### -field Alignment

This member specifies the memory alignment in bytes for this buffer.

## -remarks

In order for minidrivers to use this structure within the stream pointer offsets, the pin for which this is referring must specify scatter/gather DMA mapping generation through KSPIN_FLAG_GENERATE_MAPPINGS and the client must register its DMA adapter object with AVStream using <b>KsDeviceRegisterAdapterObject</b>. See <a href="/windows-hardware/drivers/stream/avstream-dma-services">AVStream DMA Services</a>. The KSPIN_FLAG_GENERATE_MAPPINGS flag is defined on the <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_kspin_descriptor_ex">KSPIN_DESCRIPTOR_EX</a> reference page.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksstream_pointer_offset">KSSTREAM_POINTER_OFFSET</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksdeviceregisteradapterobject">KsDeviceRegisterAdapterObject</a>

