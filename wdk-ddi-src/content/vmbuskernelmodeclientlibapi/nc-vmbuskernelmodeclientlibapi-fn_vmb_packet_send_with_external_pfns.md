---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_PACKET_SEND_WITH_EXTERNAL_PFNS
title: FN_VMB_PACKET_SEND_WITH_EXTERNAL_PFNS
author: windows-driver-content
description: 
ms.assetid: 680f7faf-6874-4c02-84b9-d919430ad386
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: vmbuskernelmodeclientlibapi.h
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
-	apiref
api_type: 
-	UserDefined
api_location: 
-	vmbuskernelmodeclientlibapi.h
api_name: 
-	FN_VMB_PACKET_SEND_WITH_EXTERNAL_PFNS
product: Windows
targetos: Windows
---

# FN_VMB_PACKET_SEND_WITH_EXTERNAL_PFNS callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

FN_VMB_PACKET_SEND_WITH_EXTERNAL_PFNS FnVmbPacketSendWithExternalPfns; 

// Definition

NTSTATUS FnVmbPacketSendWithExternalPfns 
(
	__drv_aliasesMem VMBPACKET PacketObject
	PVOID Buffer
	UINT32 BufferLength
	PPFN_NUMBER ExternalDataPfns
	UINT32 PfnLength
	UINT32 Flags
)
{...}

```

## -parameters

### -param PacketObject: 
### -param Buffer: 
### -param BufferLength: 
### -param ExternalDataPfns: 
### -param PfnLength: 
### -param Flags: 



## -returns

Returns NTSTATUS that ...
Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also