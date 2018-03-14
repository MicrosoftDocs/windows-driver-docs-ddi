---
UID: NA:vmbuskernelmodeclientlibapi
ms.assetid: 2e84074c-95a8-364a-a58d-1b59a15a0e22
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Vmbuskernelmodeclientlibapi.h header



This header is used by Networking drivers for Windows Vista and later. For more information, see
- [Networking drivers for Windows Vista and later](../_netvista/index.md)

Vmbuskernelmodeclientlibapi.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT function](nf-vmbuskernelmodeclientlibapi-vmb_channel_state_change_callbacks_init.md) | The VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT function saves callback functions to be used for state changes for a channel. |
| [VmbChannelAllocate function](nf-vmbuskernelmodeclientlibapi-vmbchannelallocate.md) | The VmbChannelAllocate function allocates a new VMBus channel that has default parameters and callbacks. |
| [VmbChannelCleanup function](nf-vmbuskernelmodeclientlibapi-vmbchannelcleanup.md) | The VmbChannelCleanup function disposes of a channel that was allocated by using the VmbChannelAllocate function or initialized by using a VMBus channel initialization function. |
| [VmbChannelCreateGpadlFromBuffer function](nf-vmbuskernelmodeclientlibapi-vmbchannelcreategpadlfrombuffer.md) | The VmbChannelCreateGpadlFromBuffer function creates a Guest Physical Address Descriptor List (GPADL) that describes a client-side buffer. The GPADL can be used in the server to access the buffer. |
| [VmbChannelCreateGpadlFromMdl function](nf-vmbuskernelmodeclientlibapi-vmbchannelcreategpadlfrommdl.md) | The VmbChannelCreateGpadlFromMdl function creates a Guest Physical Address Descriptor List (GPADL) that describes a client-side buffer. The GPADL can be used in the server to access the buffer. |
| [VmbChannelDeleteGpadl function](nf-vmbuskernelmodeclientlibapi-vmbchanneldeletegpadl.md) | The VmbChannelDeleteGpadl function deletes a Guest Physical Address Descriptor List (GPADL) mapped by the VmbChannelCreateGpadlFromMdl or VmbChannelCreateGpadlFromBuffer functions. |
| [VmbChannelDisable function](nf-vmbuskernelmodeclientlibapi-vmbchanneldisable.md) | The VmbChannelDisable function disables a channel, which closes it for client channels and revokes the channel offer for server channels. This function waits until the channel is completely torn down before it returns. |
| [VmbChannelEnable function](nf-vmbuskernelmodeclientlibapi-vmbchannelenable.md) | The VmbChannelEnable function enables a channel that is in the disabled state by connecting to VMBus and offering or opening a channel, as appropriate for the endpoint type. |
| [VmbChannelGetInterfaceInstance function](nf-vmbuskernelmodeclientlibapi-vmbchannelgetinterfaceinstance.md) | The VmbChannelGetInterfaceInstance function gets the active interface instance, which is a GUID that uniquely identifies a channel. |
| [VmbChannelGetPointer function](nf-vmbuskernelmodeclientlibapi-vmbchannelgetpointer.md) | The VmbChannelGetPointer function lets a client driver retrieve a pointer that was previously saved by using the VmbPacketSetPointer function. |
| [VmbChannelInitSetClientContextSize function](nf-vmbuskernelmodeclientlibapi-vmbchannelinitsetclientcontextsize.md) | The VmbChannelInitSetClientContextSize function sets the size of the optional context area allocated for the client driver on each incoming packet. |
| [VmbChannelInitSetFlags function](nf-vmbuskernelmodeclientlibapi-vmbchannelinitsetflags.md) | The VmbChannelInitSetFlags function sets flags common to server or client channel endpoints. |
| [VmbChannelInitSetFriendlyName function](nf-vmbuskernelmodeclientlibapi-vmbchannelinitsetfriendlyname.md) | The VmbChannelInitSetFriendlyName function sets the friendly name of the Kernel Mode Client Library (KMCL) channel. The friendly name is used for debugging and performance counter instance naming. |
| [VmbChannelInitSetMaximumExternalData function](nf-vmbuskernelmodeclientlibapi-vmbchannelinitsetmaximumexternaldata.md) | The VmbChannelInitSetMaximumExternalData function sets the maximum size and chain length of data that is described by a packet, but not directly sent in the packet. That is, the maximum size of the buffer described by an ExternalDataMdl. |
| [VmbChannelInitSetMaximumPacketSize function](nf-vmbuskernelmodeclientlibapi-vmbchannelinitsetmaximumpacketsize.md) | The VmbChannelInitSetMaximumPacketSize function sets the maximum packet size that can be delivered through a channel, which is the maximum size that will ever be specified by the VmbPacketSend function. |
| [VmbChannelInitSetProcessPacketCallbacks function](nf-vmbuskernelmodeclientlibapi-vmbchannelinitsetprocesspacketcallbacks.md) | The VmbChannelInitSetProcessPacketCallbacks function sets callback functions for packet processing. |
| [VmbChannelInitSetStateChangeCallbacks function](nf-vmbuskernelmodeclientlibapi-vmbchannelinitsetstatechangecallbacks.md) | The VmbChannelInitSetStateChangeCallbacks function sets optional callback functions for state changes. |
| [VmbChannelMapGpadl function](nf-vmbuskernelmodeclientlibapi-vmbchannelmapgpadl.md) | The VmbChannelMapGpadl function maps a client-side buffer into server-side physical address space by using a Guest Physical Address Descriptor List (GPADL) number. |
| [VmbChannelPacketComplete function](nf-vmbuskernelmodeclientlibapi-vmbchannelpacketcomplete.md) | The VmbChannelPacketComplete function cleans up any outstanding memory mappings, releases any buffers in use, and, if the opposite endpoint requested a completion packet, sends a completion packet. |
| [VmbChannelPacketDeferToPassive function](nf-vmbuskernelmodeclientlibapi-vmbchannelpacketdefertopassive.md) | The VmbChannelPacketDeferToPassive function is called by the client driver to defer a packet passed to it by the EvtVmbChannelProcessPacket callback function. |
| [VmbChannelPacketFail function](nf-vmbuskernelmodeclientlibapi-vmbchannelpacketfail.md) | The VmbChannelPacketFail function fails a packet during packet processing due to an unrecoverable error. This function stops the queue. |
| [VmbChannelPacketGetExternalData function](nf-vmbuskernelmodeclientlibapi-vmbchannelpacketgetexternaldata.md) | The VmbChannelPacketGetExternalData function gets any external Memory Descriptor Lists (MDLs) associated with a packet during packet processing. |
| [VmbChannelPause function](nf-vmbuskernelmodeclientlibapi-vmbchannelpause.md) | The VmbChannelPause function moves a channel into the paused state, which prevents new I/O. |
| [VmbChannelRestoreFromBuffer function](nf-vmbuskernelmodeclientlibapi-vmbchannelrestorefrombuffer.md) | The VmbChannelRestoreFromBuffer function restores the client state from previously saved state. The driver must check the return value of the function. |
| [VmbChannelSaveBegin function](nf-vmbuskernelmodeclientlibapi-vmbchannelsavebegin.md) | The VmbChannelSaveBegin function initializes the context for saving the state of a channel. The driver must check the return value of the function. |
| [VmbChannelSaveContinue function](nf-vmbuskernelmodeclientlibapi-vmbchannelsavecontinue.md) | The VmbChannelSaveContinue function saves the channel state to a buffer. Run the VmbChannelSaveBegin before you run this function. The driver must check the return value of the function. |
| [VmbChannelSaveEnd function](nf-vmbuskernelmodeclientlibapi-vmbchannelsaveend.md) | The VmbChannelSaveEnd function cleans up any resources that were allocated for saving state of a channel. |
| [VmbChannelSendSynchronousRequest function](nf-vmbuskernelmodeclientlibapi-vmbchannelsendsynchronousrequest.md) | The VmbChannelSendSynchronousRequest function sends a packet to the opposite endpoint and waits for a response. |
| [VmbChannelSetIncomingProcessingAtPassive function](nf-vmbuskernelmodeclientlibapi-vmbchannelsetincomingprocessingatpassive.md) | The VmbChannelSetIncomingProcessingAtPassive function sets the required IRQL for incoming parsing routines for a channel to PASSIVE_LEVEL. |
| [VmbChannelSetPointer function](nf-vmbuskernelmodeclientlibapi-vmbchannelsetpointer.md) | The VmbChannelSetPointer function saves an arbitrary pointer in a channel context. |
| [VmbChannelSetTransactionQuota function](nf-vmbuskernelmodeclientlibapi-vmbchannelsettransactionquota.md) | The VmbChannelSetTransactionQuota function sets the incoming packet quota. |
| [VmbChannelSizeofPacket function](nf-vmbuskernelmodeclientlibapi-vmbchannelsizeofpacket.md) | The VmbChannelSizeofPacket function calculates the necessary size for buffers to be used with the VmbPacketInitialize function. |
| [VmbChannelStart function](nf-vmbuskernelmodeclientlibapi-vmbchannelstart.md) | The VmbChannelStart function moves a channel out of the paused state. |
| [VmbChannelUnmapGpadl function](nf-vmbuskernelmodeclientlibapi-vmbchannelunmapgpadl.md) | The VmbChannelUnmapGpadl function unmaps a Guest Physical Address Descriptor List (GPADL) mapped using by the VmbChannelMapGpadl function. The buffer must no longer be in use by the server before this function is called. |
| [VmbClientChannelInitSetRingBufferPageCount function](nf-vmbuskernelmodeclientlibapi-vmbclientchannelinitsetringbufferpagecount.md) | The VmbClientChannelInitSetRingBufferPageCount function sets the number of pages of memory the client allocates for incoming and outgoing ring buffers. |
| [VmbClientChannelInitSetTargetPnp function](nf-vmbuskernelmodeclientlibapi-vmbclientchannelinitsettargetpnp.md) | The VmbClientChannelInitSetTargetPnp function sets a client channel's target by interface type and instance IDs. |
| [VmbConvertVmbusHandleToKernelHandle function](nf-vmbuskernelmodeclientlibapi-vmbconvertvmbushandletokernelhandle.md) | The VmbConvertVmbusHandleToKernelHandle function converts the user mode VMBus handle to kernel mode handle. |
| [VmbPacketAllocate function](nf-vmbuskernelmodeclientlibapi-vmbpacketallocate.md) | The VmbPacketAllocate function allocates a packet from the channel's lookaside list. |
| [VmbPacketFree function](nf-vmbuskernelmodeclientlibapi-vmbpacketfree.md) | The VmbPacketFree function releases a packet allocated by using the VmbPacketAllocate function. |
| [VmbPacketGetChannel function](nf-vmbuskernelmodeclientlibapi-vmbpacketgetchannel.md) | The VmbPacketGetChannel function returns the VMBus channel with which a VMBus packet is associated. |
| [VmbPacketGetPointer function](nf-vmbuskernelmodeclientlibapi-vmbpacketgetpointer.md) | The VmbPacketGetPointer function retrieves a pointer that was previously saved by using the VmbPacketSetPointer function. |
| [VmbPacketInitialize function](nf-vmbuskernelmodeclientlibapi-vmbpacketinitialize.md) | The VmbPacketInitialize function initializes a buffer to contain a VMBus packet. |
| [VmbPacketRestore function](nf-vmbuskernelmodeclientlibapi-vmbpacketrestore.md) | The VmbPacketRestore function restores packet from a buffer that contains saved packet context. |
| [VmbPacketSend function](nf-vmbuskernelmodeclientlibapi-vmbpacketsend.md) | The VmbPacketSend function sends the data in a packet buffer or external data Memory Descriptor List (MDL). The function associates that data with the VMBus packet object, which represents the packet throughout the lifetime of the transaction. |
| [VmbPacketSendWithExternalMdl function](nf-vmbuskernelmodeclientlibapi-vmbpacketsendwithexternalmdl.md) | The VmbPacketSendWithExternalMdl function sends the data in a packet buffer or external data Memory Descriptor List (MDL). |
| [VmbPacketSendWithExternalPfns function](nf-vmbuskernelmodeclientlibapi-vmbpacketsendwithexternalpfns.md) | The VmbPacketSendWithExternalPfns function sends the data in a packet buffer or external data as an array of Page Frame Numbers (PFNs). |
| [VmbPacketSetCompletionRoutine function](nf-vmbuskernelmodeclientlibapi-vmbpacketsetcompletionroutine.md) | The VmbPacketSetCompletionRoutine function sets the completion routine for a packet object. |
| [VmbPacketSetPointer function](nf-vmbuskernelmodeclientlibapi-vmbpacketsetpointer.md) | The VmbPacketSetPointer function saves an arbitrary pointer in the packet context. |
| [VmbServerChannelInitSetFlags function](nf-vmbuskernelmodeclientlibapi-vmbserverchannelinitsetflags.md) | The VmbServerChannelInitSetFlags function sets flags unique to server channel endpoints. |
| [VmbServerChannelInitSetMmioMegabytes function](nf-vmbuskernelmodeclientlibapi-vmbserverchannelinitsetmmiomegabytes.md) | The VmbServerChannelInitSetMmioMegabytes function specifies the amount, in megabytes, of guest memory-mapped I/O (MMIO) space to reserve for the device. |
| [VmbServerChannelInitSetSaveRestorePacketCallbacks function](nf-vmbuskernelmodeclientlibapi-vmbserverchannelinitsetsaverestorepacketcallbacks.md) | The VmbServerChannelInitSetSaveRestorePacketCallbacks function sets the save and restore callback functions that are called for each packet when the driver calls a save function, such as VmbChannelSaveBegin, VmbChannelSaveContinue, and VmbChannelSaveEnd, or the VmbChannelRestoreFromBuffer function. |
| [VmbServerChannelInitSetTargetInterfaceId function](nf-vmbuskernelmodeclientlibapi-vmbserverchannelinitsettargetinterfaceid.md) | The VmbServerChannelInitSetTargetInterfaceId function sets the target interface type GUID and instance GUID of the channel offer. |
| [VmbServerChannelInitSetVmbusHandle function](nf-vmbuskernelmodeclientlibapi-vmbserverchannelinitsetvmbushandle.md) | The VmbServerChannelInitSetVmbusHandle function associates an instance of VMBus with this channel. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [EVT_VMB_CHANNEL_CLOSED callback](nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_closed.md) | The EvtVmbChannelClosed callback function is invoked when the client endpoint in the guest virtual machine closes a channel by using the VmbChannelDisable function, or the opposite endpoint rescinds or closes the channel. |
| [EVT_VMB_CHANNEL_OPENED callback](nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_opened.md) | The EvtVmbChannelOpened callback function is invoked when the client endpoint in the guest virtual machine opens a channel which has been offered to it. |
| [EVT_VMB_CHANNEL_PNP_FAILURE callback](nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_pnp_failure.md) | The EvtChannelPnpFailure callback function is invoked if the client endpoint in the guest virtual machine asynchronously fails to connect even though a PnP device was located. |
| [EVT_VMB_CHANNEL_POST_STARTED callback](nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_post_started.md) | The EvtVmbChannelPostStarted callback function is invoked at either endpoint after packets can be received from the opposite endpoint. |
| [EVT_VMB_CHANNEL_PROCESSING_COMPLETE callback](nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_processing_complete.md) | The EvtVmbChannelProcessingComplete callback function is invoked when a group of packets has been delivered by the EvtVmbChannelProcessPacket function, if there is a pause before delivering subsequent packets. |
| [EVT_VMB_CHANNEL_PROCESS_PACKET callback](nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_process_packet.md) | The EvtVmbChannelProcessPacket callback function is invoked when a packet arrives in the incoming ring buffer. |
| [EVT_VMB_CHANNEL_RESTORE_PACKET callback](nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_restore_packet.md) | The EvtVmbChannelRestorePacket callback function is invoked when the virtualization service provider (VSP) server endpoint must restore the state associated with a packet object. |
| [EVT_VMB_CHANNEL_SAVE_PACKET callback](nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_save_packet.md) | The EvtVmbChannelSavePacket callback function is invoked when the virtualization service provider (VSP) endpoint must save the state associated with a packet. |
| [EVT_VMB_CHANNEL_STARTED callback](nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_started.md) | The EvtVmbChannelStarted callback function is invoked at either endpoint when a channel is fully configured but before any packets have been delivered. This occurs when the opposite endpoint opened the channel or reopened it after closing it. |
| [EVT_VMB_CHANNEL_SUSPEND callback](nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_suspend.md) | The EvtVmbChannelSuspend callback function is invoked at the server endpoint when the channel is being closed or deleted by the client endpoint, which moves the server into the Stopped state. |
| [EVT_VMB_PACKET_COMPLETION_ROUTINE callback](nc-vmbuskernelmodeclientlibapi-evt_vmb_packet_completion_routine.md) | The EvtVmbPacketCompletionRoutine callback function is invoked when the transaction associated with a sent packet is complete. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_VMB_CHANNEL_STATE_CHANGE_CALLBACKS structure](ns-vmbuskernelmodeclientlibapi-_vmb_channel_state_change_callbacks.md) | The VMB_CHANNEL_STATE_CHANGE_CALLBACKS structure contains callback functions that relate to the state changes for a channel. |
