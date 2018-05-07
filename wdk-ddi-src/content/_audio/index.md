---
UID: TP:audio
ms.assetid: 91b97f1d-92f1-3c32-955a-dd6524d5b764
ms.author: windowsdriverdev
ms.date: 05/07/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Audio



Overview of the Audio technology.

To develop Audio, you need these headers:

 * [bthhfpddi.h](..\bthhfpddi\index.md)
 * [dmusicks.h](..\dmusicks\index.md)
 * [dmusprop.h](..\dmusprop\index.md)
 * [drmk.h](..\drmk\index.md)
 * [hdaudio.h](..\hdaudio\index.md)
 * [keyworddetectoroemadapter.h](..\keyworddetectoroemadapter\index.md)
 * [ksmedia.h](..\ksmedia\index.md)
 * [portcls.h](..\portcls\index.md)
 * [punknown.h](..\punknown\index.md)
 * [unknown.h](..\unknown\index.md)

For the programming guide, see [Audio](https://docs.microsoft.com/en-us/windows-hardware/drivers/audio).

## Functions

| Title   | Description   |
| ---- |:---- |
| [BTHHFP_AUDIO_DEVICE_CAPABILTIES_INIT function](..\bthhfpddi\nf-bthhfpddi-bthhfp_audio_device_capabilties_init.md) | The BTHHFP_AUDIO_DEVICE_CAPABILTIES_INIT method returns a pointer to an initialized BTHHFP_AUDIO_DEVICE_CAPABILTIES data structure. |
| [DrmAddContentHandlers function](..\drmk\nf-drmk-drmaddcontenthandlers.md) | The DrmAddContentHandlers function provides the system with a list of functions that handle protected content. |
| [DrmCreateContentMixed function](..\drmk\nf-drmk-drmcreatecontentmixed.md) | The DrmCreateContentMixed function creates a DRM content ID to identify a KS audio stream containing mixed content from a number of streams. |
| [DrmDestroyContent function](..\drmk\nf-drmk-drmdestroycontent.md) | The DrmDestroyContent function deletes a DRM content ID that was created by DrmCreateContentMixed. |
| [DrmForwardContentToDeviceObject function](..\drmk\nf-drmk-drmforwardcontenttodeviceobject.md) | The DrmForwardContentToDeviceObject function accepts a device object representing a device to which the caller intends to forward protected content. |
| [DrmForwardContentToFileObject function](..\drmk\nf-drmk-drmforwardcontenttofileobject.md) | The DrmForwardContentToFileObject function is obsolete and is maintained only to support existing drivers. |
| [DrmForwardContentToInterface function](..\drmk\nf-drmk-drmforwardcontenttointerface.md) | The DrmForwardContentToInterface function accepts a pointer to the COM interface of an object to which the caller intends to forward protected content. |
| [DrmGetContentRights function](..\drmk\nf-drmk-drmgetcontentrights.md) | The DrmGetContentRights function retrieves the DRM content rights assigned to a DRM content ID. |
| [PcAddAdapterDevice function](..\portcls\nf-portcls-pcaddadapterdevice.md) | The PcAddAdapterDevice function adds an adapter device to the WDM device stack. |
| [PcAddContentHandlers function](..\portcls\nf-portcls-pcaddcontenthandlers.md) | The PcAddContentHandlers function provides the system with a list of functions that handle protected content. |
| [PcAddStreamResource function](..\portcls\nf-portcls-pcaddstreamresource.md) | PcAddStreamResource adds a stream resource. |
| [PcCompleteIrp function](..\portcls\nf-portcls-pccompleteirp.md) | The PcCompleteIrp function completes an IRP that was previously marked as pending. |
| [PcCompletePendingPropertyRequest function](..\portcls\nf-portcls-pccompletependingpropertyrequest.md) | The PcCompletePendingPropertyRequest function is called to complete a pending property request. |
| [PcCreateContentMixed function](..\portcls\nf-portcls-pccreatecontentmixed.md) | The PcCreateContentMixed function computes the DRM content rights for a composite stream containing mixed content from some number of KS audio streams. |
| [PcDestroyContent function](..\portcls\nf-portcls-pcdestroycontent.md) | The PcDestroyContent function deletes a DRM content ID that was created by PcCreateContentMixed. Note that this function call is identical in operation to the DrmDestroyContent function, and its parameter definitions and return value are also identical. |
| [PcDispatchIrp function](..\portcls\nf-portcls-pcdispatchirp.md) | The PcDispatchIrp function dispatches an IRP to the PortCls system driver's default handler. |
| [PcForwardContentToDeviceObject function](..\portcls\nf-portcls-pcforwardcontenttodeviceobject.md) | The PcForwardContentToDeviceObject function accepts a device object representing a device to which the caller intends to forward protected content. |
| [PcForwardContentToFileObject function](..\portcls\nf-portcls-pcforwardcontenttofileobject.md) | The PcForwardContentToFileObject function is obsolete and is maintained only to support existing drivers. |
| [PcForwardContentToInterface function](..\portcls\nf-portcls-pcforwardcontenttointerface.md) | The PcForwardContentToInterface function accepts a pointer to the COM interface of an object to which the caller intends to forward protected content. |
| [PcForwardIrpSynchronous function](..\portcls\nf-portcls-pcforwardirpsynchronous.md) | The PcForwardIrpSynchronous function is used by IRP handlers to forward Plug and Play IRPs to the physical device object (PDO). |
| [PcGetContentRights function](..\portcls\nf-portcls-pcgetcontentrights.md) | The PcGetContentRights function retrieves the DRM content rights assigned to a DRM content ID. Note that this function call is identical in operation to the DrmGetContentRights function, and its parameter definitions and return value are also identical. |
| [PcGetDeviceProperty function](..\portcls\nf-portcls-pcgetdeviceproperty.md) | The PcGetDeviceProperty function returns the requested device property from the registry. |
| [PcGetPhysicalDeviceObject function](..\portcls\nf-portcls-pcgetphysicaldeviceobject.md) | The PcGetPhysicalDeviceObject function enables audio miniport drivers to retrieve the underlying physical device object of the audio device. |
| [PcGetTimeInterval function](..\portcls\nf-portcls-pcgettimeinterval.md) | The PcGetTimeInterval function returns the time elapsed since a specified time. Time is measured in 100-nanosecond units. |
| [PcInitializeAdapterDriver function](..\portcls\nf-portcls-pcinitializeadapterdriver.md) | The PcInitializeAdapterDriver function binds an adapter driver to the PortCls system driver. |
| [PcNewDmaChannel function](..\portcls\nf-portcls-pcnewdmachannel.md) | The PcNewDmaChannel function creates a new DMA-channel object. This function is obsolete; for more information, see the following comments. |
| [PcNewInterruptSync function](..\portcls\nf-portcls-pcnewinterruptsync.md) | The PcNewInterruptSync function creates and initializes an interrupt-synchronization object. |
| [PcNewMiniport function](..\portcls\nf-portcls-pcnewminiport.md) | The PcNewMiniport function creates an instance of one of the system-supplied miniport drivers that are built into the PortCls system driver, portcls.sys. |
| [PcNewPort function](..\portcls\nf-portcls-pcnewport.md) | The PcNewPort function creates a new system-supplied port-driver object, whose interface (derived from base class IPort) is specified by a class ID. |
| [PcNewRegistryKey function](..\portcls\nf-portcls-pcnewregistrykey.md) | The PcNewRegistryKey function opens or creates a new registry key and creates an IRegistryKey object to represent the key. The caller accesses the key through this object. |
| [PcNewResourceList function](..\portcls\nf-portcls-pcnewresourcelist.md) | The PcNewResourceList function creates and initializes a resource list. |
| [PcNewResourceSublist function](..\portcls\nf-portcls-pcnewresourcesublist.md) | The PcNewResourceSublist function creates and initializes an empty resource list that is derived from another resource list. |
| [PcNewServiceGroup function](..\portcls\nf-portcls-pcnewservicegroup.md) | The PcNewServiceGroup function creates and initializes a service group. |
| [PcRegisterAdapterPnpManagement function](..\portcls\nf-portcls-pcregisteradapterpnpmanagement.md) | The PcRegisterAdapterPnpManagement function registers the adapter's PnP-management interface with the PortCls system driver. It is used to support PnP rebalance. |
| [PcRegisterAdapterPowerManagement function](..\portcls\nf-portcls-pcregisteradapterpowermanagement.md) | The PcRegisterAdapterPowerManagement function registers the adapter's power-management interface with the PortCls system driver. |
| [PcRegisterIoTimeout function](..\portcls\nf-portcls-pcregisteriotimeout.md) | The PcRegisterIoTimeout function registers a driver-supplied I/O-timer callback routine for a specified device object. |
| [PcRegisterPhysicalConnection function](..\portcls\nf-portcls-pcregisterphysicalconnection.md) | The PcRegisterPhysicalConnection function registers a physical connection between two audio adapter filters that are instantiated by the same adapter driver. |
| [PcRegisterPhysicalConnectionFromExternal function](..\portcls\nf-portcls-pcregisterphysicalconnectionfromexternal.md) | The PcRegisterPhysicalConnectionFromExternal function registers a physical connection to an audio adapter filter from an external audio adapter filter. |
| [PcRegisterPhysicalConnectionToExternal function](..\portcls\nf-portcls-pcregisterphysicalconnectiontoexternal.md) | The PcRegisterPhysicalConnectionToExternal function registers a physical connection from an audio adapter filter to an external audio adapter filter. |
| [PcRegisterSubdevice function](..\portcls\nf-portcls-pcregistersubdevice.md) | The PcRegisterSubdevice function registers a subdevice to make it available for use by clients. |
| [PcRemoveStreamResource function](..\portcls\nf-portcls-pcremovestreamresource.md) | PcRemoveStreamResource removes an existing stream resource. |
| [PcRequestNewPowerState function](..\portcls\nf-portcls-pcrequestnewpowerstate.md) | The PcRequestNewPowerState function is used to request a new power state for the device. This function is typically not needed by adapter drivers but can occasionally be useful in working around some kinds of hardware problems. |
| [PcUnregisterAdapterPnpManagement function](..\portcls\nf-portcls-pcunregisteradapterpnpmanagement.md) | The PcUnregisterAdapterPnpManagement function unregisters the audio adapter's PnP management interface from the PortCls class driver. It is used to support PnP rebalance. |
| [PcUnregisterAdapterPowerManagement function](..\portcls\nf-portcls-pcunregisteradapterpowermanagement.md) | The PcUnregisterAdapterPowerManagement function unregisters the audio adapter's power management interface from the PortCls class driver. The PcUnregisterAdapterPowerManagement function is available in Windows 7 and later versions of Windows. |
| [PcUnregisterIoTimeout function](..\portcls\nf-portcls-pcunregisteriotimeout.md) | The PcUnregisterIoTimeout function unregisters a driver-supplied I/O-timer callback routine for a specified device object. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [PALLOCATE_CAPTURE_DMA_ENGINE callback](..\hdaudio\nc-hdaudio-pallocate_capture_dma_engine.md) | The AllocateCaptureDmaEngine routine allocates a DMA engine for a capture stream.The function pointer type for an AllocateCaptureDmaEngine routine is defined as follows. |
| [PALLOCATE_CONTIGUOUS_DMA_BUFFER callback](..\hdaudio\nc-hdaudio-pallocate_contiguous_dma_buffer.md) | The AllocateContiguousDmaBuffer routine allocates a DMA buffer that consists of a single, contiguous block of physical memory.The function pointer type for an AllocateContiguousDmaBuffer routine is defined as follows. |
| [PALLOCATE_DMA_BUFFER callback](..\hdaudio\nc-hdaudio-pallocate_dma_buffer.md) | The AllocateDmaBuffer routine allocates a data buffer in system memory for a DMA engine.The function pointer type for an AllocateDmaBuffer routine is defined as follows. |
| [PALLOCATE_DMA_BUFFER_WITH_NOTIFICATION callback](..\hdaudio\nc-hdaudio-pallocate_dma_buffer_with_notification.md) | The AllocateDmaBufferWithNotification routine allocates a data buffer in system memory for a DMA engine.The function pointer type for an AllocateDmaBufferWithNotification routine is defined as follows. |
| [PALLOCATE_RENDER_DMA_ENGINE callback](..\hdaudio\nc-hdaudio-pallocate_render_dma_engine.md) | The AllocateRenderDmaEngine routine allocates a DMA engine for a render stream.The function pointer type for an AllocateRenderDmaEngine routine is defined as follows. |
| [PCHANGE_BANDWIDTH_ALLOCATION callback](..\hdaudio\nc-hdaudio-pchange_bandwidth_allocation.md) | The ChangeBandwidthAllocation routine changes a DMA engine's bandwidth allocation on the HD Audio Link.The function pointer type for a ChangeBandwidthAllocation routine is defined as follows. |
| [PCPFNEVENT_HANDLER callback](..\portcls\nc-portcls-pcpfnevent_handler.md) | An EventHandler routine processes event requests. |
| [PFNDRMADDCONTENTHANDLERS callback](..\drmk\nc-drmk-pfndrmaddcontenthandlers.md) | This callback function is reserved for system use. |
| [PFNDRMCREATECONTENTMIXED callback](..\drmk\nc-drmk-pfndrmcreatecontentmixed.md) | This callback function is reserved for system use. |
| [PFNDRMDESTROYCONTENT callback](..\drmk\nc-drmk-pfndrmdestroycontent.md) | This callback function is reserved for system use. |
| [PFNDRMFORWARDCONTENTTODEVICEOBJECT callback](..\drmk\nc-drmk-pfndrmforwardcontenttodeviceobject.md) | This callback function is reserved for system use. |
| [PFNDRMFORWARDCONTENTTOFILEOBJECT callback](..\drmk\nc-drmk-pfndrmforwardcontenttofileobject.md) | This callback function is reserved for system use. |
| [PFNDRMFORWARDCONTENTTOINTERFACE callback](..\drmk\nc-drmk-pfndrmforwardcontenttointerface.md) | This callback function is reserved for system use. |
| [PFNDRMGETCONTENTRIGHTS callback](..\drmk\nc-drmk-pfndrmgetcontentrights.md) | This callback function is reserved for system use. |
| [PFREE_CONTIGUOUS_DMA_BUFFER callback](..\hdaudio\nc-hdaudio-pfree_contiguous_dma_buffer.md) | The FreeContiguousDmaBuffer routine frees a DMA buffer and buffer descriptor list (BDL) that were allocated by a call to AllocateContiguousDmaBuffer.The function pointer type for a FreeContiguousDmaBuffer routine is defined as follows. |
| [PFREE_DMA_BUFFER callback](..\hdaudio\nc-hdaudio-pfree_dma_buffer.md) | The FreeDmaBuffer routine frees a DMA buffer that was previously allocated by a call to AllocateDmaBuffer.The function pointer type for a FreeDmaBuffer routine is defined as follows. |
| [PFREE_DMA_BUFFER_WITH_NOTIFICATION callback](..\hdaudio\nc-hdaudio-pfree_dma_buffer_with_notification.md) | The FreeDmaBufferWithNotification routine frees a DMA buffer that was previously allocated by a call to AllocateDmaBufferWithNotification.The function pointer type for a FreeDmaBufferWithNotification routine is defined as follows. |
| [PFREE_DMA_ENGINE callback](..\hdaudio\nc-hdaudio-pfree_dma_engine.md) | The FreeDmaEngine routine frees a DMA engine that was previously allocated by a call to AllocateCaptureDmaEngine or AllocateRenderDmaEngine.The function pointer type for a FreeDmaEngine routine is defined as follows. |
| [PGET_DEVICE_INFORMATION callback](..\hdaudio\nc-hdaudio-pget_device_information.md) | The GetDeviceInformation routine retrieves information about the HD Audio controller device.The function pointer type for a GetDeviceInformation routine is defined as follows. |
| [PGET_LINK_POSITION_REGISTER callback](..\hdaudio\nc-hdaudio-pget_link_position_register.md) | The GetLinkPositionRegister routine retrieves a pointer to a DMA engine's link position register.The function pointer type for a GetLinkPositionRegister routine is defined as follows. |
| [PGET_RESOURCE_INFORMATION callback](..\hdaudio\nc-hdaudio-pget_resource_information.md) | The GetResourceInformation routine retrieves information about hardware resources.The function pointer type for a GetResourceInformation routine is defined as follows. |
| [PGET_WALL_CLOCK_REGISTER callback](..\hdaudio\nc-hdaudio-pget_wall_clock_register.md) | The GetWallClockRegister routine retrieves a pointer to the wall clock register.The function pointer type for a GetWallClockRegister routine is defined as follows. |
| [PHDAUDIO_BDL_ISR callback](..\hdaudio\nc-hdaudio-phdaudio_bdl_isr.md) | The HDAudioBdlIsr routine is the ISR that the HD Audio bus driver calls each time an IOC interrupt occurs on the stream. It is a function pointer of type PHDAUDIO_BDL_ISR, which is defined as follows. |
| [PHDAUDIO_TRANSFER_COMPLETE_CALLBACK callback](..\hdaudio\nc-hdaudio-phdaudio_transfer_complete_callback.md) | HDAudio codec transfer complete callback function. PHDAUDIO_TRANSFER_COMPLETE_CALLBACK is used by the PTRANSFER_CODEC_VERBS callback function. |
| [PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK callback](..\hdaudio\nc-hdaudio-phdaudio_unsolicited_response_callback.md) | HDAudio codec unsolicited response callback function. PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK is used by the PREGISTER_EVENT_CALLBACK callback function. |
| [PREGISTER_EVENT_CALLBACK callback](..\hdaudio\nc-hdaudio-pregister_event_callback.md) | The RegisterEventCallback routine registers a callback routine for an unsolicited response from a codec or codecs.The function pointer type for a RegisterEventCallback routine is defined as follows. |
| [PREGISTER_NOTIFICATION_EVENT callback](..\hdaudio\nc-hdaudio-pregister_notification_event.md) | The RegisterNotificationEvent routine registers a kernel event so that it can receive DMA progress notifications.The function pointer type for a RegisterNotificationEvent routine is defined as follows. |
| [PSETUP_DMA_ENGINE_WITH_BDL callback](..\hdaudio\nc-hdaudio-psetup_dma_engine_with_bdl.md) | The SetupDmaEngineWithBdl routine sets up a DMA engine to use a caller-allocated DMA buffer.The function pointer type for a SetupDmaEngineWithBdl routine is defined as follows. |
| [PSET_DMA_ENGINE_STATE callback](..\hdaudio\nc-hdaudio-pset_dma_engine_state.md) | The SetDmaEngineState routine sets the state of one or more DMA engines to the Running, Stopped, Paused, or Reset state.The function pointer type for a SetDmaEngineState routine is defined as follows. |
| [PTRANSFER_CODEC_VERBS callback](..\hdaudio\nc-hdaudio-ptransfer_codec_verbs.md) | The TransferCodecVerbs routine transfers one or more commands to a codec or codecs and retrieves the responses to those commands.The function pointer type for a TransferCodecVerbs routine is defined as follows. |
| [PUNREGISTER_EVENT_CALLBACK callback](..\hdaudio\nc-hdaudio-punregister_event_callback.md) | The UnregisterEventCallback routine deletes the registration of an event callback that was previously registered by a call to RegisterEventCallback.The function pointer type for an UnregisterEventCallback routine is defined as follows. |
| [PUNREGISTER_NOTIFICATION_EVENT callback](..\hdaudio\nc-hdaudio-punregister_notification_event.md) | The UnregisterNotificationEvent routine deletes the registration of an event that was previously registered by a call to RegisterNotificationEvent.The function pointer type for an UnregisterNotificationEvent routine is defined as follows. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [*PPCMETHOD_ITEM structure](..\portcls\ns-portcls-__unnamed_struct_0c93_4.md) | The PCMETHOD_ITEM structure describes a method supported by a filter, pin, or node. |
| [*PPCMETHOD_ITEM structure](..\portcls\ns-portcls-__unnamed_struct_0cec_4.md) | The PCMETHOD_ITEM structure describes a method supported by a filter, pin, or node. |
| [*PPCNODE_DESCRIPTOR structure](..\portcls\ns-portcls-__unnamed_struct_0c93_8.md) | The PCNODE_DESCRIPTOR structure describes a node in the filter that a topology miniport driver implements. |
| [*PPCNODE_DESCRIPTOR structure](..\portcls\ns-portcls-__unnamed_struct_0cec_8.md) | The PCNODE_DESCRIPTOR structure describes a node in the filter that a topology miniport driver implements. |
| [*PPCPIN_DESCRIPTOR structure](..\portcls\ns-portcls-__unnamed_struct_0c93_7.md) | The PCPIN_DESCRIPTOR structure describes a pin factory. |
| [*PPCPIN_DESCRIPTOR structure](..\portcls\ns-portcls-__unnamed_struct_0cec_7.md) | The PCPIN_DESCRIPTOR structure describes a pin factory. |
| [KSAC3_ALTERNATE_AUDIO structure](..\ksmedia\ns-ksmedia-ksac3_alternate_audio.md) | The KSAC3_ALTERNATE_AUDIO structure specifies whether the two mono channels in an AC-3-encoded stream should be interpreted as a stereo pair or as two independent program channels. |
| [KSAC3_BIT_STREAM_MODE structure](..\ksmedia\ns-ksmedia-ksac3_bit_stream_mode.md) | The KSAC3_BIT_STREAM_MODE structure specifies the bit-stream mode, which is the type of audio service that is encoded into an AC-3 stream. |
| [KSAC3_DIALOGUE_LEVEL structure](..\ksmedia\ns-ksmedia-ksac3_dialogue_level.md) | The KSAC3_DIALOGUE_LEVEL structure specifies the average volume level of spoken dialog within the audio program encoded in an AC-3 stream. |
| [KSAC3_DOWNMIX structure](..\ksmedia\ns-ksmedia-ksac3_downmix.md) | The KSAC3_DOWNMIX structure specifies whether the program channels in an AC-3-encoded stream need to be downmixed to accommodate the speaker configuration. |
| [KSAC3_ERROR_CONCEALMENT structure](..\ksmedia\ns-ksmedia-ksac3_error_concealment.md) | The KSAC3_ERROR_CONCEALMENT structure specifies how errors in an AC-3-encoded stream should be concealed during playback. |
| [KSAC3_ROOM_TYPE structure](..\ksmedia\ns-ksmedia-ksac3_room_type.md) | The KSAC3_ROOM_TYPE structure specifies the type of audio mixing room in which an AC-3-encoded stream was produced. |
| [KSAUDIO_CHANNEL_CONFIG structure](..\ksmedia\ns-ksmedia-ksaudio_channel_config.md) | The KSAUDIO_CHANNEL_CONFIG structure specifies the configuration of channels within the data format of an audio stream. |
| [KSAUDIO_COPY_PROTECTION structure](..\ksmedia\ns-ksmedia-ksaudio_copy_protection.md) | The KSAUDIO_COPY_PROTECTION structure specifies the copy-protection status of an audio stream. |
| [KSAUDIO_DYNAMIC_RANGE structure](..\ksmedia\ns-ksmedia-ksaudio_dynamic_range.md) | The KSAUDIO_DYNAMIC_RANGE structure specifies the dynamic range of an audio stream. This structure is used to get or set the data value for the KSPROPERTY_AUDIO_DYNAMIC_RANGE property. |
| [KSAUDIO_MICROPHONE_COORDINATES structure](..\ksmedia\ns-ksmedia-ksaudio_microphone_coordinates.md) | The KSAUDIO_MICROPHONE_COORDINATES structure specifies the type and the coordinates of a single microphone in the microphone array. |
| [KSAUDIO_MIC_ARRAY_GEOMETRY structure](..\ksmedia\ns-ksmedia-ksaudio_mic_array_geometry.md) | The KSAUDIO_MIC_ARRAY_GEOMETRY structure specifies the type and the geometry of the microphone array. |
| [KSAUDIO_MIXCAP_TABLE structure](..\ksmedia\ns-ksmedia-ksaudio_mixcap_table.md) | The KSAUDIO_MIXCAP_TABLE structure specifies the mixing capabilities of a supermixer node (KSNODETYPE_SUPERMIX). This structure is used to get or set the data value for the KSPROPERTY_AUDIO_MIX_LEVEL_CAPS property. |
| [KSAUDIO_MIXLEVEL structure](..\ksmedia\ns-ksmedia-ksaudio_mixlevel.md) | The KSAUDIO_MIXLEVEL structure specifies the mixing level of an input-output path in a supermixer node (KSNODETYPE_SUPERMIX). |
| [KSAUDIO_MIX_CAPS structure](..\ksmedia\ns-ksmedia-ksaudio_mix_caps.md) | The KSAUDIO_MIX_CAPS structure specifies the mixing capabilities of a particular data path from one input channel of a supermixer node (KSNODETYPE_SUPERMIX) to an output channel of the same node. |
| [KSAUDIO_POSITION structure](..\ksmedia\ns-ksmedia-ksaudio_position.md) | The KSAUDIO_POSITION structure specifies the current positions of the play and write cursors in the sound buffer for an audio stream. |
| [KSAUDIO_POSITIONEX structure](..\ksmedia\ns-ksmedia-ksaudio_positionex.md) | The KSAUDIO_POSITIONEX structure specifies the stream position and the associated timestamp information for a kernel streaming (KS)-based audio driver. |
| [KSAUDIO_PREFERRED_STATUS structure](..\ksmedia\ns-ksmedia-ksaudio_preferred_status.md) | The KSAUDIO_PREFERRED_STATUS structure specifies the status of a preferred device. |
| [KSAUDIO_PRESENTATION_POSITION structure](..\ksmedia\ns-ksmedia-ksaudio_presentation_position.md) | The KSAUDIO_PRESENTATION_POSITION structure specifies the current cursor position in audio data stream that is being rendered to the endpoint. |
| [KSDATAFORMAT_DSOUND structure](..\ksmedia\ns-ksmedia-ksdataformat_dsound.md) | The KSDATAFORMAT_DSOUND structure provides detailed information about a DirectSound audio stream. |
| [KSDATAFORMAT_WAVEFORMATEX structure](..\ksmedia\ns-ksmedia-ksdataformat_waveformatex.md) | The KSDATAFORMAT_WAVEFORMATEX structure provides detailed information about the data format of an audio stream consisting of wave data. |
| [KSDATARANGE_AUDIO structure](..\ksmedia\ns-ksmedia-ksdatarange_audio.md) | The KSDATARANGE_AUDIO structure specifies a range of audio formats. |
| [KSDATARANGE_MUSIC structure](..\ksmedia\ns-ksmedia-ksdatarange_music.md) | The KSDATARANGE_MUSIC structure specifies a range of DirectMusic MIDI formats. |
| [KSDRMAUDIOSTREAM_CONTENTID structure](..\drmk\ns-drmk-ksdrmaudiostream_contentid.md) | The KSDRMAUDIOSTREAM_CONTENTID structure specifies the DRM content ID and DRM content rights for a KSPROPERTY_DRMAUDIOSTREAM_CONTENTIDset-property request. |
| [KSDS3D_BUFFER_ALL structure](..\ksmedia\ns-ksmedia-ksds3d_buffer_all.md) | The KSDS3D_BUFFER_ALL structure specifies all the 3D characteristics of a DirectSound 3D buffer. |
| [KSDS3D_BUFFER_CONE_ANGLES structure](..\ksmedia\ns-ksmedia-ksds3d_buffer_cone_angles.md) | A KSDS3D_BUFFER_CONE_ANGLES structure specifies the inside and outside cone angles. |
| [KSDS3D_HRTF_FILTER_FORMAT_MSG structure](..\ksmedia\ns-ksmedia-ksds3d_hrtf_filter_format_msg.md) | The KSDS3D_HRTF_FILTER_FORMAT_MSG structure specifies the filter format to use for a head-relative transfer function (HRTF). |
| [KSDS3D_HRTF_INIT_MSG structure](..\ksmedia\ns-ksmedia-ksds3d_hrtf_init_msg.md) | The KSDS3D_HRTF_INIT_MSG structure specifies the parameter settings to use to initialize the head-relative transfer function (HRTF). |
| [KSDS3D_HRTF_PARAMS_MSG structure](..\ksmedia\ns-ksmedia-ksds3d_hrtf_params_msg.md) | The KSDS3D_HRTF_PARAMS_MSG structure specifies the parameter settings to apply to a head-relative transfer function (HRTF). |
| [KSDS3D_ITD_PARAMS structure](..\ksmedia\ns-ksmedia-ksds3d_itd_params.md) | The KSDS3D_ITD_PARAMS structure specifies the parameters applied by the interaural time delay (ITD) algorithm to the left or right channel in a 3D node (KSNODETYPE_3D_EFFECTS). |
| [KSDS3D_ITD_PARAMS_MSG structure](..\ksmedia\ns-ksmedia-ksds3d_itd_params_msg.md) | The KSDS3D_ITD_PARAMS_MSG structure specifies the parameters used by the interaural time delay (ITD) algorithm in a 3D node (KSNODETYPE_3D_EFFECTS). |
| [KSDS3D_LISTENER_ALL structure](..\ksmedia\ns-ksmedia-ksds3d_listener_all.md) | The KSDS3D_LISTENER_ALL structure specifies all the properties of the DirectSound 3D listener. This structure is used to get or set the data value for the KSPROPERTY_DIRECTSOUND3DLISTENER_ALL property. |
| [KSDS3D_LISTENER_ORIENTATION structure](..\ksmedia\ns-ksmedia-ksds3d_listener_orientation.md) | A KSD3D_LISTENER_ORIENTATION structure specifies the position vector of the 3D listener. This structure is used to get or set the data value for the KSPROPERTY_DIRECTSOUND3DLISTENER_ORIENTATION property. |
| [KSDSOUND_BUFFERDESC structure](..\ksmedia\ns-ksmedia-ksdsound_bufferdesc.md) | The KSDSOUND_BUFFERDESC structure describes a DirectSound buffer. |
| [KSMUSICFORMAT structure](..\ksmedia\ns-ksmedia-ksmusicformat.md) | The KSMUSICFORMAT structure is used to send and receive information about MIDI data that is input from and output to WDM audio devices. |
| [KSNODEPROPERTY structure](..\ksmedia\ns-ksmedia-ksnodeproperty.md) | The KSNODEPROPERTY structure specifies a node and a property of that node. |
| [KSNODEPROPERTY_AUDIO_CHANNEL structure](..\ksmedia\ns-ksmedia-ksnodeproperty_audio_channel.md) | The KSNODEPROPERTY_AUDIO_CHANNEL structure specifies a property of a channel in a node. |
| [KSP_DRMAUDIOSTREAM_CONTENTID structure](..\drmk\ns-drmk-ksp_drmaudiostream_contentid.md) | The KSP_DRMAUDIOSTREAM_CONTENTID structure specifies the property, request type, and context for a KSPROPERTY_DRMAUDIOSTREAM_CONTENTIDset-property request. It also specifies a list of function pointers to the DRM functions. |
| [KSRTAUDIO_BUFFER structure](..\ksmedia\ns-ksmedia-ksrtaudio_buffer.md) | The KSRTAUDIO_BUFFER structure specifies the buffer address, size, and a call memory barrier flag for a cyclic audio data buffer. |
| [KSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION structure](..\ksmedia\ns-ksmedia-ksrtaudio_buffer_property_with_notification.md) | The KSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION structure appends a buffer base address, a requested buffer size, and a notification count to a KSPROPERTY structure. |
| [KSRTAUDIO_GETREADPACKET_INFO structure](..\ksmedia\ns-ksmedia-ksrtaudio_getreadpacket_info.md) | The KSRTAUDIO_GETREADPACKET_INFO structure describes information for an audio packet. |
| [KSRTAUDIO_HWLATENCY structure](..\ksmedia\ns-ksmedia-ksrtaudio_hwlatency.md) | The KSRTAUDIO_HWLATENCY structure describes the latency that the audio hardware adds to a wave stream during playback or recording. |
| [KSRTAUDIO_HWREGISTER structure](..\ksmedia\ns-ksmedia-ksrtaudio_hwregister.md) | The KSRTAUDIO_HWREGISTER structure specifies the address and additional information about a hardware register requested by the client. |
| [KSRTAUDIO_HWREGISTER_PROPERTY structure](..\ksmedia\ns-ksmedia-ksrtaudio_hwregister_property.md) | The KSRTAUDIO_HWREGISTRY_PROPERTY structure appends a register base address to a KSPROPERTY structure. |
| [KSRTAUDIO_NOTIFICATION_EVENT_PROPERTY structure](..\ksmedia\ns-ksmedia-ksrtaudio_notification_event_property.md) | The KSRTAUDIO_NOTIFICATION_EVENT_PROPERTY structure appends an event handle to a KSPROPERTY structure |
| [KSRTAUDIO_SETWRITEPACKET_INFO structure](..\ksmedia\ns-ksmedia-ksrtaudio_setwritepacket_info.md) | The KSRTAUDIO_SETWRITEPACKET_INFO structure describes information associated with an audio packet. |
| [LOOPEDSTREAMING_POSITION_EVENT_DATA structure](..\ksmedia\ns-ksmedia-loopedstreaming_position_event_data.md) | The LOOPEDSTREAMING_POSITION_EVENT_DATA structure describes a position event in a looped buffer. |
| [PCAUTOMATION_TABLE structure](..\portcls\ns-portcls-__unnamed_struct_0c93_6.md) | The PCAUTOMATION_TABLE structure contains a miniport driver's master table of properties, methods, and events. |
| [PCAUTOMATION_TABLE structure](..\portcls\ns-portcls-__unnamed_struct_0cb6_6.md) | The PCAUTOMATION_TABLE structure contains a miniport driver's master table of properties, methods, and events. |
| [PCAUTOMATION_TABLE structure](..\portcls\ns-portcls-__unnamed_struct_0cec_6.md) | The PCAUTOMATION_TABLE structure contains a miniport driver's master table of properties, methods, and events. |
| [PCAUTOMATION_TABLE structure](..\portcls\ns-portcls-__unnamed_struct_3.md) | The PCAUTOMATION_TABLE structure contains a miniport driver's master table of properties, methods, and events. |
| [PCEVENT_ITEM structure](..\portcls\ns-portcls-__unnamed_struct_0c93_5.md) | The PCEVENT_ITEM structure is used to describe an event that is supported by a particular filter, pin, or node. |
| [PCEVENT_ITEM structure](..\portcls\ns-portcls-__unnamed_struct_0cb6_5.md) | The PCEVENT_ITEM structure is used to describe an event that is supported by a particular filter, pin, or node. |
| [PCEVENT_ITEM structure](..\portcls\ns-portcls-__unnamed_struct_0cec_5.md) | The PCEVENT_ITEM structure is used to describe an event that is supported by a particular filter, pin, or node. |
| [PCEVENT_ITEM structure](..\portcls\ns-portcls-__unnamed_struct_2.md) | The PCEVENT_ITEM structure is used to describe an event that is supported by a particular filter, pin, or node. |
| [PCFILTER_DESCRIPTOR structure](..\portcls\ns-portcls-__unnamed_struct_0c93_9.md) | The PCFILTER_DESCRIPTOR structure describes a miniport driver's implementation of a filter. The structure specifies the filter's pins, nodes, connections, and properties. |
| [PCFILTER_DESCRIPTOR structure](..\portcls\ns-portcls-__unnamed_struct_0cb6_9.md) | The PCFILTER_DESCRIPTOR structure describes a miniport driver's implementation of a filter. The structure specifies the filter's pins, nodes, connections, and properties. |
| [PCFILTER_DESCRIPTOR structure](..\portcls\ns-portcls-__unnamed_struct_0cec_9.md) | The PCFILTER_DESCRIPTOR structure describes a miniport driver's implementation of a filter. The structure specifies the filter's pins, nodes, connections, and properties. |
| [PCFILTER_DESCRIPTOR structure](..\portcls\ns-portcls-__unnamed_struct_6.md) | The PCFILTER_DESCRIPTOR structure describes a miniport driver's implementation of a filter. The structure specifies the filter's pins, nodes, connections, and properties. |
| [PCMETHOD_ITEM structure](..\portcls\ns-portcls-__unnamed_struct_0cb6_4.md) | The PCMETHOD_ITEM structure describes a method supported by a filter, pin, or node. |
| [PCMETHOD_ITEM structure](..\portcls\ns-portcls-__unnamed_struct_1.md) | The PCMETHOD_ITEM structure describes a method supported by a filter, pin, or node. |
| [PCNODE_DESCRIPTOR structure](..\portcls\ns-portcls-__unnamed_struct_0cb6_8.md) | The PCNODE_DESCRIPTOR structure describes a node in the filter that a topology miniport driver implements. |
| [PCNODE_DESCRIPTOR structure](..\portcls\ns-portcls-__unnamed_struct_5.md) | The PCNODE_DESCRIPTOR structure describes a node in the filter that a topology miniport driver implements. |
| [PCPIN_DESCRIPTOR structure](..\portcls\ns-portcls-__unnamed_struct_0cb6_7.md) | The PCPIN_DESCRIPTOR structure describes a pin factory. |
| [PCPIN_DESCRIPTOR structure](..\portcls\ns-portcls-__unnamed_struct_4.md) | The PCPIN_DESCRIPTOR structure describes a pin factory. |
| [PCPROPERTY_ITEM structure](..\portcls\ns-portcls-__unnamed_struct_0.md) | The PCPROPERTY_ITEM structure describes a property that is supported by a particular filter, pin, or node. |
| [PCPROPERTY_ITEM structure](..\portcls\ns-portcls-__unnamed_struct_0c93_3.md) | The PCPROPERTY_ITEM structure describes a property that is supported by a particular filter, pin, or node. |
| [PCPROPERTY_ITEM structure](..\portcls\ns-portcls-__unnamed_struct_0cb6_3.md) | The PCPROPERTY_ITEM structure describes a property that is supported by a particular filter, pin, or node. |
| [PCPROPERTY_ITEM structure](..\portcls\ns-portcls-__unnamed_struct_0cec_3.md) | The PCPROPERTY_ITEM structure describes a property that is supported by a particular filter, pin, or node. |
| [SOUNDDETECTOR_PATTERNHEADER structure](..\ksmedia\ns-ksmedia-sounddetector_patternheader.md) | The SOUNDDETECTOR_PATTERNHEADER structure specifies the pattern header for the sound detector in the KSPROPERTY_SOUNDDETECTOR_PATTERNS property. |
| [SYSAUDIO_ATTACH_VIRTUAL_SOURCE structure](..\ksmedia\ns-ksmedia-sysaudio_attach_virtual_source.md) | The SYSAUDIO_ATTACH_VIRTUAL_SOURCE structure is used to attach a mixer-line virtual source (for example, a volume or mute control) to a mixer pin on the virtual audio device. |
| [SYSAUDIO_CREATE_VIRTUAL_SOURCE structure](..\ksmedia\ns-ksmedia-sysaudio_create_virtual_source.md) | The SYSAUDIO_CREATE_VIRTUAL_SOURCE structure is used to create a mixer-line virtual source such as a volume control or mute. |
| [SYSAUDIO_INSTANCE_INFO structure](..\ksmedia\ns-ksmedia-sysaudio_instance_info.md) | The SYSAUDIO_INSTANCE_INFO structure specifies which virtual audio device to open and includes flags for configuring that device. |
| [SYSAUDIO_SELECT_GRAPH structure](..\ksmedia\ns-ksmedia-sysaudio_select_graph.md) | The SYSAUDIO_SELECT_GRAPH structure is used to specify a graph that includes an optional node such as an AEC control. |
| [WAVEFORMATEXTENSIBLE structure](..\ksmedia\ns-ksmedia-waveformatextensible.md) | The WAVEFORMATEXTENSIBLE structure specifies the format of an audio wave stream. |
| [_BTHHFP_AUDIO_DEVICE_CAPABILTIES structure](..\bthhfpddi\ns-bthhfpddi-_bthhfp_audio_device_capabilties.md) | The BTHHFP_AUDIO_DEVICE_CAPABILTIES data structure describes the capabilities of a Bluetooth HFP device, including the version and whether it supports 16 kHz sampling. |
| [_BTHHFP_DESCRIPTOR structure](..\bthhfpddi\ns-bthhfpddi-_bthhfp_descriptor.md) | The BTHHFP_DESCRIPTOR data structure stores information describing a paired Handsfree profile (HFP) device. |
| [_BTHHFP_DESCRIPTOR2 structure](..\bthhfpddi\ns-bthhfpddi-_bthhfp_descriptor2.md) | The BTHHFP_DESCRIPTOR2 data structure stores information describing a paired Handsfree profile (HFP) device. |
| [_DMUS_KERNEL_EVENT structure](..\dmusicks\ns-dmusicks-_dmus_kernel_event.md) | The DMUS_KERNEL_EVENT structure is used to package time-stamped music events. |
| [_DS3DVECTOR structure](..\ksmedia\ns-ksmedia-_ds3dvector.md) | The DS3DVECTOR structure contains three-dimensional position coordinates, position vector components, or velocity vector components. |
| [_HDAUDIO_BUFFER_DESCRIPTOR structure](..\hdaudio\ns-hdaudio-_hdaudio_buffer_descriptor.md) | The HDAUDIO_BUFFER_DESCRIPTOR structure specifies a buffer descriptor, which is an entry in a buffer descriptor list (BDL). |
| [_HDAUDIO_BUS_INTERFACE structure](..\hdaudio\ns-hdaudio-_hdaudio_bus_interface.md) | The HDAUDIO_BUS_INTERFACE structure specifies the information that a client requires to call the routines in the HDAUDIO_BUS_INTERFACE version of the HD Audio DDI. Another variant of this DDI is specified by the HDAUDIO_BUS_INTERFACE_BDL structure. |
| [_HDAUDIO_BUS_INTERFACE_BDL structure](..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_bdl.md) | The HDAUDIO_BUS_INTERFACE_BDL structure specifies the information that a client requires to call the routines in the HDAUDIO_BUS_INTERFACE_BDL version of the HD Audio DDI. Another variant of this DDI is specified by the HDAUDIO_BUS_INTERFACE structure. |
| [_HDAUDIO_BUS_INTERFACE_V2 structure](..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_v2.md) | The HDAUDIO_BUS_INTERFACE_V2 structure specifies the information that a client requires to call the routines in the HDAUDIO_BUS_INTERFACE_V2 version of the HD Audio DDI. |
| [_HDAUDIO_CODEC_COMMAND structure](..\hdaudio\ns-hdaudio-_hdaudio_codec_command.md) | The HDAUDIO_CODEC_COMMAND structure specifies a codec command. |
| [_HDAUDIO_CODEC_RESPONSE structure](..\hdaudio\ns-hdaudio-_hdaudio_codec_response.md) | The HDAUDIO_CODEC_RESPONSE structure specifies either a response to a codec command or an unsolicited response from a codec. |
| [_HDAUDIO_CODEC_TRANSFER structure](..\hdaudio\ns-hdaudio-_hdaudio_codec_transfer.md) | The HDAUDIO_CODEC_TRANSFER structure specifies a codec command and the response to that command. |
| [_HDAUDIO_CONVERTER_FORMAT structure](..\hdaudio\ns-hdaudio-_hdaudio_converter_format.md) | The HDAUDIO_CONVERTER_FORMAT structure specifies the 16-bit encoded stream format for an input or output converter, as defined in the Intel High Definition Audio Specification (see the Intel HD Audio website). |
| [_HDAUDIO_DEVICE_INFORMATION structure](..\hdaudio\ns-hdaudio-_hdaudio_device_information.md) | The HDAUDIO_DEVICE_INFORMATION structure specifies the hardware capabilities of the HD Audio bus controller. |
| [_HDAUDIO_STREAM_FORMAT structure](..\hdaudio\ns-hdaudio-_hdaudio_stream_format.md) | The HDAUDIO_STREAM_FORMAT structure describes the data format of a capture or render stream. |
| [_HFP_BYPASS_CODEC_ID_V1 structure](..\bthhfpddi\ns-bthhfpddi-_hfp_bypass_codec_id_v1.md) | The HFP_BYPASS_CODEC_ID_V1 structure defines version 1 of the supported codec ID structure. |
| [_KSAUDIOMODULE_DESCRIPTOR structure](..\ksmedia\ns-ksmedia-_ksaudiomodule_descriptor.md) | The KSAUDIOMODULE_DESCRIPTOR structure describes the static, external properties of audio modules. |
| [_KSAUDIOMODULE_NOTIFICATION structure](..\ksmedia\ns-ksmedia-_ksaudiomodule_notification.md) | The KSAUDIOMODULE_NOTIFICATION structure describes the properties associated with audio modules change notification. |
| [_KSAUDIOMODULE_PROPERTY structure](..\ksmedia\ns-ksmedia-_ksaudiomodule_property.md) | The KSAUDIOMODULE_DESCRIPTOR structure describes the static, external properties of the audio modules. |
| [_KSAUDIO_PACKETSIZE_CONSTRAINTS structure](..\ksmedia\ns-ksmedia-_ksaudio_packetsize_constraints.md) | The KSAUDIO_PACKETSIZE_CONSTRAINTS structure describes the physical hardware constraints. |
| [_KSAUDIO_PACKETSIZE_CONSTRAINTS2 structure](..\ksmedia\ns-ksmedia-_ksaudio_packetsize_constraints2.md) | The KSAUDIO_PACKETSIZE_CONSTRAINTS2 structure describes the physical hardware constraints. |
| [_KSAUDIO_PACKETSIZE_SIGNALPROCESSINGMODE_CONSTRAINT structure](..\ksmedia\ns-ksmedia-_ksaudio_packetsize_signalprocessingmode_constraint.md) | The KSAUDIO_PACKETSIZE_PROCESSINGMODE_CONSTRAINT structure describes the constraints specific to any signal processing mode. |
| [_PCEVENT_REQUEST structure](..\portcls\ns-portcls-_pcevent_request.md) | The PCEVENT_REQUEST structure specifies an event request. |
| [_PCMETHOD_REQUEST structure](..\portcls\ns-portcls-_pcmethod_request.md) | The PCMETHOD_REQUEST structure specifies a method request. |
| [_PCNOTIFICATION_BUFFER structure](..\portcls\ns-portcls-_pcnotification_buffer.md) | The notification buffer used by IPortClsNotifications. |
| [_PCPROPERTY_REQUEST structure](..\portcls\ns-portcls-_pcproperty_request.md) | The PCPROPERTY_REQUEST structure specifies a property request. |
| [_PCSTREAMRESOURCE_DESCRIPTOR structure](..\portcls\ns-portcls-_pcstreamresource_descriptor.md) | PCSTREAMRESOURCE_DESCRIPTOR defines the stream resource. Use PCSTREAMRESOURCE_DESCRIPTOR_INIT to correctly initialize this structure. |
| [_SYNTHCAPS structure](..\dmusprop\ns-dmusprop-_synthcaps.md) | The SYNTHCAPS structure specifies the capabilities of a synthesizer. |
| [_SYNTHDOWNLOAD structure](..\dmusprop\ns-dmusprop-_synthdownload.md) | The SYNTHDOWNLOAD structure specifies a handle for downloaded DLS data. It also specifies whether the buffer containing the DLS data can be freed. |
| [_SYNTHVOICEPRIORITY_INSTANCE structure](..\dmusprop\ns-dmusprop-_synthvoicepriority_instance.md) | The SYNTHVOICEPRIORITY_INSTANCE structure identifies a voice in a MIDI synthesizer by specifying the voice's channel group (set of 16 MIDI channels) and its channel number within that group. |
| [_SYNTH_BUFFER structure](..\dmusprop\ns-dmusprop-_synth_buffer.md) | The SYNTH_BUFFER structure specifies DLS data that is being downloaded to a synthesizer. |
| [_SYNTH_PORTPARAMS structure](..\dmusprop\ns-dmusprop-_synth_portparams.md) | The SYNTH_PORTPARAMS structure contains the configuration parameters for a DirectMusic port, which is a DirectMusic term for a device that sends or receives music data. |
| [_SYNTH_REVERB_PARAMS structure](..\dmusprop\ns-dmusprop-_synth_reverb_params.md) | The SYNTH_REVERB_PARAMS structure contains configuration parameters. |
| [_SYNTH_STATS structure](..\dmusprop\ns-dmusprop-_synth_stats.md) | The SYNTH_STATS structure specifies synthesizer performance statistics such as the number of voices playing, CPU usage, number of notes lost, amount of free memory, and peak volume level. |
| [_USBSIDEBANDAUDIO_DEVICE_DESCRIPTOR structure](..\usbsidebandaudio\ns-usbsidebandaudio-_usbsidebandaudio_device_descriptor.md) | TBD. |
| [_USBSIDEBANDAUDIO_DEVICE_ERROR structure](..\usbsidebandaudio\ns-usbsidebandaudio-_usbsidebandaudio_device_error.md) | TBD. |
| [_USBSIDEBANDAUDIO_ENDPOINT_DESCRIPTOR structure](..\usbsidebandaudio\ns-usbsidebandaudio-_usbsidebandaudio_endpoint_descriptor.md) | TBD. |
| [_USBSIDEBANDAUDIO_EP_SHADOW_RESOURCES structure](..\usbsidebandaudio\ns-usbsidebandaudio-_usbsidebandaudio_ep_shadow_resources.md) | TBD. |
| [_USBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_FUNCTION structure](..\usbsidebandaudio\ns-usbsidebandaudio-_usbsidebandaudio_ep_shadow_resources_function.md) | TBD. |
| [_USBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_PARAMS structure](..\usbsidebandaudio\ns-usbsidebandaudio-_usbsidebandaudio_ep_shadow_resources_params.md) | TBD. |
| [_USBSIDEBANDAUDIO_MUTE_PARAMS structure](..\usbsidebandaudio\ns-usbsidebandaudio-_usbsidebandaudio_mute_params.md) | TBD. |
| [_USBSIDEBANDAUDIO_SIDETONE_DESCRIPTOR structure](..\usbsidebandaudio\ns-usbsidebandaudio-_usbsidebandaudio_sidetone_descriptor.md) | TBD. |
| [_USBSIDEBANDAUDIO_SIDETONE_PARAMS structure](..\usbsidebandaudio\ns-usbsidebandaudio-_usbsidebandaudio_sidetone_params.md) | TBD. |
| [_USBSIDEBANDAUDIO_STREAM_OPEN_PARAMS structure](..\usbsidebandaudio\ns-usbsidebandaudio-_usbsidebandaudio_stream_open_params.md) | TBD. |
| [_USBSIDEBANDAUDIO_STREAM_STATUS_PARAMS structure](..\usbsidebandaudio\ns-usbsidebandaudio-_usbsidebandaudio_stream_status_params.md) | TBD. |
| [_USBSIDEBANDAUDIO_SUPPORTED_FORMATS structure](..\usbsidebandaudio\ns-usbsidebandaudio-_usbsidebandaudio_supported_formats.md) | TBD. |
| [_USBSIDEBANDAUDIO_VOLUME_PARAMS structure](..\usbsidebandaudio\ns-usbsidebandaudio-_usbsidebandaudio_volume_params.md) | TBD. |
| [__MIDL_IKeywordDetectorOemAdapter_0003 structure](..\keyworddetectoroemadapter\ns-keyworddetectoroemadapter-__midl_ikeyworddetectoroemadapter_0003.md) | The KEYWORDSELECTOR struct is a triplet of IDs that uniquely select a particular keyword, language, and user combination. |
| [__MIDL___MIDL_itf_keyworddetectoroemadapter_0000_0000_0001 structure](..\keyworddetectoroemadapter\ns-keyworddetectoroemadapter-__midl___midl_itf_keyworddetectoroemadapter_0000_0000_0001.md) | The SOUNDDETECTOR_PATTERNHEADER structure specifies the pattern header for the sound detector in the KSPROPERTY_SOUNDDETECTOR_PATTERNS property. |
| [_tagKSAUDIOENGINE_BUFFER_SIZE_RANGE structure](..\ksmedia\ns-ksmedia-_tagksaudioengine_buffer_size_range.md) | The KSAUDIOENGINE_BUFFER_SIZE_RANGE structure specifies the minimum and maximum buffer size that the hardware audio engine can support at the instance when it is called. |
| [_tagKSAUDIOENGINE_DESCRIPTOR structure](..\ksmedia\ns-ksmedia-_tagksaudioengine_descriptor.md) | The KSAUDIOENGINE_DESCRIPTOR structure describes the static, external properties of the audio engine. |
| [_tagKSAUDIOENGINE_VOLUMELEVEL structure](..\ksmedia\ns-ksmedia-_tagksaudioengine_volumelevel.md) | The KSAUDIOENGINE_VOLUMELEVEL structure specifies the target volume level, ramp type, and duration within which the volume level should change, for a given volume level request via the KSPROPERTY_AUDIOENGINE_VOLUMELEVEL property. |
| [_tagKSJACK_SINK_INFORMATION structure](..\ksmedia\ns-ksmedia-_tagksjack_sink_information.md) | The KSJACK_SINK_INFORMATION structure specifies information about a display-related digital audio device, such as an HDMI device or a display port. |
| [_tagKSTELEPHONY_CALLCONTROL structure](..\ksmedia\ns-ksmedia-_tagkstelephony_callcontrol.md) | The KSTELEPHONY_CALLCONTROL structure specifies the phone call type and control operation to use for the KSPROPERTY_TELEPHONY_CALLCONTROL property. |
| [_tagKSTELEPHONY_CALLINFO structure](..\ksmedia\ns-ksmedia-_tagkstelephony_callinfo.md) | The KSTELEPHONY_CALLINFO structure specifies the type and state of a phone call for the KSPROPERTY_TELEPHONY_CALLINFO property. |
| [_tagKSTELEPHONY_PROVIDERCHANGE structure](..\ksmedia\ns-ksmedia-_tagkstelephony_providerchange.md) | The KSTELEPHONY_PROVIDERCHANGE structure specifies the phone call type and provider change operation to use for the KSPROPERTY_TELEPHONY_PROVIDERCHANGE property. |
| [_tagKSTOPOLOGY_ENDPOINTID structure](..\ksmedia\ns-ksmedia-_tagkstopology_endpointid.md) | The KSTOPOLOGY_ENDPOINTID structure specifies the name and the pin ID of a topology endpoint. |
| [_tagKSTOPOLOGY_ENDPOINTIDPAIR structure](..\ksmedia\ns-ksmedia-_tagkstopology_endpointidpair.md) | The KSTOPOLOGY_ENDPOINTIDPAIR structure specifies the render and capture endpoint IDs to use for the KSPROPERTY_TELEPHONY_ENDPOINTIDPAIR property. |
| [tagDRMFORWARD structure](..\drmk\ns-drmk-tagdrmforward.md) | The DRMFORWARD structure contains the information that the DRMK system driver needs in order to forward a DRM content ID to a device that handles protected content. |
| [tagDRMRIGHTS structure](..\drmk\ns-drmk-tagdrmrights.md) | The DRMRIGHTS structure specifies the DRM content rights assigned to a KS audio pin or to a port-class driver's stream object. |
| [tagKSATTRIBUTE_AUDIOSIGNALPROCESSING_MODE structure](..\ksmedia\ns-ksmedia-tagksattribute_audiosignalprocessing_mode.md) | The KSATTRIBUTE_AUDIOSIGNALPROCESSING_MODE structure specifies an audio signal processing mode. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [AUDIO_CURVE_TYPE enumeration](..\ksmedia\ne-ksmedia-audio_curve_type.md) | The AUDIO_CURVE_TYPE enumeration defines constants that specify a curve algorithm to be applied to set a volume level. |
| [DMUS_STREAM_TYPE enumeration](..\dmusicks\ne-dmusicks-dmus_stream_type.md) | Used for a DirectMusic synthesizer device. |
| [EPcMiniportEngineEvent enumeration](..\portcls\ne-portcls-epcminiportengineevent.md) | This topic introduces the EPcMiniportEngineEvent enum, and describes the parameters that provide additional information when the miniport driver reports a glitching error. |
| [PC_REBALANCE_TYPE enumeration](..\portcls\ne-portcls-pc_rebalance_type.md) | The PC_REBALANCE_TYPE enum describes the type of support for rebalancing. |
| [TELEPHONY_CALLCONTROLOP enumeration](..\ksmedia\ne-ksmedia-telephony_callcontrolop.md) | The TELEPHONY_CALLCONTROLOP enumeration defines constants that specify an operation to perform on a phone call. |
| [TELEPHONY_CALLSTATE enumeration](..\ksmedia\ne-ksmedia-telephony_callstate.md) | The TELEPHONY_CALLSTATE enumeration defines constants that specify the state of a phone call. |
| [TELEPHONY_CALLTYPE enumeration](..\ksmedia\ne-ksmedia-telephony_calltype.md) | The TELEPHONY_CALLTYPE enumeration defines constants that specify the type of phone call. |
| [TELEPHONY_PROVIDERCHANGEOP enumeration](..\ksmedia\ne-ksmedia-telephony_providerchangeop.md) | The TELEPHONY_PROVIDERCHANGEOP enumeration defines constants that specify the requested provider change operation. |
| [_HDAUDIO_CODEC_POWER_STATE enumeration](..\hdaudio\ne-hdaudio-_hdaudio_codec_power_state.md) | The HDAUDIO_CODEC_POWER_STATE enumeration defines constants that specify the different power states that HD Audio codecs can support. All states are from DEVICE_POWER_STATE except PowerCodecD3Cold. |
| [_HDAUDIO_STREAM_STATE enumeration](..\hdaudio\ne-hdaudio-_hdaudio_stream_state.md) | The HDAUDIO_STREAM_STATE enumeration defines constants that specify the different stream states supported by HDAudio. |
| [_HFP_BYPASS_CODEC_ID_VERSION enumeration](..\bthhfpddi\ne-bthhfpddi-_hfp_bypass_codec_id_version.md) | The HFP_BYPASS_CODEC_ID_VERSION enumeration defines the codec ID structure versions that are supported by the HFP service. |
| [_PC_EXIT_LATENCY enumeration](..\portcls\ne-portcls-_pc_exit_latency.md) | This topic discusses the PC_EXIT_LATENCY enum, and describes its members. The latency times map to specific maximum times in which the device must be able to exit its sleep state and enter the fully functional state (D0). |
| [_PcStreamResourceType enumeration](..\portcls\ne-portcls-_pcstreamresourcetype.md) | This topic discusses the PcStreamResourceType enum, and describes its members. The PcStreamResourceType enum is used to define the type of resources used for specific audio streaming. |
| [__MIDL_IKeywordDetectorOemAdapter_0002 enumeration](..\keyworddetectoroemadapter\ne-keyworddetectoroemadapter-__midl_ikeyworddetectoroemadapter_0002.md) | The KEYWORDID enumeration identifies the phrase text/function of a keyword. The value is also be used in the Windows Biometric Service adapters. |
| [eChannelTargetType enumeration](..\portcls\ne-portcls-echanneltargettype.md) | The eChannelTargetType enumeration defines constants that specify a type of node (target) in a given channel. |
| [eEngineFormatType enumeration](..\portcls\ne-portcls-eengineformattype.md) | The eEngineFormatType enumeration defines constants that specify the audio data type supported by the audio engine. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_BTHHFP_DEVICE_GET_CODEC_ID IOCTL](..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_device_get_codec_id.md) | An audio driver can send an IOCTL_BTHHFP_DEVICE_GET_CODEC_ID control code to query the Bluetooth driver stack about the codec ID used by the HFP service. This helps the audio driver determine the sampling rate for the data. |
| [IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE IOCTL](..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_device_get_connection_status_update.md) | The IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE IOCTL Gets a connection status update. |
| [IOCTL_BTHHFP_DEVICE_GET_CONTAINERID IOCTL](..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_device_get_containerid.md) | The IOCTL_BTHHFP_DEVICE_GET_CONTAINERID IOCTL Gets the PnP Container ID of the Bluetooth device. |
| [IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR IOCTL](..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_device_get_descriptor.md) | The audio driver issues the IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR control code to get information about an enabled GUID_DEVINTERFACE_BLUETOOTH_HFP_SCO_HCIBYPASS device interface. |
| [IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR2 IOCTL](..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_device_get_descriptor2.md) | The IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR2 IOCTL Gets descriptive information about the paired Handsfree profile (HFP) device. |
| [IOCTL_BTHHFP_DEVICE_GET_KSNODETYPES IOCTL](..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_device_get_ksnodetypes.md) | The IOCTL_BTHHFP_DEVICE_GET_KSNODETYPES IOCTL Gets the KSNODE types that best describe the Bluetooth device’s input and output. |
| [IOCTL_BTHHFP_DEVICE_GET_NRECDISABLE_STATUS_UPDATE IOCTL](..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_device_get_nrecdisable_status_update.md) | The IOCTL_BTHHFP_DEVICE_GET_NRECDISABLE_STATUS_UPDATE IOCTL Gets noise reduction / echo cancellation (NREC) Disable status updates from the remote Bluetooth device. |
| [IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES IOCTL](..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_device_get_volumepropertyvalues.md) | The IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES IOCTL returns KSPROPERTY_VALUES data for the KSPROPERTY_AUDIO_VOLUMELEVEL property. |
| [IOCTL_BTHHFP_DEVICE_REQUEST_CONNECT IOCTL](..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_device_request_connect.md) | The IOCTL_BTHHFP_DEVICE_REQUEST_CONNECT IOCTL requests a Handsfree Profile (HFP) Service Level Connection to the Bluetooth device. |
| [IOCTL_BTHHFP_DEVICE_REQUEST_DISCONNECT IOCTL](..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_device_request_disconnect.md) | The IOCTL_BTHHFP_DEVICE_REQUEST_DISCONNECT IOCTL removes the Handfree Profile (HFP) Service Level Connection that existed between the audio driver and the Bluetooth device. |
| [IOCTL_BTHHFP_MIC_GET_VOLUME_STATUS_UPDATE IOCTL](..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_mic_get_volume_status_update.md) | The IOCTL_BTHHFP_MIC_GET_VOLUME_STATUS_UPDATE IOCTL Gets the volume level setting of the Bluetooth device's microphone. |
| [IOCTL_BTHHFP_MIC_SET_VOLUME IOCTL](..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_mic_set_volume.md) | The IOCTL_BTHHFP_MIC_SET_VOLUME IOCTL sets the volume level of the microphone for the Bluetooth device. |
| [IOCTL_BTHHFP_SPEAKER_GET_VOLUME_STATUS_UPDATE IOCTL](..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_speaker_get_volume_status_update.md) | The IOCTL_BTHHFP_SPEAKER_GET_VOLUME_STATUS_UPDATE IOCTL Gets the volume level setting of the Bluetooth device's speaker. |
| [IOCTL_BTHHFP_SPEAKER_SET_VOLUME IOCTL](..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_speaker_set_volume.md) | The IOCTL_BTHHFP_SPEAKER_SET_VOLUME IOCTL sets the volume level for the speaker of the Bluetooth device. |
| [IOCTL_BTHHFP_STREAM_CLOSE IOCTL](..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_stream_close.md) | The IOCTL_BTHHFP_STREAM_CLOSE IOCTL indicates that the client driver no longer requires the synchronous connection-oriented (SCO) channel for streaming audio. |
| [IOCTL_BTHHFP_STREAM_GET_STATUS_UPDATE IOCTL](..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_stream_get_status_update.md) | The IOCTL_BTHHFP_STREAM_GET_STATUS_UPDATE IOCTL Gets a stream channel status update. |
| [IOCTL_BTHHFP_STREAM_OPEN IOCTL](..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_stream_open.md) | The IOCTL_BTHHFP_STREAM_OPEN IOCTL requests an open synchronous connection-oriented (SCO) channel to transmit audio data over the air. |
| [IOCTL_USBSBAUD_GET_DEVICE_DESCRIPTOR IOCTL](..\usbsidebandaudio\ni-usbsidebandaudio-ioctl_usbsbaud_get_device_descriptor.md) | TBD |
| [IOCTL_USBSBAUD_GET_ENDPOINT_DESCRIPTOR IOCTL](..\usbsidebandaudio\ni-usbsidebandaudio-ioctl_usbsbaud_get_endpoint_descriptor.md) | TBD |
| [IOCTL_USBSBAUD_GET_ERROR_STATUS_UPDATE IOCTL](..\usbsidebandaudio\ni-usbsidebandaudio-ioctl_usbsbaud_get_error_status_update.md) | TBD |
| [IOCTL_USBSBAUD_GET_MUTE_STATUS_UPDATE IOCTL](..\usbsidebandaudio\ni-usbsidebandaudio-ioctl_usbsbaud_get_mute_status_update.md) | TBD |
| [IOCTL_USBSBAUD_GET_SHADOW_RESOURCES IOCTL](..\usbsidebandaudio\ni-usbsidebandaudio-ioctl_usbsbaud_get_shadow_resources.md) | TBD |
| [IOCTL_USBSBAUD_GET_SIDETONE_STATUS_UPDATE IOCTL](..\usbsidebandaudio\ni-usbsidebandaudio-ioctl_usbsbaud_get_sidetone_status_update.md) | TBD |
| [IOCTL_USBSBAUD_GET_SIDETONE_VOLUMEPROPERTYVALUES IOCTL](..\usbsidebandaudio\ni-usbsidebandaudio-ioctl_usbsbaud_get_sidetone_volumepropertyvalues.md) | TBD |
| [IOCTL_USBSBAUD_GET_STREAM_STATUS_UPDATE IOCTL](..\usbsidebandaudio\ni-usbsidebandaudio-ioctl_usbsbaud_get_stream_status_update.md) | TBD |
| [IOCTL_USBSBAUD_GET_SUPPORTED_FORMATS IOCTL](..\usbsidebandaudio\ni-usbsidebandaudio-ioctl_usbsbaud_get_supported_formats.md) | TBD |
| [IOCTL_USBSBAUD_GET_VOLUMEPROPERTYVALUES IOCTL](..\usbsidebandaudio\ni-usbsidebandaudio-ioctl_usbsbaud_get_volumepropertyvalues.md) | TBD |
| [IOCTL_USBSBAUD_GET_VOLUME_STATUS_UPDATE IOCTL](..\usbsidebandaudio\ni-usbsidebandaudio-ioctl_usbsbaud_get_volume_status_update.md) | TBD |
| [IOCTL_USBSBAUD_SET_MUTE IOCTL](..\usbsidebandaudio\ni-usbsidebandaudio-ioctl_usbsbaud_set_mute.md) | TBD |
| [IOCTL_USBSBAUD_SET_SIDETONE_PROPERTY IOCTL](..\usbsidebandaudio\ni-usbsidebandaudio-ioctl_usbsbaud_set_sidetone_property.md) | TBD |
| [IOCTL_USBSBAUD_SET_STREAM_CLOSE IOCTL](..\usbsidebandaudio\ni-usbsidebandaudio-ioctl_usbsbaud_set_stream_close.md) | TBD |
| [IOCTL_USBSBAUD_SET_STREAM_OPEN IOCTL](..\usbsidebandaudio\ni-usbsidebandaudio-ioctl_usbsbaud_set_stream_open.md) | TBD |
| [IOCTL_USBSBAUD_SET_VOLUME IOCTL](..\usbsidebandaudio\ni-usbsidebandaudio-ioctl_usbsbaud_set_volume.md) | TBD |

## Interfaces

| Title   | Description   |
| ---- |:---- |
| [IAdapterPnpManagement interface](..\portcls\nn-portcls-iadapterpnpmanagement.md) | IAdapterPnpManagement is an interface that adapters should implement and register if they want to receive PnP management messages. |
| [IAdapterPowerManagement interface](..\portcls\nn-portcls-iadapterpowermanagement.md) | The IAdapterPowerManagement interface is used to manage the power state of an audio adapter. |
| [IAdapterPowerManagement2 interface](..\portcls\nn-portcls-iadapterpowermanagement2.md) | The IAdapterPowerManagement2 interface inherits from IUnknown and it is used to manage the power state of an audio adapter. |
| [IAdapterPowerManagement3 interface](..\portcls\nn-portcls-iadapterpowermanagement3.md) | The IAdapterPowerManagement3 interface inherits from IUnknown, and it is used for receiving power management messages. |
| [IAllocatorMXF interface](..\dmusicks\nn-dmusicks-iallocatormxf.md) | The IAllocatorMXF interface manages buffer storage for DirectMusic streams. |
| [IDmaChannel interface](..\portcls\nn-portcls-idmachannel.md) | The IDmaChannel interface provides an abstraction of a DMA channel and its associated DMA buffer and usage parameters. |
| [IDmaChannelSlave interface](..\portcls\nn-portcls-idmachannelslave.md) | The IDmaChannelSlave interface provides methods for monitoring and controlling a DMA channel for a subordinate device (as described in Introduction to Adapter Objects). |
| [IDrmAudioStream interface](..\drmk\nn-drmk-idrmaudiostream.md) | The IDrmAudioStream interface assigns DRM protection to the digital content in an audio stream. |
| [IDrmPort interface](..\portcls\nn-portcls-idrmport.md) | The IDrmPort interface is used by a WaveCyclic or WavePci miniport driver to manage DRM-protected content (see Digital Rights Management). |
| [IDrmPort2 interface](..\portcls\nn-portcls-idrmport2.md) | The IDrmPort2 interface is used by a WaveCyclic or WavePci miniport driver to manage DRM-protected content (see Digital Rights Management). |
| [IInterruptSync interface](..\portcls\nn-portcls-iinterruptsync.md) | The IInterruptSync interface represents an interrupt sync object that synchronizes the execution of a list of interrupt service routines (ISRs) with non-ISR routines. |
| [IKeywordDetectorOemAdapter interface](..\keyworddetectoroemadapter\nn-keyworddetectoroemadapter-ikeyworddetectoroemadapter.md) | IKeywordDetectorOemAdapter is a Component Object Model (COM) interface for interacting with the Voice Activation Driver Interface. The IKeywordDetectorOemAdapter interface is supported in Windows 10 and later versions of Windows. |
| [IMXF interface](..\dmusicks\nn-dmusicks-imxf.md) | The IMXF interface represents the DirectMusic stream on a MIDI transport filter (MXF). |
| [IMasterClock interface](..\dmusicks\nn-dmusicks-imasterclock.md) | The IMasterClock interface provides Microsoft DirectMusic streams with access to the current reference time from the master clock. |
| [IMiniport interface](..\portcls\nn-portcls-iminiport.md) | The IMiniport interface is the generic miniport interface that all miniport objects support. IMiniport inherits from the IUnknown interface. |
| [IMiniportAudioEngineNode interface](..\portcls\nn-portcls-iminiportaudioenginenode.md) | This interface allows a miniport driver to use KS properties that access the audio engine via a KS filter handle. |
| [IMiniportAudioSignalProcessing interface](..\portcls\nn-portcls-iminiportaudiosignalprocessing.md) | The IMiniportAudioSignalProcessing interface is implemented by the WaveRT miniport component of any audio driver, if any of its pins support audio signal processing modes. |
| [IMiniportDMus interface](..\dmusicks\nn-dmusicks-iminiportdmus.md) | The IMiniportDMus interface is the primary interface for a DMus miniport driver for a DirectMusic synthesizer device. |
| [IMiniportMidi interface](..\portcls\nn-portcls-iminiportmidi.md) | The IMiniportMidi interface is the primary interface for a MIDI miniport driver for a MIDI synthesizer device. |
| [IMiniportMidiStream interface](..\portcls\nn-portcls-iminiportmidistream.md) | The IMiniportMidiStream interface represents the MIDI stream that flows through a pin on a MIDI filter. |
| [IMiniportPnpNotify interface](..\portcls\nn-portcls-iminiportpnpnotify.md) | IMiniportPnpNotify is an optional interface to allow miniport objects (audio subdevices) to receive PnP state change notifications. |
| [IMiniportStreamAudioEngineNode interface](..\portcls\nn-portcls-iminiportstreamaudioenginenode.md) | This interface allows a miniport driver to use KS properties that access the audio engine via a pin instance handle. |
| [IMiniportStreamAudioEngineNode2 interface](..\portcls\nn-portcls-iminiportstreamaudioenginenode2.md) | The IMiniportStreamAudioEngineNode2 interface allows an audio miniport driver to extend the capabilities of the IMiniportStreamAudioEngineNode interface. |
| [IMiniportTopology interface](..\portcls\nn-portcls-iminiporttopology.md) | The IMiniportTopology interface is the primary interface of a Topology miniport driver. |
| [IMiniportWaveCyclic interface](..\portcls\nn-portcls-iminiportwavecyclic.md) | The IMiniportWaveCyclic interface is the primary interface that is exposed by the miniport driver for a WaveCyclic audio device. |
| [IMiniportWaveCyclicStream interface](..\portcls\nn-portcls-iminiportwavecyclicstream.md) | The IMiniportWaveCyclicStream interface represents the wave stream that flows through a pin on a WaveCyclic filter. |
| [IMiniportWavePci interface](..\portcls\nn-portcls-iminiportwavepci.md) | The IMiniportWavePci interface is the primary interface that is exposed by the miniport driver for a WavePci audio device. |
| [IMiniportWavePciStream interface](..\portcls\nn-portcls-iminiportwavepcistream.md) | The IMiniportWavePciStream interface represents the wave stream that flows through a pin on a WavePci filter. |
| [IMiniportWaveRT interface](..\portcls\nn-portcls-iminiportwavert.md) | The IMiniportWaveRT interface is the primary interface that is exposed by the miniport driver for a WaveRT audio device. |
| [IMiniportWaveRTInputStream interface](..\portcls\nn-portcls-iminiportwavertinputstream.md) | The IMiniportWaveRTInputStream interface represents the input wave stream that flows through a pin on the KS filter that wraps a WaveRT rendering or capture device. IMiniportWaveRTInputStream inherits from the IUnknown interface. |
| [IMiniportWaveRTOutputStream interface](..\portcls\nn-portcls-iminiportwavertoutputstream.md) | The IMiniportWaveRTOutputStream interface represents the output wave stream. IMiniportWaveRTOutputStream inherits from the IUnknown interface. |
| [IMiniportWaveRTStream interface](..\portcls\nn-portcls-iminiportwavertstream.md) | The IMiniportWaveRTStream interface represents the wave stream that flows through a pin on the KS filter that wraps a WaveRT rendering or capture device. |
| [IMiniportWaveRTStreamNotification interface](..\portcls\nn-portcls-iminiportwavertstreamnotification.md) | The IMiniportWaveRTStreamNotification interface is supported in Windows Vista and later Windows operating systems, and it augments the IMiniportWaveRTStream interface, providing additional methods to facilitate DMA driver event notifications. |
| [IMusicTechnology interface](..\portcls\nn-portcls-imusictechnology.md) | The IMusicTechnology interface is used to change the music technology GUIDs that are specified in the data range descriptors for the pins belonging to a MIDI or DMus miniport driver. |
| [IPinCount interface](..\portcls\nn-portcls-ipincount.md) | The IPinCount interface provides a means for the miniport driver to monitor and manipulate its pin counts dynamically as pins are instantiated and closed. |
| [IPinName interface](..\portcls\nn-portcls-ipinname.md) | In Windows 7 and later operating systems, the IPinName interface is used by miniport drivers to report and update the names of audio endpoints. |
| [IPort interface](..\portcls\nn-portcls-iport.md) | The IPort interface is the generic interface for audio port drivers. All audio port drivers expose IPort as part of their lower edge. The adapter driver calls the initialization method on this interface. IPort inherits from the IUnknown interface. |
| [IPortClsEtwHelper interface](..\portcls\nn-portcls-iportclsetwhelper.md) | The IPortClsEtwHelper interface allows an audio miniport driver to access the Event Tracing for Windows (ETW) helper functions. |
| [IPortClsNotifications interface](..\portcls\nn-portcls-iportclsnotifications.md) | An interface implemented by ports to provide notification helpers to miniports to support audio module communication. |
| [IPortClsPnp interface](..\portcls\nn-portcls-iportclspnp.md) | IPortClsPnp is the PnP management interface that the port class driver (PortCls) exposes to the adapter. |
| [IPortClsPower interface](..\portcls\nn-portcls-iportclspower.md) | The IPortClsPower interface is supported in Windows Vista and later versions of Windows. IPortClsPower is the power management interface that the port class driver (PortCls) exposes to the adapter. |
| [IPortClsRuntimePower interface](..\portcls\nn-portcls-iportclsruntimepower.md) | IPortClsRuntimePower is the interface that the port class driver (PortCls) uses for accessing the runtime power management capabilities of the audio adapter. |
| [IPortClsStreamResourceManager interface](..\portcls\nn-portcls-iportclsstreamresourcemanager.md) | IPortClsStreamResourceManager is used to manage the registration of audio stream resources. |
| [IPortClsStreamResourceManager2 interface](..\portcls\nn-portcls-iportclsstreamresourcemanager2.md) | IPortClsStreamResourceManager2 is used to manage the registration of audio stream resources. |
| [IPortClsVersion interface](..\portcls\nn-portcls-iportclsversion.md) | The IPortClsVersion interface is used by a miniport driver to identify the version of the Windows operating system that the driver is running on. The port driver implements this interface and exposes it to the miniport driver. |
| [IPortDMus interface](..\dmusicks\nn-dmusicks-iportdmus.md) | The IPortDMus interface is the DMus port driver's primary interface. |
| [IPortEvents interface](..\portcls\nn-portcls-iportevents.md) | The IPortEvents interface is used by miniport drivers to notify clients of hardware events. |
| [IPortMidi interface](..\portcls\nn-portcls-iportmidi.md) | The IPortMidi interface is the MIDI port driver's primary interface. |
| [IPortTopology interface](..\portcls\nn-portcls-iporttopology.md) | The IPortTopology interface provides generic port driver support to a topology miniport driver. |
| [IPortWMIRegistration interface](..\portcls\nn-portcls-iportwmiregistration.md) | The IPortWMIRegistration interface is provided in Windows 7 and later versions of Windows. This interface allows the miniport driver to coordinate Event Tracing for Windows (ETW) registration between PortCls and the miniport driver. |
| [IPortWaveCyclic interface](..\portcls\nn-portcls-iportwavecyclic.md) | The IPortWaveCyclic interface is the WaveCyclic port driver's primary interface. |
| [IPortWavePci interface](..\portcls\nn-portcls-iportwavepci.md) | The IPortWavePci interface is the WavePci port driver's primary interface. |
| [IPortWavePciStream interface](..\portcls\nn-portcls-iportwavepcistream.md) | The IPortWavePciStream interface is the stream-associated callback interface that provides mapping services to WavePci miniport stream objects. |
| [IPortWaveRT interface](..\portcls\nn-portcls-iportwavert.md) | The IPortWaveRT interface is supported in Windows Vista and later operating systems and it is the main interface that the WaveRT port driver exposes to the adapter driver that implements the WaveRT miniport driver object. |
| [IPortWaveRTStream interface](..\portcls\nn-portcls-iportwavertstream.md) | The IPortWaveRTStream interface is supported in Windows Vista and later operating systems, and it is a stream-specific interface that provides helper methods for use by the WaveRT miniport driver. |
| [IPositionNotify interface](..\dmusicks\nn-dmusicks-ipositionnotify.md) | PositionNotify |
| [IPowerNotify interface](..\portcls\nn-portcls-ipowernotify.md) | The IPowerNotify interface is an optional interface that miniport drivers can expose if they require advance notification of impending power-state changes. |
| [IPreFetchOffset interface](..\portcls\nn-portcls-iprefetchoffset.md) | The IPreFetchOffset interface controls the prefetch offset, which is the number of bytes separating the play and write cursors in a DirectSound output stream. |
| [IRegistryKey interface](..\portcls\nn-portcls-iregistrykey.md) | The IRegistryKey interface provides an abstraction of a registry key that a miniport driver can use to access the key and its subkeys. |
| [IResourceList interface](..\portcls\nn-portcls-iresourcelist.md) | The IResourceList interface provides an abstraction of a configuration resource list, which is a list of the system hardware resources that the Plug and Play manager assigns to a device at startup time. |
| [IServiceGroup interface](..\portcls\nn-portcls-iservicegroup.md) | The IServiceGroup interface encapsulates a group of objects that all require notification of the same service request. |
| [IServiceSink interface](..\portcls\nn-portcls-iservicesink.md) | The IServiceSink interface encapsulates handling of a service request. |
| [ISynthSinkDMus interface](..\dmusicks\nn-dmusicks-isynthsinkdmus.md) | The ISynthSinkDMus interface handles wave output for a DirectMusic synthesizer device. |
| [IUnregisterPhysicalConnection interface](..\portcls\nn-portcls-iunregisterphysicalconnection.md) | The IUnregisterPhysicalConnection interface implements three methods to remove a registered physical connection. |
| [IUnregisterSubdevice interface](..\portcls\nn-portcls-iunregistersubdevice.md) | The IUnregisterSubdevice interface implements a method to remove a registered subdevice. |

## Methods

| Title   | Description   |
| ---- |:---- |
| [IAdapterPowerManagement2::PowerChangeState2 method](..\portcls\nf-portcls-iadapterpowermanagement2-powerchangestate2.md) | Portcls calls the IAdapterPowerManagement2 |
| [IAdapterPowerManagement3::D3ExitLatencyChanged method](..\portcls\nf-portcls-iadapterpowermanagement3-d3exitlatencychanged.md) | PortCls calls the D3ExitLatencyChanged method while the device is in sleep (D3) power state, to provide a new exit latency value. |
| [IAdapterPowerManagement::PowerChangeState method](..\portcls\nf-portcls-iadapterpowermanagement-powerchangestate.md) | The PowerChangeState method requests that the device change to a new power state. |
| [IAdapterPowerManagement::QueryDeviceCapabilities method](..\portcls\nf-portcls-iadapterpowermanagement-querydevicecapabilities.md) | The QueryDeviceCapabilities method is called by PortCls in response to a Plug and Play IRP_MN_QUERY_CAPABILITIES IRP. |
| [IAdapterPowerManagement::QueryPowerChangeState method](..\portcls\nf-portcls-iadapterpowermanagement-querypowerchangestate.md) | The QueryPowerChangeState method is called by PortCls in response to the receipt of an IRP_MN_QUERY_POWER power IRP. |
| [IAllocatorMXF::GetBuffer method](..\dmusicks\nf-dmusicks-iallocatormxf-getbuffer.md) | The GetBuffer method allocates a buffer for long MIDI events. |
| [IAllocatorMXF::GetBufferSize method](..\dmusicks\nf-dmusicks-iallocatormxf-getbuffersize.md) | The GetBufferSize method gets the buffer size from the allocator. |
| [IAllocatorMXF::GetMessage method](..\dmusicks\nf-dmusicks-iallocatormxf-getmessage.md) | The GetMessage method serves as the retrieval point for any DirectMusic kernel-mode component that utilizes the port driver's allocator to reuse DMUS_KERNEL_EVENT structures. |
| [IAllocatorMXF::PutBuffer method](..\dmusicks\nf-dmusicks-iallocatormxf-putbuffer.md) | This method is not currently used by the miniport driver. The PutBuffer method passes a buffer to the allocator, but this occurs automatically when IMXF |
| [IDrmAudioStream::SetContentId method](..\drmk\nf-drmk-idrmaudiostream-setcontentid.md) | The SetContentId method sets the DRM content ID and its assigned DRM content rights on a KS audio stream. |
| [IDrmPort2::AddContentHandlers method](..\portcls\nf-portcls-idrmport2-addcontenthandlers.md) | The AddContentHandlers method provides the system with a list of functions that handle protected content. |
| [IDrmPort2::ForwardContentToDeviceObject method](..\portcls\nf-portcls-idrmport2-forwardcontenttodeviceobject.md) | The ForwardContentToDeviceObject method accepts a device object representing a device to which the caller intends to forward protected content. |
| [IInterruptSync::CallSynchronizedRoutine method](..\portcls\nf-portcls-iinterruptsync-callsynchronizedroutine.md) | The CallSynchronizedRoutine method calls a routine that is not an interrupt service routine (ISR) but whose execution needs to be synchronized with ISRs. |
| [IInterruptSync::Connect method](..\portcls\nf-portcls-iinterruptsync-connect.md) | The Connect method connects the synchronization object to the interrupt. |
| [IInterruptSync::Disconnect method](..\portcls\nf-portcls-iinterruptsync-disconnect.md) | The Disconnect method disconnects the synchronization object from the interrupt. |
| [IInterruptSync::GetKInterrupt method](..\portcls\nf-portcls-iinterruptsync-getkinterrupt.md) | The GetKInterrupt method gets a WDM interrupt object from a port-class synchronization object. |
| [IInterruptSync::RegisterServiceRoutine method](..\portcls\nf-portcls-iinterruptsync-registerserviceroutine.md) | The RegisterServiceRoutine method registers an interrupt service routine (ISR) that is to be called when an interrupt occurs. |
| [IKeywordDetectorOemAdapter::BuildArmingPatternData method](..\keyworddetectoroemadapter\nf-keyworddetectoroemadapter-ikeyworddetectoroemadapter-buildarmingpatterndata.md) | The BuildArmingPatternData method is called by the operating system to build OEM-specific pattern data that includes any keyword and user-specific model data for detection. |
| [IKeywordDetectorOemAdapter::ComputeAndAddUserModelData method](..\keyworddetectoroemadapter\nf-keyworddetectoroemadapter-ikeyworddetectoroemadapter-computeandaddusermodeldata.md) | The ComputeAndAddUserModelData method is used by the training user experience to compute the user-specific information relative to the user-independent keyword. |
| [IKeywordDetectorOemAdapter::GetCapabilities method](..\keyworddetectoroemadapter\nf-keyworddetectoroemadapter-ikeyworddetectoroemadapter-getcapabilities.md) | The GetCapabilities method returns the keywords and languages supported by the object. |
| [IKeywordDetectorOemAdapter::ParseDetectionResultData method](..\keyworddetectoroemadapter\nf-keyworddetectoroemadapter-ikeyworddetectoroemadapter-parsedetectionresultdata.md) | The ParseDetectionResultData method is called by the operating system after handling a keyword detection event and after retrieving the result data from KSPROPERTY_SOUNDDETECTOR_MATCHRESULT. |
| [IKeywordDetectorOemAdapter::VerifyUserKeyword method](..\keyworddetectoroemadapter\nf-keyworddetectoroemadapter-ikeyworddetectoroemadapter-verifyuserkeyword.md) | The VerifyUserKeyword method is used by the training user experience to verify that one instance of a spoken utterance, captured during training, matches a predefined keyword within some tolerance. |
| [IMasterClock::GetTime method](..\dmusicks\nf-dmusicks-imasterclock-gettime.md) | The GetTime method retrieves the current reference time read from the master clock. |
| [IMiniportAudioEngineNode::GetAudioEngineDescriptor method](..\portcls\nf-portcls-iminiportaudioenginenode-getaudioenginedescriptor.md) | Gets the descriptor for the audio engine node. |
| [IMiniportAudioEngineNode::GetBufferSizeRange method](..\portcls\nf-portcls-iminiportaudioenginenode-getbuffersizerange.md) | Gets the minimum and maximum buffer size that the hardware audio engine can support. |
| [IMiniportAudioEngineNode::GetDeviceAttributeSteppings method](..\portcls\nf-portcls-iminiportaudioenginenode-getdeviceattributesteppings.md) | Gets the allowed stepping value for the audio device attribute. |
| [IMiniportAudioEngineNode::GetDeviceChannelCount method](..\portcls\nf-portcls-iminiportaudioenginenode-getdevicechannelcount.md) | Gets a count of the number of channels supported by the audio device. |
| [IMiniportAudioEngineNode::GetDeviceChannelMute method](..\portcls\nf-portcls-iminiportaudioenginenode-getdevicechannelmute.md) | Gets the state of the Mute node for the audio device channel. |
| [IMiniportAudioEngineNode::GetDeviceChannelPeakMeter method](..\portcls\nf-portcls-iminiportaudioenginenode-getdevicechannelpeakmeter.md) | Gets the PeakMeter value for the audio device channel. |
| [IMiniportAudioEngineNode::GetDeviceChannelVolume method](..\portcls\nf-portcls-iminiportaudioenginenode-getdevicechannelvolume.md) | Gets the volume level for a given channel of the audio device. |
| [IMiniportAudioEngineNode::GetDeviceFormat method](..\portcls\nf-portcls-iminiportaudioenginenode-getdeviceformat.md) | Gets the audio data format for an audio device. |
| [IMiniportAudioEngineNode::GetEngineFormatSize method](..\portcls\nf-portcls-iminiportaudioenginenode-getengineformatsize.md) | Gets the format type and the buffer size for the audio engine's audio data format. |
| [IMiniportAudioEngineNode::GetGfxState method](..\portcls\nf-portcls-iminiportaudioenginenode-getgfxstate.md) | Gets the state of the global effects (GFX) node in the audio engine. |
| [IMiniportAudioEngineNode::GetMixFormat method](..\portcls\nf-portcls-iminiportaudioenginenode-getmixformat.md) | Gets the audio data format for the audio engine mixer. |
| [IMiniportAudioEngineNode::GetSupportedDeviceFormats method](..\portcls\nf-portcls-iminiportaudioenginenode-getsupporteddeviceformats.md) | Gets the supported audio data formats for the audio device. |
| [IMiniportAudioEngineNode::SetDeviceChannelMute method](..\portcls\nf-portcls-iminiportaudioenginenode-setdevicechannelmute.md) | Sets the state of the Mute node for the audio device channel. |
| [IMiniportAudioEngineNode::SetDeviceChannelVolume method](..\portcls\nf-portcls-iminiportaudioenginenode-setdevicechannelvolume.md) | Sets the volume level for a given channel of the audio device. |
| [IMiniportAudioEngineNode::SetDeviceFormat method](..\portcls\nf-portcls-iminiportaudioenginenode-setdeviceformat.md) | Sets the audio data format for an audio device. |
| [IMiniportAudioEngineNode::SetGfxState method](..\portcls\nf-portcls-iminiportaudioenginenode-setgfxstate.md) | Sets the state of the global effects (GFX) node in the audio engine. |
| [IMiniportAudioSignalProcessing::GetModes method](..\portcls\nf-portcls-iminiportaudiosignalprocessing-getmodes.md) | The GetModes method, Gets the audio signal processing modes supported by an audio pin. |
| [IMiniportDMus::Init method](..\dmusicks\nf-dmusicks-iminiportdmus-init.md) | The Init method initializes the DMus miniport object. |
| [IMiniportDMus::NewStream method](..\dmusicks\nf-dmusicks-iminiportdmus-newstream.md) | The NewStream method creates a new instance of a logical stream associated with a specified physical channel. |
| [IMiniportDMus::Service method](..\dmusicks\nf-dmusicks-iminiportdmus-service.md) | This method does not currently need to be implemented in the miniport driver. The Service method is currently unused. |
| [IMiniportMidi::Init method](..\portcls\nf-portcls-iminiportmidi-init.md) | The Init method initializes the MIDI miniport object. |
| [IMiniportMidi::NewStream method](..\portcls\nf-portcls-iminiportmidi-newstream.md) | The NewStream method creates a new instance of a logical stream associated with a specified physical channel. |
| [IMiniportMidi::Service method](..\portcls\nf-portcls-iminiportmidi-service.md) | The Service method notifies the miniport driver of a request for service. |
| [IMiniportMidiStream::Read method](..\portcls\nf-portcls-iminiportmidistream-read.md) | The Read method reads data from an incoming MIDI stream. |
| [IMiniportMidiStream::SetFormat method](..\portcls\nf-portcls-iminiportmidistream-setformat.md) | The SetFormat method sets the KS data format of the MIDI stream. |
| [IMiniportMidiStream::SetState method](..\portcls\nf-portcls-iminiportmidistream-setstate.md) | The SetState method sets the stream's transport state to a new state value. |
| [IMiniportMidiStream::Write method](..\portcls\nf-portcls-iminiportmidistream-write.md) | The Write method writes data to an outgoing MIDI stream. |
| [IMiniportStreamAudioEngineNode2::SetStreamCurrentWritePositionForLastBuffer method](..\portcls\nf-portcls-iminiportstreamaudioenginenode2-setstreamcurrentwritepositionforlastbuffer.md) | Sets the current cursor position in the last audio data stream that was written to the audio buffer. |
| [IMiniportStreamAudioEngineNode::GetLfxState method](..\portcls\nf-portcls-iminiportstreamaudioenginenode-getlfxstate.md) | Gets the state of the local effects (LFX) node that is in the path of the audio stream. |
| [IMiniportStreamAudioEngineNode::GetStreamAttributeSteppings method](..\portcls\nf-portcls-iminiportstreamaudioenginenode-getstreamattributesteppings.md) | Gets the allowed stepping value for the audio stream attribute. |
| [IMiniportStreamAudioEngineNode::GetStreamChannelCount method](..\portcls\nf-portcls-iminiportstreamaudioenginenode-getstreamchannelcount.md) | Gets a count of the number of channels available for the stream. |
| [IMiniportStreamAudioEngineNode::GetStreamChannelMute method](..\portcls\nf-portcls-iminiportstreamaudioenginenode-getstreamchannelmute.md) | Gets the state of the Mute node in the path of the audio stream. |
| [IMiniportStreamAudioEngineNode::GetStreamChannelPeakMeter method](..\portcls\nf-portcls-iminiportstreamaudioenginenode-getstreamchannelpeakmeter.md) | Gets the value of the PeakMeter node in the path of the audio stream. |
| [IMiniportStreamAudioEngineNode::GetStreamChannelVolume method](..\portcls\nf-portcls-iminiportstreamaudioenginenode-getstreamchannelvolume.md) | Gets the current volume level that is applied to the audio stream. |
| [IMiniportStreamAudioEngineNode::GetStreamLinearBufferPosition method](..\portcls\nf-portcls-iminiportstreamaudioenginenode-getstreamlinearbufferposition.md) | Gets the number of bytes that the DMA has fetched from the audio buffer since the beginning of the stream. |
| [IMiniportStreamAudioEngineNode::GetStreamPresentationPosition method](..\portcls\nf-portcls-iminiportstreamaudioenginenode-getstreampresentationposition.md) | Gets the current cursor position in the audio data stream that is being rendered to the endpoint. |
| [IMiniportStreamAudioEngineNode::SetLfxState method](..\portcls\nf-portcls-iminiportstreamaudioenginenode-setlfxstate.md) | Sets the state of the local effects (LFX) node that is in the path of the audio stream. |
| [IMiniportStreamAudioEngineNode::SetStreamChannelMute method](..\portcls\nf-portcls-iminiportstreamaudioenginenode-setstreamchannelmute.md) | Sets the state of the Mute node in the path of the audio stream. |
| [IMiniportStreamAudioEngineNode::SetStreamChannelVolume method](..\portcls\nf-portcls-iminiportstreamaudioenginenode-setstreamchannelvolume.md) | Sets the volume level to be applied to the audio stream. |
| [IMiniportStreamAudioEngineNode::SetStreamCurrentWritePosition method](..\portcls\nf-portcls-iminiportstreamaudioenginenode-setstreamcurrentwriteposition.md) | Sets the current cursor position in the audio data stream that is being captured from the endpoint. |
| [IMiniportStreamAudioEngineNode::SetStreamLoopbackProtection method](..\portcls\nf-portcls-iminiportstreamaudioenginenode-setstreamloopbackprotection.md) | Sets the loopback protection status of the audio engine node. |
| [IMiniportTopology::Init method](..\portcls\nf-portcls-iminiporttopology-init.md) | The Init method initializes the topology miniport object. |
| [IMiniportWaveCyclic::Init method](..\portcls\nf-portcls-iminiportwavecyclic-init.md) | The Init method initializes the WaveCyclic miniport object. Initialization includes verification of the hardware using the resources specified in the resource list. |
| [IMiniportWaveCyclic::NewStream method](..\portcls\nf-portcls-iminiportwavecyclic-newstream.md) | The NewStream method creates a new instance of a logical stream that is associated with a specified physical channel. |
| [IMiniportWaveCyclicStream::GetPosition method](..\portcls\nf-portcls-iminiportwavecyclicstream-getposition.md) | The GetPosition method gets the current position of the stream. |
| [IMiniportWaveCyclicStream::NormalizePhysicalPosition method](..\portcls\nf-portcls-iminiportwavecyclicstream-normalizephysicalposition.md) | The NormalizePhysicalPosition method converts a physical buffer position to a time-based value. |
| [IMiniportWaveCyclicStream::SetFormat method](..\portcls\nf-portcls-iminiportwavecyclicstream-setformat.md) | The SetFormat method sets the KS data format of the wave stream. |
| [IMiniportWaveCyclicStream::SetNotificationFreq method](..\portcls\nf-portcls-iminiportwavecyclicstream-setnotificationfreq.md) | The SetNotificationFreq method controls the frequency at which notification interrupts are generated by setting the interval between successive interrupts. |
| [IMiniportWaveCyclicStream::SetState method](..\portcls\nf-portcls-iminiportwavecyclicstream-setstate.md) | The SetState method sets the new state of playback or recording for the stream. |
| [IMiniportWaveCyclicStream::Silence method](..\portcls\nf-portcls-iminiportwavecyclicstream-silence.md) | The Silence method is used to copy silence samples to a specified buffer. |
| [IMiniportWavePci::Init method](..\portcls\nf-portcls-iminiportwavepci-init.md) | The Init method initializes the WavePci miniport object. Initialization includes verification of the hardware using the resources specified in the resource list. |
| [IMiniportWavePci::NewStream method](..\portcls\nf-portcls-iminiportwavepci-newstream.md) | The NewStream method creates a new instance of a logical stream associated with a specified physical channel. |
| [IMiniportWavePci::Service method](..\portcls\nf-portcls-iminiportwavepci-service.md) | The Service method notifies the miniport driver of a request for service. |
| [IMiniportWavePciStream::GetAllocatorFraming method](..\portcls\nf-portcls-iminiportwavepcistream-getallocatorframing.md) | The GetAllocatorFraming method gets the preferred allocator-framing parameters for the stream. |
| [IMiniportWavePciStream::GetPosition method](..\portcls\nf-portcls-iminiportwavepcistream-getposition.md) | The GetPosition method gets the current position of the stream. |
| [IMiniportWavePciStream::MappingAvailable method](..\portcls\nf-portcls-iminiportwavepcistream-mappingavailable.md) | The MappingAvailable method indicates that a new mapping is available. |
| [IMiniportWavePciStream::NormalizePhysicalPosition method](..\portcls\nf-portcls-iminiportwavepcistream-normalizephysicalposition.md) | The NormalizePhysicalPosition method converts a physical buffer position to a time-based value. |
| [IMiniportWavePciStream::RevokeMappings method](..\portcls\nf-portcls-iminiportwavepcistream-revokemappings.md) | The RevokeMappings method revokes mappings that were previously obtained through IPortWavePciStream |
| [IMiniportWavePciStream::Service method](..\portcls\nf-portcls-iminiportwavepcistream-service.md) | The Service method notifies the miniport driver of a request for service. |
| [IMiniportWavePciStream::SetFormat method](..\portcls\nf-portcls-iminiportwavepcistream-setformat.md) | The SetFormat method sets the KS data format of the wave stream. |
| [IMiniportWavePciStream::SetState method](..\portcls\nf-portcls-iminiportwavepcistream-setstate.md) | The SetState method changes the state of the stream transport. |
| [IMiniportWaveRT::GetDeviceDescription method](..\portcls\nf-portcls-iminiportwavert-getdevicedescription.md) | The GetDeviceDescription method returns a pointer to a DEVICE_DESCRIPTION structure describing the device. |
| [IMiniportWaveRT::Init method](..\portcls\nf-portcls-iminiportwavert-init.md) | The Init method initializes the WaveRT miniport driver object. |
| [IMiniportWaveRT::NewStream method](..\portcls\nf-portcls-iminiportwavert-newstream.md) | The NewStream method creates a new instance of a WaveRT stream object. |
| [IMiniportWaveRTInputStream::GetReadPacket method](..\portcls\nf-portcls-iminiportwavertinputstream-getreadpacket.md) | Returns information about captured data. |
| [IMiniportWaveRTOutputStream::GetOutputStreamPresentationPosition method](..\portcls\nf-portcls-iminiportwavertoutputstream-getoutputstreampresentationposition.md) | Returns stream presentation information. |
| [IMiniportWaveRTOutputStream::GetPacketCount method](..\portcls\nf-portcls-iminiportwavertoutputstream-getpacketcount.md) | GetPacketCount returns the (1-based) count of packets completely transferred from the WaveRT buffer into hardware. |
| [IMiniportWaveRTOutputStream::SetWritePacket method](..\portcls\nf-portcls-iminiportwavertoutputstream-setwritepacket.md) | SetWritePacket informs the driver that the OS has written valid data to the WaveRT buffer. |
| [IMiniportWaveRTStreamNotification::AllocateBufferWithNotification method](..\portcls\nf-portcls-iminiportwavertstreamnotification-allocatebufferwithnotification.md) | The AllocateAudioBufferWithNotification method allocates a cyclic buffer for audio data when you want to implement DMA-driven event notification. If you do not want event notification, you must use IMiniportWaveRTStream |
| [IMiniportWaveRTStreamNotification::FreeBufferWithNotification method](..\portcls\nf-portcls-iminiportwavertstreamnotification-freebufferwithnotification.md) | The FreeBufferWithNotification method is used to free an audio buffer previously allocated with a call to IMiniportWaveRTStreamNotification |
| [IMiniportWaveRTStreamNotification::RegisterNotificationEvent method](..\portcls\nf-portcls-iminiportwavertstreamnotification-registernotificationevent.md) | The RegisterNotificationEvent method registers an event to be notified for DMA-driven event notification. |
| [IMiniportWaveRTStreamNotification::UnregisterNotificationEvent method](..\portcls\nf-portcls-iminiportwavertstreamnotification-unregisternotificationevent.md) | The UnregisterNotificationEvent method unregisters an event from DMA driven event notification. |
| [IMusicTechnology::SetTechnology method](..\portcls\nf-portcls-imusictechnology-settechnology.md) | The SetTechnology method changes the Technology member of each KSDATARANGE_MUSIC structure in the data ranges for the miniport driver's pins. |
| [IPinCount::PinCount method](..\portcls\nf-portcls-ipincount-pincount.md) | The PinCount method queries the miniport driver for its pin count. |
| [IPinName::GetPinName method](..\portcls\nf-portcls-ipinname-getpinname.md) | The GetPinName method retrieves the friendly name of an audio endpoint. |
| [IPortClsEtwHelper::MiniportWriteEtwEvent method](..\portcls\nf-portcls-iportclsetwhelper-miniportwriteetwevent.md) | The MiniportWriteEtwEvent method is used by an audio miniport driver for providing the information about an Event Tracing for Windows (ETW) event. |
| [IPortClsNotifications::AllocNotificationBuffer method](..\portcls\nf-portcls-iportclsnotifications-allocnotificationbuffer.md) | Allocates a buffer of the specified size, in the specified memory pool, for use in sending notifications, to allow for communications between audio modules and UWP apps. |
| [IPortClsNotifications::FreeNotificationBuffer method](..\portcls\nf-portcls-iportclsnotifications-freenotificationbuffer.md) | Frees a previously allocated IPortClsNotifications buffer. The buffer is used in sending notifications, to allow for communications between audio modules and UWP apps. |
| [IPortClsNotifications::SendNotification method](..\portcls\nf-portcls-iportclsnotifications-sendnotification.md) | Sends a notification to the listening UWP apps, to allow for communications between audio modules and UWP apps. |
| [IPortClsPnp::RegisterAdapterPnpManagement method](..\portcls\nf-portcls-iportclspnp-registeradapterpnpmanagement.md) | The RegisterAdapterPowerManagement method registers the PnP management interface of the adapter with PortCls. |
| [IPortClsPnp::UnregisterAdapterPnpManagement method](..\portcls\nf-portcls-iportclspnp-unregisteradapterpnpmanagement.md) | The UnRegisterAdapterPowerManagement method unregisters the PnP management interface of the adapter from PortCls. |
| [IPortClsPower::RegisterAdapterPowerManagement method](..\portcls\nf-portcls-iportclspower-registeradapterpowermanagement.md) | The RegisterAdapterPowerManagement method registers the power management interface of the adapter with PortCls. |
| [IPortClsPower::SetIdlePowerManagement method](..\portcls\nf-portcls-iportclspower-setidlepowermanagement.md) | The SetIdlePowerManagement method provides a way for the adapter driver to opt in or opt out of idle state detection. |
| [IPortClsPower::UnregisterAdapterPowerManagement method](..\portcls\nf-portcls-iportclspower-unregisteradapterpowermanagement.md) | The UnregisterAdapterPowerManagement method unregisters the adapter's power management interface with PortCls. |
| [IPortClsRuntimePower::RegisterPowerControlCallback method](..\portcls\nf-portcls-iportclsruntimepower-registerpowercontrolcallback.md) | The port class driver (PortCls) uses the RegisterPowerControlCallback method to register a power control callback. |
| [IPortClsRuntimePower::SendPowerControl method](..\portcls\nf-portcls-iportclsruntimepower-sendpowercontrol.md) | The port class driver (PortCls) uses the SendPowerControl method to send power control codes to the audio adapter. |
| [IPortClsRuntimePower::UnregisterPowerControlCallback method](..\portcls\nf-portcls-iportclsruntimepower-unregisterpowercontrolcallback.md) | The port class driver (PortCls) uses the UnregisterPowerControlCallback method to unregister a power control callback. |
| [IPortClsStreamResourceManager2::AddStreamResource2 method](..\portcls\nf-portcls-iportclsstreamresourcemanager2-addstreamresource2.md) | AddStreamResource2 adds a stream resource. Two type of stream resources are supported |
| [IPortClsVersion::GetVersion method](..\portcls\nf-portcls-iportclsversion-getversion.md) | The GetVersion method returns the version of the Windows operating system that the driver is running on. |
| [IPortDMus::Notify method](..\dmusicks\nf-dmusicks-iportdmus-notify.md) | The Notify method should be called from the miniport driver's interrupt service routine (ISR) when a hardware interrupt has occurred. |
| [IPortDMus::RegisterServiceGroup method](..\dmusicks\nf-dmusicks-iportdmus-registerservicegroup.md) | The RegisterServiceGroup method registers a service group with the DMus port driver. |
| [IPortEvents::AddEventToEventList method](..\portcls\nf-portcls-iportevents-addeventtoeventlist.md) | The AddEventToEventList method adds an event to the port driver's event list. |
| [IPortEvents::GenerateEventList method](..\portcls\nf-portcls-iportevents-generateeventlist.md) | The GenerateEventList method notifies clients through the port driver's list of event entries that a particular event has occurred. |
| [IPortMidi::Notify method](..\portcls\nf-portcls-iportmidi-notify.md) | The Notify method notifies the port driver that an interrupt indicating the progress of the DMA pointer has occurred. It should be called from the miniport driver's interrupt service routine (ISR). |
| [IPortMidi::RegisterServiceGroup method](..\portcls\nf-portcls-iportmidi-registerservicegroup.md) | The RegisterServiceGroup method registers the service group to be used for the IPortMidi |
| [IPortWMIRegistration::RegisterWMIProvider method](..\portcls\nf-portcls-iportwmiregistration-registerwmiprovider.md) | The RegisterWMIProvider method registers the Event Tracing for Windows (ETW) capability of the miniport driver with PortCls. |
| [IPortWMIRegistration::UnregisterWMIProvider method](..\portcls\nf-portcls-iportwmiregistration-unregisterwmiprovider.md) | The UnregisterWMIProvider method unregisters the Event Tracing for Windows (ETW) interface that was previously registered with a call to the RegisterWMIProvider method. The unregistration disables the ETW registration with PortCls. |
| [IPortWaveCyclic::NewMasterDmaChannel method](..\portcls\nf-portcls-iportwavecyclic-newmasterdmachannel.md) | The NewMasterDmaChannel method creates a new instance of a bus-master DMA channel. |
| [IPortWaveCyclic::NewSlaveDmaChannel method](..\portcls\nf-portcls-iportwavecyclic-newslavedmachannel.md) | The NewSlaveDmaChannel method creates a new instance of a subordinate DMA channel. |
| [IPortWaveCyclic::Notify method](..\portcls\nf-portcls-iportwavecyclic-notify.md) | The Notify method notifies the port driver that an interrupt indicating the progress of the DMA pointer has occurred. It should be called from the miniport driver's interrupt service routine (ISR). |
| [IPortWavePci::NewMasterDmaChannel method](..\portcls\nf-portcls-iportwavepci-newmasterdmachannel.md) | The NewMasterDmaChannel method creates a new instance of a bus-master DMA channel. |
| [IPortWavePci::Notify method](..\portcls\nf-portcls-iportwavepci-notify.md) | The Notify method notifies the port driver that an interrupt indicating the progress of the DMA pointer has occurred. |
| [IPortWavePciStream::GetMapping method](..\portcls\nf-portcls-iportwavepcistream-getmapping.md) | The GetMapping method obtains a mapping from the port driver and associates a tag with the mapping. |
| [IPortWavePciStream::ReleaseMapping method](..\portcls\nf-portcls-iportwavepcistream-releasemapping.md) | The ReleaseMapping method releases a mapping that was obtained by a previous call to IPortWavePciStream |
| [IPortWavePciStream::TerminatePacket method](..\portcls\nf-portcls-iportwavepcistream-terminatepacket.md) | The TerminatePacket method terminates the packet currently being mapped. |
| [IPortWaveRTStream::AllocateContiguousPagesForMdl method](..\portcls\nf-portcls-iportwavertstream-allocatecontiguouspagesformdl.md) | The AllocateContiguousPagesForMdl method allocates a list of contiguous, nonpaged, physical memory pages and returns a pointer to a memory descriptor list (MDL) that describes them. |
| [IPortWaveRTStream::AllocatePagesForMdl method](..\portcls\nf-portcls-iportwavertstream-allocatepagesformdl.md) | The AllocatePagesForMdl method allocates a list of nonpaged physical memory pages and returns a pointer to a memory descriptor list (MDL) that describes them. |
| [IPortWaveRTStream::FreePagesFromMdl method](..\portcls\nf-portcls-iportwavertstream-freepagesfrommdl.md) | The FreePagesFromMdl method frees a memory descriptor list (MDL). |
| [IPortWaveRTStream::GetPhysicalPageAddress method](..\portcls\nf-portcls-iportwavertstream-getphysicalpageaddress.md) | The GetPhysicalPageAddress method returns the physical address for a page within a memory descriptor list (MDL). |
| [IPortWaveRTStream::GetPhysicalPagesCount method](..\portcls\nf-portcls-iportwavertstream-getphysicalpagescount.md) | The GetPhysicalPagesCount method returns the count of the physical pages in a memory descriptor list (MDL). |
| [IPortWaveRTStream::MapAllocatedPages method](..\portcls\nf-portcls-iportwavertstream-mapallocatedpages.md) | The MapAllocatedPages method maps a list of previously allocated physical pages into a contiguous block of virtual memory that is accessible from kernel-mode. |
| [IPortWaveRTStream::UnmapAllocatedPages method](..\portcls\nf-portcls-iportwavertstream-unmapallocatedpages.md) | The UnmapAllocatedPages method releases a mapping. |
| [IPositionNotify::PositionNotify method](..\dmusicks\nf-dmusicks-ipositionnotify-positionnotify.md) | Byte position notify for MXF graph. |
| [IPowerNotify::PowerChangeNotify method](..\portcls\nf-portcls-ipowernotify-powerchangenotify.md) | The PowerChangeNotify method notifies the miniport driver of changes in the power state. |
| [IPreFetchOffset::SetPreFetchOffset method](..\portcls\nf-portcls-iprefetchoffset-setprefetchoffset.md) | The SetPreFetchOffset method sets the prefetch offset, which is the number of bytes of data separating the write cursor from the play cursor in a DirectSound output stream. |
| [IRegistryKey::DeleteKey method](..\portcls\nf-portcls-iregistrykey-deletekey.md) | The DeleteKey method deletes the registry key. |
| [IRegistryKey::EnumerateKey method](..\portcls\nf-portcls-iregistrykey-enumeratekey.md) | The EnumerateKey method returns information about the subkeys of the open key. |
| [IRegistryKey::EnumerateValueKey method](..\portcls\nf-portcls-iregistrykey-enumeratevaluekey.md) | The EnumerateValueKey method returns information about a registry entry that contains a value key. |
| [IRegistryKey::NewSubKey method](..\portcls\nf-portcls-iregistrykey-newsubkey.md) | The NewSubKey method either creates a new registry subkey or opens an existing subkey under the key represented by the IRegistryKey object. |
| [IRegistryKey::QueryKey method](..\portcls\nf-portcls-iregistrykey-querykey.md) | The QueryKey method retrieves information about a registry key, including the key name, key class, and the number of subkeys and their sizes. |
| [IRegistryKey::QueryRegistryValues method](..\portcls\nf-portcls-iregistrykey-queryregistryvalues.md) | The QueryRegistryValues method allows the caller to query several values from the registry with a single call. |
| [IRegistryKey::QueryValueKey method](..\portcls\nf-portcls-iregistrykey-queryvaluekey.md) | The QueryValueKey method retrieves information about a registry key's value entries, including their names, types, data sizes, and values. |
| [IRegistryKey::SetValueKey method](..\portcls\nf-portcls-iregistrykey-setvaluekey.md) | The SetValueKey method replaces or creates a value entry under the open key. |
| [IResourceList::AddEntry method](..\portcls\nf-portcls-iresourcelist-addentry.md) | The AddEntry method adds an entry to a resource list. |
| [IResourceList::AddEntryFromParent method](..\portcls\nf-portcls-iresourcelist-addentryfromparent.md) | The AddEntryFromParent method adds to a resource list an entry found in the resource list's parent list. |
| [IResourceList::FindTranslatedEntry method](..\portcls\nf-portcls-iresourcelist-findtranslatedentry.md) | The FindTranslatedEntry method returns a pointer to a translated entry of the specified type, or NULL if no such entry is found. |
| [IResourceList::FindUntranslatedEntry method](..\portcls\nf-portcls-iresourcelist-finduntranslatedentry.md) | The FindUntranslatedEntry method returns a pointer to an untranslated entry of the specified type, or NULL if no such pointer is found. |
| [IResourceList::NumberOfEntries method](..\portcls\nf-portcls-iresourcelist-numberofentries.md) | The NumberOfEntries method returns the number of resource items in the resource list. |
| [IResourceList::NumberOfEntriesOfType method](..\portcls\nf-portcls-iresourcelist-numberofentriesoftype.md) | The NumberOfEntriesOfType method returns the number of resource items of a given type in the resource list. For each resource type, a macro is defined to call this method as previously described. |
| [IResourceList::TranslatedList method](..\portcls\nf-portcls-iresourcelist-translatedlist.md) | The TranslatedList method returns the list of translated resources. |
| [IResourceList::UntranslatedList method](..\portcls\nf-portcls-iresourcelist-untranslatedlist.md) | The UntranslatedList method returns the list of untranslated resources. |
| [IServiceGroup::AddMember method](..\portcls\nf-portcls-iservicegroup-addmember.md) | The AddMember method adds a member to the service group. |
| [IServiceGroup::CancelDelayedService method](..\portcls\nf-portcls-iservicegroup-canceldelayedservice.md) | The CancelDelayedService method cancels the previously requested delayed service. |
| [IServiceGroup::RemoveMember method](..\portcls\nf-portcls-iservicegroup-removemember.md) | The RemoveMember method removes the specified member from the service group. |
| [IServiceGroup::RequestDelayedService method](..\portcls\nf-portcls-iservicegroup-requestdelayedservice.md) | The RequestDelayedService method requests service after the specified delay. |
| [IServiceGroup::RequestService method](..\portcls\nf-portcls-iservicegroup-requestservice.md) | TBD |
| [IServiceGroup::SupportDelayedService method](..\portcls\nf-portcls-iservicegroup-supportdelayedservice.md) | The SupportDelayedService method indicates that the service group should prepare to support delayed service. |
| [IServiceSink::RequestService method](..\portcls\nf-portcls-iservicesink-requestservice.md) | The RequestService method is called to forward a service request to an IServiceSink object. |
| [ISynthSinkDMus::RefTimeToSample method](..\dmusicks\nf-dmusicks-isynthsinkdmus-reftimetosample.md) | The RefTimeToSample method converts a reference time into a sample time. |
| [ISynthSinkDMus::Render method](..\dmusicks\nf-dmusicks-isynthsinkdmus-render.md) | The Render method renders wave data into a destination sink. |
| [ISynthSinkDMus::SampleToRefTime method](..\dmusicks\nf-dmusicks-isynthsinkdmus-sampletoreftime.md) | The SampleToRefTime method converts a sample time to a reference time. |
| [ISynthSinkDMus::SyncToMaster method](..\dmusicks\nf-dmusicks-isynthsinkdmus-synctomaster.md) | The SyncToMaster method allows synchronization to the master clock in order to avoid drift. |
| [IUnregisterPhysicalConnection::UnregisterPhysicalConnection method](..\portcls\nf-portcls-iunregisterphysicalconnection-unregisterphysicalconnection.md) | The UnregisterPhysicalConnection method deletes the registration of a physical connection that was registered by a previous call to PcRegisterPhysicalConnection. |
| [IUnregisterPhysicalConnection::UnregisterPhysicalConnectionFromExternal method](..\portcls\nf-portcls-iunregisterphysicalconnection-unregisterphysicalconnectionfromexternal.md) | The UnregisterPhysicalConnectionFromExternal method deletes the registration of a physical connection that was registered by a previous call to PcRegisterPhysicalConnectionFromExternal. |
| [IUnregisterPhysicalConnection::UnregisterPhysicalConnectionToExternal method](..\portcls\nf-portcls-iunregisterphysicalconnection-unregisterphysicalconnectiontoexternal.md) | The UnregisterPhysicalConnectionToExternal method deletes the registration of a physical connection that was registered by a previous call to PcRegisterPhysicalConnectionToExternal. |
| [IUnregisterSubdevice::UnregisterSubdevice method](..\portcls\nf-portcls-iunregistersubdevice-unregistersubdevice.md) | The UnregisterSubdevice method deletes the registration of a subdevice that was previously registered by a call to PcRegisterSubdevice. |
