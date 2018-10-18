---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_ENABLE
title: FN_VMB_CHANNEL_ENABLE
author: windows-driver-content
description: The VmbChannelEnable function enables a channel that is in the disabled state by connecting to VMBus and offering or opening a channel, as appropriate for the endpoint type.
tech.root: netvista
ms.assetid: e2761a5b-dac3-4423-93af-5f009c2cfaad
ms.date: 05/21/2018
ms.topic: callback
req.header: vmbuskernelmodeclientlibapi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1803
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
-	apiref
api_type: 
-	UserDefined
api_location: 
-	vmbuskernelmodeclientlibapi.h
api_name: 
-	FN_VMB_CHANNEL_ENABLE
product:
-	Windows
targetos: Windows
---

# FN_VMB_CHANNEL_ENABLE callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelEnable</b> function enables a channel that is in the disabled state by connecting to VMBus and
offering or opening a channel, as  appropriate for the endpoint type.

## -prototype

```cpp
//Declaration

FN_VMB_CHANNEL_ENABLE FnVmbChannelEnable; 

// Definition

NTSTATUS FnVmbChannelEnable 
(
	VMBCHANNEL Channel
)
{...}

```

## -parameters

### -param Channel 

The handle of a channel to enable.

## -returns

Returns STATUS_SUCCESS if the operation succeeds, or an appropriate NTSTATUS error code otherwise.

## -remarks

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a client function accessed from the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md) structure. 
>
> For more information, see the Remarks section of the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md).

## -see-also
