---
UID: NF:nbluso.NET_BUFFER_LIST_IS_USO_SET
tech.root: netvista
title: NET_BUFFER_LIST_IS_USO_SET
ms.date: 05/10/2024
targetos: Windows
description: NET_BUFFER_LIST_IS_USO_SET returns whether the UDP segment offload (USO) offload information is set for a NET_BUFFER_LIST structure.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ndis.h/nbluso.h
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
 - nbluso.h
api_name:
 - NET_BUFFER_LIST_IS_USO_SET
f1_keywords:
 - NET_BUFFER_LIST_IS_USO_SET
 - nbluso/NET_BUFFER_LIST_IS_USO_SET
dev_langs:
 - c++
helpviewer_keywords:
 - NET_BUFFER_LIST_IS_USO_SET
---

# NET_BUFFER_LIST_IS_USO_SET function (ndis.h)

## -description

The **NET_BUFFER_LIST_IS_USO_SET** function returns whether the [UDP Segment Offload (USO)](/windows-hardware/drivers/network/udp-segmentation-offload-uso-) offload information is set for a [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) structure.

## -parameters

### -param Nbl [in]

A pointer to a **NET_BUFFER_LIST** structure.

## -returns

Returns a non-zero value if the USO feature is enabled for this **NET_BUFFER_LIST**.

## -remarks

## -see-also

[**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md)

[UDP Segment Offload (USO)](/windows-hardware/drivers/network/udp-segmentation-offload-uso-)
