---
UID: NC:netdevice.EVT_NET_DEVICE_PREVIEW_POWER_OFFLOAD
title: EVT_NET_DEVICE_PREVIEW_POWER_OFFLOAD (netdevice.h)
author: windows-driver-content
description: 
tech.root:
ms.assetid: 7429f331-19e5-4a1c-8153-b814c57871d6
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
f1_keywords:
 - "netdevice/EVT_NET_DEVICE_PREVIEW_POWER_OFFLOAD"
req.header: netdevice.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
 - apiref
api_type: 
 - UserDefined
api_location: 
 - netdevice.h
api_name: 
 - EVT_NET_DEVICE_PREVIEW_POWER_OFFLOAD
product: 
 - Windows
targetos: Windows
ms.custom: Vb
---

# EVT_NET_DEVICE_PREVIEW_POWER_OFFLOAD callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

EVT_NET_DEVICE_PREVIEW_POWER_OFFLOAD EvtNetDevicePreviewPowerOffload; 

// Definition

NTSTATUS EvtNetDevicePreviewPowerOffload 
(
	WDFDEVICE Device
	NETPOWEROFFLOAD PowerOffload
)
{...}

```

## -parameters

### -param Device: 
### -param PowerOffload: 



## -returns

Returns NTSTATUS that ...
Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also