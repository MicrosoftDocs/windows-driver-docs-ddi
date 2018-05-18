---
UID: NS:vmbuskernelmodeclientlibapi._KMCL_CLIENT_INTERFACE_V1
title: _KMCL_CLIENT_INTERFACE_V1
author: windows-driver-content
description: 
ms.assetid: 7f4cd2b7-046e-49d9-a834-e77d94ba1dc8
ms.author: windowsdriverdev
ms.date: 
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _KMCL_CLIENT_INTERFACE_V1, KMCL_CLIENT_INTERFACE_V1, *PKMCL_CLIENT_INTERFACE_V1, 
req.header: vmbuskernelmodeclientlibapi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: KMCL_CLIENT_INTERFACE_V1, *PKMCL_CLIENT_INTERFACE_V1
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	vmbuskernelmodeclientlibapi.h
api_name: 
-	_KMCL_CLIENT_INTERFACE_V1
product: Windows
targetos: Windows
---

# _KMCL_CLIENT_INTERFACE_V1 structure

## -description

test

## -syntax

```C++
#ifdef __cplusplus

typedef struct _KMCL_CLIENT_INTERFACE_V1 : INTERFACE {

#else

typedef struct _KMCL_CLIENT_INTERFACE_V1 {
    INTERFACE;

#endif

    PFN_VMB_CHANNEL_ALLOCATE                                         VmbChannelAllocate;
    PFN_VMB_CHANNEL_CLEANUP                                          VmbChannelCleanup;
    PFN_VMB_CHANNEL_CREATE_GPADL_FROM_BUFFER                         VmbChannelCreateGpadlFromBuffer;
    PFN_VMB_CHANNEL_CREATE_GPADL_FROM_MDL                            VmbChannelCreateGpadlFromMdl;
    PFN_VMB_CHANNEL_DELETE_GPADL                                     VmbChannelDeleteGpadl;
    PFN_VMB_CHANNEL_DISABLE                                          VmbChannelDisable;
    PFN_VMB_CHANNEL_ENABLE                                           VmbChannelEnable;
    PFN_VMB_CHANNEL_GET_INTERFACE_INSTANCE                           VmbChannelGetInterfaceInstance;
    PFN_VMB_CHANNEL_GET_MMIO_SPACE                                   VmbChannelGetMmioSpace;
    PFN_VMB_CHANNEL_GET_POINTER                                      VmbChannelGetPointer;
    PFN_VMB_CHANNEL_INIT_SET_CLIENT_CONTEXT_SIZE                     VmbChannelInitSetClientContextSize;
    PFN_VMB_CHANNEL_INIT_SET_FLAGS                                   VmbChannelInitSetFlags;
    PFN_VMB_CHANNEL_INIT_SET_FRIENDLY_NAME                           VmbChannelInitSetFriendlyName;
    PFN_VMB_CHANNEL_INIT_SET_MAXIMUM_EXTERNAL_DATA                   VmbChannelInitSetMaximumExternalData;
    PFN_VMB_CHANNEL_INIT_SET_MAXIMUM_PACKET_SIZE                     VmbChannelInitSetMaximumPacketSize;
    PFN_VMB_CHANNEL_INIT_SET_PROCESS_PACKET_CALLBACKS                VmbChannelInitSetProcessPacketCallbacks;
    PFN_VMB_CHANNEL_INIT_SET_STATE_CHANGE_CALLBACKS                  VmbChannelInitSetStateChangeCallbacks;
    PFN_VMB_CHANNEL_PACKET_COMPLETE                                  VmbChannelPacketComplete;
    PFN_VMB_CHANNEL_PACKET_DEFER_TO_PASSIVE                          VmbChannelPacketDeferToPassive;
    PFN_VMB_CHANNEL_PACKET_FAIL                                      VmbChannelPacketFail;
    PFN_VMB_CHANNEL_PACKET_GET_EXTERNAL_DATA                         VmbChannelPacketGetExternalData;
    PFN_VMB_CHANNEL_PAUSE                                            VmbChannelPause;
    PFN_VMB_CHANNEL_SEND_SYNCHRONOUS_REQUEST                         VmbChannelSendSynchronousRequest;
    PFN_VMB_CHANNEL_SET_INCOMING_PROCESSING_AT_PASSIVE               VmbChannelSetIncomingProcessingAtPassive;
    PFN_VMB_CHANNEL_SET_INTERRUPT_LATENCY                            VmbChannelSetInterruptLatency;
    PFN_VMB_CHANNEL_SET_POINTER                                      VmbChannelSetPointer;
    PFN_VMB_CHANNEL_SET_TRANSACTION_QUOTA                            VmbChannelSetTransactionQuota;
    PFN_VMB_CHANNEL_SIZEOF_PACKET                                    VmbChannelSizeofPacket;
    PFN_VMB_CHANNEL_START                                            VmbChannelStart;
    PFN_VMB_CLIENT_CHANNEL_INIT_SET_RING_BUFFER_PAGE_COUNT           VmbClientChannelInitSetRingBufferPageCount;
    PFN_VMB_CLIENT_CHANNEL_INIT_SET_TARGET_PNP                       VmbClientChannelInitSetTargetPnp;
    PFN_VMB_PACKET_ALLOCATE                                          VmbPacketAllocate;
    PFN_VMB_PACKET_FREE                                              VmbPacketFree;
    PFN_VMB_PACKET_GET_CHANNEL                                       VmbPacketGetChannel;
    PFN_VMB_PACKET_GET_POINTER                                       VmbPacketGetPointer;
    PFN_VMB_PACKET_INITIALIZE                                        VmbPacketInitialize;
    PFN_VMB_PACKET_SEND                                              VmbPacketSend;
    PFN_VMB_PACKET_SEND_WITH_EXTERNAL_MDL                            VmbPacketSendWithExternalMdl;
    PFN_VMB_PACKET_SEND_WITH_EXTERNAL_PFNS                           VmbPacketSendWithExternalPfns;
    PFN_VMB_PACKET_SET_COMPLETION_ROUTINE                            VmbPacketSetCompletionRoutine;
    PFN_VMB_PACKET_SET_POINTER                                       VmbPacketSetPointer;

} KMCL_CLIENT_INTERFACE_V1, *PKMCL_CLIENT_INTERFACE_V1;
```

## -struct-fields

### -field INTERFACE

test

### -field _KMCL_CLIENT_INTERFACE_V1

test
 
### -field _KMCL_CLIENT_INTERFACE_V1.VmbChannelAllocate

test
 
#### -VmbChannelCleanup

test
 
#### -VmbChannelCreateGpadlFromBuffer

test
 
#### -VmbChannelCreateGpadlFromMdl

test
 
#### -VmbChannelDeleteGpadl

test
 
#### -VmbChannelDisable

test
 
#### -VmbChannelEnable

test
 
#### -VmbChannelGetInterfaceInstance

test
 
#### -VmbChannelGetMmioSpace

test
 
#### -VmbChannelGetPointer

test
 
#### -VmbChannelInitSetClientContextSize

test
 
#### -VmbChannelInitSetFlags

test
 
#### -VmbChannelInitSetFriendlyName

test
 
#### -VmbChannelInitSetMaximumExternalData

test
 
#### -VmbChannelInitSetMaximumPacketSize

test
 
#### -VmbChannelInitSetProcessPacketCallbacks

test
 
#### -VmbChannelInitSetStateChangeCallbacks

test
 
#### -VmbChannelPacketComplete

test
 
#### -VmbChannelPacketDeferToPassive

test
 
#### -VmbChannelPacketFail

test
 
#### -VmbChannelPacketGetExternalData

test
 
#### -VmbChannelPause

test
 
#### -VmbChannelSendSynchronousRequest

test
 
#### -VmbChannelSetIncomingProcessingAtPassive

test
 
#### -VmbChannelSetInterruptLatency

test
 
#### -VmbChannelSetPointer

test
 
#### -VmbChannelSetTransactionQuota

test
 
#### -VmbChannelSizeofPacket

test
 
#### -VmbChannelStart

test
 
#### -VmbClientChannelInitSetRingBufferPageCount

test
 
#### -VmbClientChannelInitSetTargetPnp

test
 
#### -VmbPacketAllocate

test
 
#### -VmbPacketFree

test
 
#### -VmbPacketGetChannel

test
 
#### -VmbPacketGetPointer

test
 
#### -VmbPacketInitialize

test
 
#### -VmbPacketSend

test
 
#### -VmbPacketSendWithExternalMdl

test
 
#### -VmbPacketSendWithExternalPfns

test
 
#### -VmbPacketSetCompletionRoutine

test
 
#### -VmbPacketSetPointer

test
 
## -remarks

test

## -see-also

test