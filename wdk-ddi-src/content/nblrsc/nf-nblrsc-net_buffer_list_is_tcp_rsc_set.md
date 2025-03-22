---
UID: NF:nblrsc.NET_BUFFER_LIST_IS_TCP_RSC_SET
tech.root: netvista
title: NET_BUFFER_LIST_IS_TCP_RSC_SET
ms.date: 05/10/2024
targetos: Windows
description: NET_BUFFER_LIST_IS_TCP_RSC_SET returns whether receive segment coalescing (RSC) is set for a NET_BUFFER_LIST structure.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ndis.h/nblrsc.h
req.idl: 
req.include-header: ndis.h
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2
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
 - nblrsc.h
api_name:
 - NET_BUFFER_LIST_IS_TCP_RSC_SET
f1_keywords:
 - NET_BUFFER_LIST_IS_TCP_RSC_SET
 - nblrsc/NET_BUFFER_LIST_IS_TCP_RSC_SET
dev_langs:
 - c++
helpviewer_keywords:
 - NET_BUFFER_LIST_IS_TCP_RSC_SET
---

# NET_BUFFER_LIST_IS_TCP_RSC_SET function (ndis.h)

## -description

The **NET_BUFFER_LIST_IS_TCP_RSC_SET** function returns whether receive segment coalescing (RSC) is set for a [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) structure.

## -parameters

### -param Nbl [in]

A pointer to a **NET_BUFFER_LIST** structure.

## -returns

Returns a non-zero value if RSC is enabled for this **NET_BUFFER_LIST**.

## -remarks

## -see-also

[**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md)
