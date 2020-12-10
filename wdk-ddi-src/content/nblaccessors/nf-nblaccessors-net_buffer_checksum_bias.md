---
UID: NF:nblaccessors.NET_BUFFER_CHECKSUM_BIAS
title: NET_BUFFER_CHECKSUM_BIAS
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: NET_BUFFER_CHECKSUM_BIAS is a macro that NDIS drivers use to get the ChecksumBias member of a NET_BUFFER structure.
tech.root: netvista 
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ndis/nblaccessors.h
req.idl: 
req.include-header: ndis.h
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.target-type: Universal
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - nblaccessors.h
api_name:
 - NET_BUFFER_CHECKSUM_BIAS
f1_keywords:
 - NET_BUFFER_CHECKSUM_BIAS
 - nblaccessors/NET_BUFFER_CHECKSUM_BIAS
dev_langs:
 - c++
---

# NET_BUFFER_CHECKSUM_BIAS macro


## -description

**NET_BUFFER_CHECKSUM_BIAS** is a macro that NDIS drivers use to get the **ChecksumBias** member of a [**NET_BUFFER**](ns-ndis-_net_buffer.md) structure.

## -parameters

### -param _NB

A pointer to a **NET_BUFFER** structure.

## -returns

**NET_BUFFER_CHECKSUM_BIAS** returns the value of the **ChecksumBias** member of the indicated **NET_BUFFER** structure.

## -remarks

The return value specifies the number of bytes of data to skip over at the beginning of the data buffer when computing a checksum. This value is used by the TCP/IP protocol.

## -see-also

[**NET_BUFFER**](ns-ndis-_net_buffer.md)

