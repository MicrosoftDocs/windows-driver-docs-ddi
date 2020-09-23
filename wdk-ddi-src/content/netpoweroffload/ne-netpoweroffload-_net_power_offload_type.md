---
UID: NE:netpoweroffload._NET_POWER_OFFLOAD_TYPE
title: NET_POWER_OFFLOAD_TYPE (netpoweroffload.h)
description: The NET_POWER_OFFLOAD_TYPE enumeration specifies the type for a low power offload protocol offload to a net adapter.
tech.root: netvista
ms.assetid: d321223f-7e48-43c6-bb35-85f0c646651e
ms.author: windowsdriverdev
ms.date: 09/30/2019
keywords: ["NET_POWER_OFFLOAD_TYPE enumeration"]
ms.keywords: NET_POWER_OFFLOAD_TYPE, NET_POWER_OFFLOAD_TYPE,
req.header: netpoweroffload.h
req.include-header: netadaptercx.h 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: NET_POWER_OFFLOAD_TYPE
targetos: Windows
ms.custom: Vb
f1_keywords:
 - _NET_POWER_OFFLOAD_TYPE
 - netpoweroffload/_NET_POWER_OFFLOAD_TYPE
 - NET_POWER_OFFLOAD_TYPE
 - netpoweroffload/NET_POWER_OFFLOAD_TYPE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netpoweroffload.h
api_name:
 - NET_POWER_OFFLOAD_TYPE
product:
 - Windows
---

# NET_POWER_OFFLOAD_TYPE enumeration


## -description

The **NET_POWER_OFFLOAD_TYPE** enumeration specifies the type for a low power offload protocol offload to a net adapter.

## -enum-fields

### -field NetPowerOffloadTypeArp 

The power offload is the IPv4 ARP protocol.

### -field NetPowerOffloadTypeNS 

The power offload is the IPv6 Neighbor Solicitation (NS) protocol.

## -remarks

Call [**NetPowerOffloadGetType**](../netpoweroffload/nf-netpoweroffload-netpoweroffloadgettype.md) to get the type for a low power protocol offload.

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

