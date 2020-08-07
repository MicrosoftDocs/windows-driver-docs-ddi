---
UID: NS:vmbuskernelmodeclientlibapi._KMCL_SERVER_ONLY_METHODS_V5
title: _KMCL_CLIENT_INTERFACE_V1 (vmbuskernelmodeclientlibapi.h)
description: The KMCL_CLIENT_INTERFACE_V1 structure contains function pointers for client functions for the VMBus Kernel Mode Client Library (KMCL) interface.
tech.root: netvista
ms.assetid: 7f4cd2b7-046e-49d9-a834-e77d94ba1dc8
ms.date: 09/13/2018
keywords: ["KMCL_CLIENT_INTERFACE_V1 structure"]
f1_keywords:
 - "vmbuskernelmodeclientlibapi/_KMCL_CLIENT_INTERFACE_V1"
 - "_KMCL_CLIENT_INTERFACE_V1"
ms.keywords: _KMCL_CLIENT_INTERFACE_V1, KMCL_CLIENT_INTERFACE_V1, *PKMCL_CLIENT_INTERFACE_V1, 
req.header: vmbuskernelmodeclientlibapi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1803
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
- apiref
api_type: 
- HeaderDef
api_location: 
- vmbuskernelmodeclientlibapi.h
api_name: 
- _KMCL_CLIENT_INTERFACE_V1
targetos: Windows
ms.custom: RS5
---

# _KMCL_CLIENT_INTERFACE_V1 structure

## -description

The **KMCL_CLIENT_INTERFACE_V1** structure contains function pointers for client functions for the VMBus Kernel Mode Client Library (KMCL) interface.

For more information about how to access the KMCL interface, see the Remarks section.

## -syntax

```cpp
typedef struct _KMCL_CLIENT_INTERFACE_V1 {
    INTERFACE;
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
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbChannelAllocate

A pointer to the [**VmbChannelAllocate**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_allocate.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbChannelCleanup

A pointer to the [**VmbChannelCleanup**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_cleanup.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbChannelCreateGpadlFromBuffer

A pointer to the [**VmbChannelCreateGpadlFromBuffer**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_create_gpadl_from_buffer.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbChannelCreateGpadlFromMdl

A pointer to the [**VmbChannelCreateGpadlFromMdl**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_create_gpadl_from_mdl.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbChannelDeleteGpadl

A pointer to the [**VmbChannelDeleteGpadl**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_delete_gpadl.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbChannelDisable

A pointer to the [**VmbChannelDisable**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_disable.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbChannelEnable

A pointer to the [**VmbChannelEnable**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_enable.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbChannelGetInterfaceInstance

A pointer to the [**VmbChannelGetInterfaceInstance**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_get_interface_instance.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbChannelGetMmioSpace

A pointer to the [**VmbChannelGetMmioSpace**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_get_mmio_space.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbChannelGetPointer

A pointer to the [**VmbChannelGetPointer**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_get_pointer.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbChannelInitSetClientContextSize

A pointer to the [**VmbChannelInitSetClientContextSize**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_init_set_client_context_size.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbChannelInitSetFlags

A pointer to the [**VmbChannelInitSetFlags**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_init_set_flags.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbChannelInitSetFriendlyName

A pointer to the [**VmbChannelInitSetFriendlyName**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_init_set_friendly_name.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbChannelInitSetMaximumExternalData

A pointer to the [**VmbChannelInitSetMaximumExternalData**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_init_set_maximum_external_data.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbChannelInitSetMaximumPacketSize

A pointer to the [**VmbChannelInitSetMaximumPacketSize**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_init_set_maximum_packet_size.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbChannelInitSetProcessPacketCallbacks

A pointer to the [**VmbChannelInitSetProcessPacketCallbacks**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_init_set_process_packet_callbacks.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbChannelInitSetStateChangeCallbacks

A pointer to the [**VmbChannelInitSetStateChangeCallbacks**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_init_set_state_change_callbacks.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbChannelPacketComplete

A pointer to the [**VmbChannelPacketComplete**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_packet_complete.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbChannelPacketDeferToPassive

A pointer to the [**VmbChannelPacketDeferToPassive**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_packet_defer_to_passive.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbChannelPacketFail

A pointer to the [**VmbChannelPacketFail**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_packet_fail.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbChannelPacketGetExternalData

A pointer to the [**VmbChannelPacketGetExternalData**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_packet_get_external_data.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbChannelPause

A pointer to the [**VmbChannelPause**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_pause.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbChannelSendSynchronousRequest

A pointer to the [**VmbChannelPause**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_send_synchronous_request.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbChannelSetIncomingProcessingAtPassive

A pointer to the [**VmbChannelSetIncomingProcessingAtPassive**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_set_incoming_processing_at_passive.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbChannelSetInterruptLatency

A pointer to the [**VmbChannelSetInterruptLatency**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_set_interrupt_latency.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbChannelSetPointer

A pointer to the [**VmbChannelSetPointer**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_set_pointer.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbChannelSetTransactionQuota

A pointer to the [**VmbChannelSetTransactionQuota**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_set_transaction_quota.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbChannelSizeofPacket

A pointer to the [**VmbChannelSizeofPacket**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_sizeof_packet.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbChannelStart

A pointer to the [**VmbChannelStart**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_start.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbClientChannelInitSetRingBufferPageCount

A pointer to the [**VmbClientChannelInitSetRingBufferPageCount**](nc-vmbuskernelmodeclientlibapi-fn_vmb_client_channel_init_set_ring_buffer_page_count.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbClientChannelInitSetTargetPnp

A pointer to the [**VmbClientChannelInitSetTargetPnp**](nc-vmbuskernelmodeclientlibapi-fn_vmb_client_channel_init_set_target_pnp.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbPacketAllocate

A pointer to the [**VmbPacketAllocate**](nc-vmbuskernelmodeclientlibapi-fn_vmb_packet_allocate.md) function.

### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbPacketFree

A pointer to the [**VmbPacketFree**](nc-vmbuskernelmodeclientlibapi-fn_vmb_packet_free.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbPacketGetChannel

A pointer to the [**VmbPacketGetChannel**](nc-vmbuskernelmodeclientlibapi-fn_vmb_packet_get_channel.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbPacketGetPointer

A pointer to the [**VmbPacketGetPointer**](nc-vmbuskernelmodeclientlibapi-fn_vmb_packet_get_pointer.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbPacketInitialize

A pointer to the [**VmbPacketInitialize**](nc-vmbuskernelmodeclientlibapi-fn_vmb_packet_initialize.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbPacketSend

A pointer to the [**VmbPacketSend**](nc-vmbuskernelmodeclientlibapi-fn_vmb_packet_send.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbPacketSendWithExternalMdl

A pointer to the [**VmbPacketSendWithExternalMdl**](nc-vmbuskernelmodeclientlibapi-fn_vmb_packet_send_with_external_mdl.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbPacketSendWithExternalPfns

A pointer to the [**VmbPacketSendWithExternalPfns**](nc-vmbuskernelmodeclientlibapi-fn_vmb_packet_send_with_external_pfns.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbPacketSetCompletionRoutine

A pointer to the [**VmbPacketSetCompletionRoutine**](nc-vmbuskernelmodeclientlibapi-fn_vmb_packet_set_completion_routine.md) function.
 
### -field _KMCL_CLIENT_INTERFACE_V1._KMCL_CLIENT_INTERFACE_V1.VmbPacketSetPointer

A pointer to the [**VmbPacketSetPointer**](nc-vmbuskernelmodeclientlibapi-fn_vmb_packet_set_pointer.md) function.
 
## -remarks

The first member of this structure is an [**INTERFACE**](../wdm/ns-wdm-_interface.md) structure that describes the KMCL interface exported by the Vmbuskmcl.sys bus driver.

The function pointers in **KMCL_CLIENT_INTERFACE_V1** are called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This structure contains function pointers for client functions. 

To access client functions of the KMCL interface, allocate a **KMCL_CLIENT_INTERFACE_V1** structure to receive the interface, then call either [**WdfFdoQueryForInterface**](../wdffdo/nf-wdffdo-wdffdoqueryforinterface.md) or [**WdfIoTargetQueryForInterface**](../wdfiotarget/nf-wdfiotarget-wdfiotargetqueryforinterface.md) with these parameters:
 
- *InterfaceType* parameter: **KMCL_CLIENT_INTERFACE_TYPE**
- *Size* parameter: `sizeof(KMCL_CLIENT_INTERFACE_V1)`
- *Version* parameter: **KMCL_CLIENT_INTERFACE_VERSION_V1** 

If the interface query function succeeds, the **KMCL_CLIENT_INTERFACE_V1** structure contains function pointers that you can use to call VMBus KMCL client functions.

For server-only methods, see the [**KMCL_SERVER_ONLY_METHODS**](ns-vmbuskernelmodeclientlibapi-_kmcl_server_only_methods.md) structure.

For more information about driver-defined interfaces, see [Using Driver-Defined Interfaces](https://docs.microsoft.com/windows-hardware/drivers/wdf/using-driver-defined-interfaces).

## -see-also

[Using Driver-Defined Interfaces](https://docs.microsoft.com/windows-hardware/drivers/wdf/using-driver-defined-interfaces)

[**WdfFdoQueryForInterface**](../wdffdo/nf-wdffdo-wdffdoqueryforinterface.md)

[**WdfIoTargetQueryForInterface**](../wdfiotarget/nf-wdfiotarget-wdfiotargetqueryforinterface.md)

[**KMCL_SERVER_ONLY_METHODS**](ns-vmbuskernelmodeclientlibapi-_kmcl_server_only_methods.md)
