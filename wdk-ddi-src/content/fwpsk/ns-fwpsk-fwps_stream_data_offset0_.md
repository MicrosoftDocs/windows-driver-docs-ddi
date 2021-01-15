---
UID: NS:fwpsk.FWPS_STREAM_DATA_OFFSET0_
title: FWPS_STREAM_DATA_OFFSET0_ (fwpsk.h)
description: The FWPS_STREAM_DATA_OFFSET0 structure defines an offset into a portion of a data stream that is described by an FWPS_STREAM_DATA0 structure.Note  FWPS_STREAM_DATA_OFFSET0 is a specific version of FWPS_STREAM_DATA_OFFSET.
old-location: netvista\fwps_stream_data_offset0.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["FWPS_STREAM_DATA_OFFSET0_ structure"]
ms.keywords: FWPS_STREAM_DATA_OFFSET0, FWPS_STREAM_DATA_OFFSET0 structure [Network Drivers Starting with Windows Vista], FWPS_STREAM_DATA_OFFSET0_, fwpsk/FWPS_STREAM_DATA_OFFSET0, netvista.fwps_stream_data_offset0, wfp_ref_3_struct_3_fwps_P-Z_dc4b9bc1-f92b-4318-9cf4-466047be22f2.xml
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.typenames: FWPS_STREAM_DATA_OFFSET0
f1_keywords:
 - FWPS_STREAM_DATA_OFFSET0_
 - fwpsk/FWPS_STREAM_DATA_OFFSET0_
 - FWPS_STREAM_DATA_OFFSET0
 - fwpsk/FWPS_STREAM_DATA_OFFSET0
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - fwpsk.h
api_name:
 - FWPS_STREAM_DATA_OFFSET0_
 - FWPS_STREAM_DATA_OFFSET0
---

# FWPS_STREAM_DATA_OFFSET0_ structure


## -description

The <b>FWPS_STREAM_DATA_OFFSET0</b> structure defines an offset into a portion of a data stream that is
  described by an 
  <a href="/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_stream_data0_">FWPS_STREAM_DATA0</a> structure.
<div class="alert"><b>Note</b>  <b>FWPS_STREAM_DATA_OFFSET0</b> is a specific version of <b>FWPS_STREAM_DATA_OFFSET</b>. See <a href="/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -struct-fields

### -field netBufferList

A pointer to the 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure in which the
     offset lies.

### -field netBuffer

A pointer to the 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure in which the offset
     lies.

### -field mdl

A pointer to the Memory Descriptor List (MDL) in which the offset lies.

### -field mdlOffset

The byte offset from the beginning of the MDL pointed to by the 
     <b>Mdl</b> member.

### -field netBufferOffset

Reserved for system use. Callout drivers must not use this member.

### -field streamDataOffset

Reserved for system use. Callout drivers must not use this member.

## -remarks

An FWPS_STREAM_DATA_OFFSET0 structure is contained within an 
    <a href="/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_stream_data0_">FWPS_STREAM_DATA0</a> structure. The
    FWPS_STREAM_DATA_OFFSET0 structure specifies an offset into the data stream.

The combination of the 
    <b>netBufferList</b>, 
    <b>netBuffer</b>, 
    <b>Mdl</b>, and 
    <b>mdlOffset</b> members provide the location of the first byte of the data of interest.

## -see-also

<a href="/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_stream_data0_">FWPS_STREAM_DATA0</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>

