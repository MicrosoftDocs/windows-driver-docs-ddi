---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_PACKET_RESTORE
title: FN_VMB_PACKET_RESTORE
author: windows-driver-content
description: 
ms.assetid: 2bb4f7b2-a6e7-4a11-a5ca-bfd7db47037a
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
-	FN_VMB_PACKET_RESTORE
product: Windows
targetos: Windows
---

# FN_VMB_PACKET_RESTORE callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

FN_VMB_PACKET_RESTORE FnVmbPacketRestore; 

// Definition

NTSTATUS FnVmbPacketRestore 
(
	__drv_aliasesMem VMBPACKET PacketObject
	PVOID Buffer
	ULONG BufferSize
)
{...}

```

## -parameters

### -param PacketObject: 
### -param Buffer: 
### -param BufferSize: 



## -returns

Returns NTSTATUS that ...
Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also