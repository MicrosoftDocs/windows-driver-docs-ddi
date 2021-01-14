---
UID: NC:bthsdpddi.PRETRIEVEUUID128
title: PRETRIEVEUUID128 (bthsdpddi.h)
description: The Bluetooth SdpRetrieveUuid128 function is used to copy an unaligned 128-bit universally unique identifier (UUID) from an SDP stream.
old-location: bltooth\sdpretrieveuuid128.htm
tech.root: bltooth
ms.date: 04/27/2018
keywords: ["PRETRIEVEUUID128 callback function"]
ms.keywords: PRETRIEVEUUID128, PRETRIEVEUUID128 callback, SdpRetrieveUuid128, SdpRetrieveUuid128 callback function [Bluetooth Devices], bltooth.sdpretrieveuuid128, bth_funcs_a4149063-722b-45c0-a86b-ffce73b94b0d.xml, sdplib/SdpRetrieveUuid128
req.header: bthsdpddi.h
req.include-header: BthSdpddi.h
req.target-type: Desktop
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.irql: <= PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PRETRIEVEUUID128
 - bthsdpddi/PRETRIEVEUUID128
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - sdplib.h
api_name:
 - PRETRIEVEUUID128
product:
 - Windows
---

# PRETRIEVEUUID128 callback function


## -description

The Bluetooth 
  <b>SdpRetrieveUuid128</b> function is used to copy an unaligned 128-bit universally unique identifier (UUID)
  from an SDP stream.

## -parameters

### -param Stream

A pointer to an unaligned 128-bit UUID.

### -param uuid128

A pointer to an aligned variable to receive the 128-bit UUID.

## -remarks

The 
    <b>SdpRetrieveUuid128</b> function does not search for the UUID to copy. The 
    <i>Stream</i> parameter must specify the exact address of the UUID to be extracted.

Some processor architectures require that values be aligned in memory and will generate an error if an
    attempt is made to access a misaligned value. SDP records are constructed without regard to processor
    alignment rules. When SDP records are stored in memory, they might contain elements that are misaligned
    according to local processor's alignment rules.

The 
    <b>SdpRetrieveUuid128</b> function safely copies UUIDs onto computers that have alignment requirements and
    efficiently copies UUIDs onto computers that do not have requirements. In addition, this function works
    on UUIDs that are aligned correctly.

This function has no effect on byte order.

Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="/windows-hardware/drivers/ddi/bthsdpddi/ns-bthsdpddi-_bthddi_sdp_parse_interface">
    BTHDDI_SDP_PARSE_INTERFACE</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/bthsdpddi/ns-bthsdpddi-_bthddi_sdp_parse_interface">BTHDDI_SDP_PARSE_INTERFACE</a>

