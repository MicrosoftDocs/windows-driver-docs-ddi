---
UID: NF:poll.NdisRegisterPoll
tech.root: netvista
title: NdisRegisterPoll
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: 
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: poll.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - poll.h
api_name:
 - NdisRegisterPoll
f1_keywords:
 - NdisRegisterPoll
 - poll/NdisRegisterPoll
dev_langs:
 - c++
---

## -description

A miniport driver calls the **NdisRegisterPoll** function to register resources required for the miniport's poll routine. 

## -parameters

### -param NdisHandle

[_In_] An NDIS_HANDLE to a block of driver-allocated context information.

### -param Context

[_In_opt_] A pointer to a context area.

### -param Characteristics

[_In_] A pointer to an [**NDIS_POLL_CHARACTERISTICS**](ns-poll-ndis_poll_characteristics.md) structure. 

### -param PollHandle

[_Out_] A pointer to a caller-supplied NDIS_POLL_HANDLE variable. This location receives a handle to the new poll routine context. The driver must save this handle for use in subsequent **NdisXxx** function calls.

## -returns

Returns STATUS_SUCCESS if the operation succeeds. Otherwise, returns an [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) error code.

## -remarks

The driver must subsequently call the [**NdisDeregisterPoll**](nf-poll-ndisderegisterpoll.md) function when the NDIS poll is no longer needed.

## -see-also

[**NDIS_POLL_CHARACTERISTICS**](ns-poll-ndis_poll_characteristics.md)

[**NdisDeregisterPoll**](nf-poll-ndisderegisterpoll.md)