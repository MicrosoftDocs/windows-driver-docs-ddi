---
UID: TP:audio
author: windows-driver-content
ms.assetid: 91b97f1d-92f1-3c32-955a-dd6524d5b764
ms.author: windowsdriverdev
ms.date: 07/10/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Audio

## -description

These headers are used to create Microsoft Windows Driver Model (WDM) audio drivers. These drivers control audio hardware that render and capture streams containing audio data. 

To develop Audio drivers, you need these headers:

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

For programming information, see [Audio Devices Design Guide](https://docs.microsoft.com/windows-hardware/drivers/audio).
 

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [PALLOCATE_CAPTURE_DMA_ENGINE callback function](..\hdaudio\nc-hdaudio-pallocate_capture_dma_engine.md) | The AllocateCaptureDmaEngine routine allocates a DMA engine for a capture stream.The function pointer type for an AllocateCaptureDmaEngine routine is defined as follows. |
| [PALLOCATE_CONTIGUOUS_DMA_BUFFER callback function](..\hdaudio\nc-hdaudio-pallocate_contiguous_dma_buffer.md) | The AllocateContiguousDmaBuffer routine allocates a DMA buffer that consists of a single, contiguous block of physical memory.The function pointer type for an AllocateContiguousDmaBuffer routine is defined as follows. |
| [PALLOCATE_DMA_BUFFER callback function](..\hdaudio\nc-hdaudio-pallocate_dma_buffer.md) | The AllocateDmaBuffer routine allocates a data buffer in system memory for a DMA engine.The function pointer type for an AllocateDmaBuffer routine is defined as follows. |
| [PALLOCATE_DMA_BUFFER_WITH_NOTIFICATION callback function](..\hdaudio\nc-hdaudio-pallocate_dma_buffer_with_notification.md) | The AllocateDmaBufferWithNotification routine allocates a data buffer in system memory for a DMA engine.The function pointer type for an AllocateDmaBufferWithNotification routine is defined as follows. |
| [PALLOCATE_RENDER_DMA_ENGINE callback function](..\hdaudio\nc-hdaudio-pallocate_render_dma_engine.md) | The AllocateRenderDmaEngine routine allocates a DMA engine for a render stream.The function pointer type for an AllocateRenderDmaEngine routine is defined as follows. |
| [PCHANGE_BANDWIDTH_ALLOCATION callback function](..\hdaudio\nc-hdaudio-pchange_bandwidth_allocation.md) | The ChangeBandwidthAllocation routine changes a DMA engine's bandwidth allocation on the HD Audio Link.The function pointer type for a ChangeBandwidthAllocation routine is defined as follows. |
| [PCPFNEVENT_HANDLER callback function](..\portcls\nc-portcls-pcpfnevent_handler.md) | An EventHandler routine processes event requests. |
| [PFNDRMADDCONTENTHANDLERS callback function](..\drmk\nc-drmk-pfndrmaddcontenthandlers.md) | This callback function is reserved for system use. |
| [PFNDRMCREATECONTENTMIXED callback function](..\drmk\nc-drmk-pfndrmcreatecontentmixed.md) | This callback function is reserved for system use. |
| [PFNDRMDESTROYCONTENT callback function](..\drmk\nc-drmk-pfndrmdestroycontent.md) | This callback function is reserved for system use. |
| [PFNDRMFORWARDCONTENTTODEVICEOBJECT callback function](..\drmk\nc-drmk-pfndrmforwardcontenttodeviceobject.md) | This callback function is reserved for system use. |
| [PFNDRMFORWARDCONTENTTOFILEOBJECT callback function](..\drmk\nc-drmk-pfndrmforwardcontenttofileobject.md) | This callback function is reserved for system use. |
| [PFNDRMFORWARDCONTENTTOINTERFACE callback function](..\drmk\nc-drmk-pfndrmforwardcontenttointerface.md) | This callback function is reserved for system use. |
| [PFNDRMGETCONTENTRIGHTS callback function](..\drmk\nc-drmk-pfndrmgetcontentrights.md) | This callback function is reserved for system use. |
| [PFREE_CONTIGUOUS_DMA_BUFFER callback function](..\hdaudio\nc-hdaudio-pfree_contiguous_dma_buffer.md) | The FreeContiguousDmaBuffer routine frees a DMA buffer and buffer descriptor list (BDL) that were allocated by a call to AllocateContiguousDmaBuffer.The function pointer type for a FreeContiguousDmaBuffer routine is defined as follows. |
| [PFREE_DMA_BUFFER callback function](..\hdaudio\nc-hdaudio-pfree_dma_buffer.md) | The FreeDmaBuffer routine frees a DMA buffer that was previously allocated by a call to AllocateDmaBuffer.The function pointer type for a FreeDmaBuffer routine is defined as follows. |
| [PFREE_DMA_BUFFER_WITH_NOTIFICATION callback function](..\hdaudio\nc-hdaudio-pfree_dma_buffer_with_notification.md) | The FreeDmaBufferWithNotification routine frees a DMA buffer that was previously allocated by a call to AllocateDmaBufferWithNotification.The function pointer type for a FreeDmaBufferWithNotification routine is defined as follows. |
| [PFREE_DMA_ENGINE callback function](..\hdaudio\nc-hdaudio-pfree_dma_engine.md) | The FreeDmaEngine routine frees a DMA engine that was previously allocated by a call to AllocateCaptureDmaEngine or AllocateRenderDmaEngine.The function pointer type for a FreeDmaEngine routine is defined as follows. |
| [PGET_DEVICE_INFORMATION callback function](..\hdaudio\nc-hdaudio-pget_device_information.md) | The GetDeviceInformation routine retrieves information about the HD Audio controller device.The function pointer type for a GetDeviceInformation routine is defined as follows. |
| [PGET_LINK_POSITION_REGISTER callback function](..\hdaudio\nc-hdaudio-pget_link_position_register.md) | The GetLinkPositionRegister routine retrieves a pointer to a DMA engine's link position register.The function pointer type for a GetLinkPositionRegister routine is defined as follows. |
| [PGET_RESOURCE_INFORMATION callback function](..\hdaudio\nc-hdaudio-pget_resource_information.md) | The GetResourceInformation routine retrieves information about hardware resources.The function pointer type for a GetResourceInformation routine is defined as follows. |
| [PGET_WALL_CLOCK_REGISTER callback function](..\hdaudio\nc-hdaudio-pget_wall_clock_register.md) | The GetWallClockRegister routine retrieves a pointer to the wall clock register.The function pointer type for a GetWallClockRegister routine is defined as follows. |
| [PHDAUDIO_BDL_ISR callback function](..\hdaudio\nc-hdaudio-phdaudio_bdl_isr.md) | The HDAudioBdlIsr routine is the ISR that the HD Audio bus driver calls each time an IOC interrupt occurs on the stream. It is a function pointer of type PHDAUDIO_BDL_ISR, which is defined as follows. |
| [PHDAUDIO_TRANSFER_COMPLETE_CALLBACK callback function](..\hdaudio\nc-hdaudio-phdaudio_transfer_complete_callback.md) | HDAudio codec transfer complete callback function. PHDAUDIO_TRANSFER_COMPLETE_CALLBACK is used by the PTRANSFER_CODEC_VERBS callback function. |
| [PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK callback function](..\hdaudio\nc-hdaudio-phdaudio_unsolicited_response_callback.md) | HDAudio codec unsolicited response callback function. PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK is used by the PREGISTER_EVENT_CALLBACK callback function. |
| [PREGISTER_EVENT_CALLBACK callback function](..\hdaudio\nc-hdaudio-pregister_event_callback.md) | The RegisterEventCallback routine registers a callback routine for an unsolicited response from a codec or codecs.The function pointer type for a RegisterEventCallback routine is defined as follows. |
| [PREGISTER_NOTIFICATION_EVENT callback function](..\hdaudio\nc-hdaudio-pregister_notification_event.md) | The RegisterNotificationEvent routine registers a kernel event so that it can receive DMA progress notifications.The function pointer type for a RegisterNotificationEvent routine is defined as follows. |
| [PSETUP_DMA_ENGINE_WITH_BDL callback function](..\hdaudio\nc-hdaudio-psetup_dma_engine_with_bdl.md) | The SetupDmaEngineWithBdl routine sets up a DMA engine to use a caller-allocated DMA buffer.The function pointer type for a SetupDmaEngineWithBdl routine is defined as follows. |
| [PSET_DMA_ENGINE_STATE callback function](..\hdaudio\nc-hdaudio-pset_dma_engine_state.md) | The SetDmaEngineState routine sets the state of one or more DMA engines to the Running, Stopped, Paused, or Reset state.The function pointer type for a SetDmaEngineState routine is defined as follows. |
| [PTRANSFER_CODEC_VERBS callback function](..\hdaudio\nc-hdaudio-ptransfer_codec_verbs.md) | The TransferCodecVerbs routine transfers one or more commands to a codec or codecs and retrieves the responses to those commands.The function pointer type for a TransferCodecVerbs routine is defined as follows. |
| [PUNREGISTER_EVENT_CALLBACK callback function](..\hdaudio\nc-hdaudio-punregister_event_callback.md) | The UnregisterEventCallback routine deletes the registration of an event callback that was previously registered by a call to RegisterEventCallback.The function pointer type for an UnregisterEventCallback routine is defined as follows. |
| [PUNREGISTER_NOTIFICATION_EVENT callback function](..\hdaudio\nc-hdaudio-punregister_notification_event.md) | The UnregisterNotificationEvent routine deletes the registration of an event that was previously registered by a call to RegisterNotificationEvent.The function pointer type for an UnregisterNotificationEvent routine is defined as follows. |





## Methods

| Title   | Description   |
| ---- |:---- |
| [IAdapterPowerManagement2::PowerChangeState2](..\portcls\nf-portcls-iadapterpowermanagement2-powerchangestate2.md) | Portcls calls the IAdapterPowerManagement2 |
| [IAdapterPowerManagement3::D3ExitLatencyChanged](..\portcls\nf-portcls-iadapterpowermanagement3-d3exitlatencychanged.md) | PortCls calls the D3ExitLatencyChanged method while the device is in sleep (D3) power state, to provide a new exit latency value. |
| [IAdapterPowerManagement::PowerChangeState](..\portcls\nf-portcls-iadapterpowermanagement-powerchangestate.md) | The PowerChangeState method requests that the device change to a new power state. |
| [IAdapterPowerManagement::QueryDeviceCapabilities](..\portcls\nf-portcls-iadapterpowermanagement-querydevicecapabilities.md) | The QueryDeviceCapabilities method is called by PortCls in response to a Plug and Play IRP_MN_QUERY_CAPABILITIES IRP. |
| [IAdapterPowerManagement::QueryPowerChangeState](..\portcls\nf-portcls-iadapterpowermanagement-querypowerchangestate.md) | The QueryPowerChangeState method is called by PortCls in response to the receipt of an IRP_MN_QUERY_POWER power IRP. |
| [IAllocatorMXF::GetBufferSize](..\dmusicks\nf-dmusicks-iallocatormxf-getbuffersize.md) | The GetBufferSize method gets the buffer size from the allocator. |
| [IAllocatorMXF::GetBuffer](..\dmusicks\nf-dmusicks-iallocatormxf-getbuffer.md) | The GetBuffer method allocates a buffer for long MIDI events. |
| [IAllocatorMXF::GetMessage](..\dmusicks\nf-dmusicks-iallocatormxf-getmessage.md) | The GetMessage method serves as the retrieval point for any DirectMusic kernel-mode component that utilizes the port driver's allocator to reuse DMUS_KERNEL_EVENT structures. |
| [IAllocatorMXF::PutBuffer](..\dmusicks\nf-dmusicks-iallocatormxf-putbuffer.md) | This method is not currently used by the miniport driver. The PutBuffer method passes a buffer to the allocator, but this occurs automatically when IMXF |
| [IDrmAudioStream::SetContentId](..\drmk\nf-drmk-idrmaudiostream-setcontentid.md) | The SetContentId method sets the DRM content ID and its assigned DRM content rights on a KS audio stream. |
| [IDrmPort2::AddContentHandlers](..\portcls\nf-portcls-idrmport2-addcontenthandlers.md) | The AddContentHandlers method provides the system with a list of functions that handle protected content. |
| [IDrmPort2::ForwardContentToDeviceObject](..\portcls\nf-portcls-idrmport2-forwardcontenttodeviceobject.md) | The ForwardContentToDeviceObject method accepts a device object representing a device to which the caller intends to forward protected content. |
| [IInterruptSync::CallSynchronizedRoutine](..\portcls\nf-portcls-iinterruptsync-callsynchronizedroutine.md) | The CallSynchronizedRoutine method calls a routine that is not an interrupt service routine (ISR) but whose execution needs to be synchronized with ISRs. |
| [IInterruptSync::Connect](..\portcls\nf-portcls-iinterruptsync-connect.md) | The Connect method connects the synchronization object to the interrupt. |
| [IInterruptSync::Disconnect](..\portcls\nf-portcls-iinterruptsync-disconnect.md) | The Disconnect method disconnects the synchronization object from the interrupt. |
| [IInterruptSync::GetKInterrupt](..\portcls\nf-portcls-iinterruptsync-getkinterrupt.md) | The GetKInterrupt method gets a WDM interrupt object from a port-class synchronization object. |
| [IInterruptSync::RegisterServiceRoutine](..\portcls\nf-portcls-iinterruptsync-registerserviceroutine.md) | The RegisterServiceRoutine method registers an interrupt service routine (ISR) that is to be called when an interrupt occurs. |
| [IKeywordDetectorOemAdapter::BuildArmingPatternData](..\keyworddetectoroemadapter\nf-keyworddetectoroemadapter-ikeyworddetectoroemadapter-buildarmingpatterndata.md) | The BuildArmingPatternData method is called by the operating system to build OEM-specific pattern data that includes any keyword and user-specific model data for detection. |
| [IKeywordDetectorOemAdapter::ComputeAndAddUserModelData](..\keyworddetectoroemadapter\nf-keyworddetectoroemadapter-ikeyworddetectoroemadapter-computeandaddusermodeldata.md) | The ComputeAndAddUserModelData method is used by the training user experience to compute the user-specific information relative to the user-independent keyword. |
| [IKeywordDetectorOemAdapter::GetCapabilities](..\keyworddetectoroemadapter\nf-keyworddetectoroemadapter-ikeyworddetectoroemadapter-getcapabilities.md) | The GetCapabilities method returns the keywords and languages supported by the object. |
| [IKeywordDetectorOemAdapter::ParseDetectionResultData](..\keyworddetectoroemadapter\nf-keyworddetectoroemadapter-ikeyworddetectoroemadapter-parsedetectionresultdata.md) | The ParseDetectionResultData method is called by the operating system after handling a keyword detection event and after retrieving the result data from KSPROPERTY_SOUNDDETECTOR_MATCHRESULT. |
| [IKeywordDetectorOemAdapter::VerifyUserKeyword](..\keyworddetectoroemadapter\nf-keyworddetectoroemadapter-ikeyworddetectoroemadapter-verifyuserkeyword.md) | The VerifyUserKeyword method is used by the training user experience to verify that one instance of a spoken utterance, captured during training, matches a predefined keyword within some tolerance. |
| [IMasterClock::GetTime](..\dmusicks\nf-dmusicks-imasterclock-gettime.md) | The GetTime method retrieves the current reference time read from the master clock. |
| [IMiniportAudioEngineNode::GetAudioEngineDescriptor](..\portcls\nf-portcls-iminiportaudioenginenode-getaudioenginedescriptor.md) | Gets the descriptor for the audio engine node. |
| [IMiniportAudioEngineNode::GetBufferSizeRange](..\portcls\nf-portcls-iminiportaudioenginenode-getbuffersizerange.md) | Gets the minimum and maximum buffer size that the hardware audio engine can support. |
| [IMiniportAudioEngineNode::GetDeviceAttributeSteppings](..\portcls\nf-portcls-iminiportaudioenginenode-getdeviceattributesteppings.md) | Gets the allowed stepping value for the audio device attribute. |
| [IMiniportAudioEngineNode::GetDeviceChannelCount](..\portcls\nf-portcls-iminiportaudioenginenode-getdevicechannelcount.md) | Gets a count of the number of channels supported by the audio device. |
| [IMiniportAudioEngineNode::GetDeviceChannelMute](..\portcls\nf-portcls-iminiportaudioenginenode-getdevicechannelmute.md) | Gets the state of the Mute node for the audio device channel. |
| [IMiniportAudioEngineNode::GetDeviceChannelPeakMeter](..\portcls\nf-portcls-iminiportaudioenginenode-getdevicechannelpeakmeter.md) | Gets the PeakMeter value for the audio device channel. |
| [IMiniportAudioEngineNode::GetDeviceChannelVolume](..\portcls\nf-portcls-iminiportaudioenginenode-getdevicechannelvolume.md) | Gets the volume level for a given channel of the audio device. |
| [IMiniportAudioEngineNode::GetDeviceFormat](..\portcls\nf-portcls-iminiportaudioenginenode-getdeviceformat.md) | Gets the audio data format for an audio device. |
| [IMiniportAudioEngineNode::GetEngineFormatSize](..\portcls\nf-portcls-iminiportaudioenginenode-getengineformatsize.md) | Gets the format type and the buffer size for the audio engine's audio data format. |
| [IMiniportAudioEngineNode::GetGfxState](..\portcls\nf-portcls-iminiportaudioenginenode-getgfxstate.md) | Gets the state of the global effects (GFX) node in the audio engine. |
| [IMiniportAudioEngineNode::GetMixFormat](..\portcls\nf-portcls-iminiportaudioenginenode-getmixformat.md) | Gets the audio data format for the audio engine mixer. |
| [IMiniportAudioEngineNode::GetSupportedDeviceFormats](..\portcls\nf-portcls-iminiportaudioenginenode-getsupporteddeviceformats.md) | Gets the supported audio data formats for the audio device. |
| [IMiniportAudioEngineNode::SetDeviceChannelMute](..\portcls\nf-portcls-iminiportaudioenginenode-setdevicechannelmute.md) | Sets the state of the Mute node for the audio device channel. |
| [IMiniportAudioEngineNode::SetDeviceChannelVolume](..\portcls\nf-portcls-iminiportaudioenginenode-setdevicechannelvolume.md) | Sets the volume level for a given channel of the audio device. |
| [IMiniportAudioEngineNode::SetDeviceFormat](..\portcls\nf-portcls-iminiportaudioenginenode-setdeviceformat.md) | Sets the audio data format for an audio device. |
| [IMiniportAudioEngineNode::SetGfxState](..\portcls\nf-portcls-iminiportaudioenginenode-setgfxstate.md) | Sets the state of the global effects (GFX) node in the audio engine. |
| [IMiniportAudioSignalProcessing::GetModes](..\portcls\nf-portcls-iminiportaudiosignalprocessing-getmodes.md) | The GetModes method, Gets the audio signal processing modes supported by an audio pin. |
| [IMiniportDMus::Init](..\dmusicks\nf-dmusicks-iminiportdmus-init.md) | The Init method initializes the DMus miniport object. |
| [IMiniportDMus::NewStream](..\dmusicks\nf-dmusicks-iminiportdmus-newstream.md) | The NewStream method creates a new instance of a logical stream associated with a specified physical channel. |
| [IMiniportDMus::Service](..\dmusicks\nf-dmusicks-iminiportdmus-service.md) | This method does not currently need to be implemented in the miniport driver. The Service method is currently unused. |
| [IMiniportMidi::Init](..\portcls\nf-portcls-iminiportmidi-init.md) | The Init method initializes the MIDI miniport object. |
| [IMiniportMidi::NewStream](..\portcls\nf-portcls-iminiportmidi-newstream.md) | The NewStream method creates a new instance of a logical stream associated with a specified physical channel. |
| [IMiniportMidi::Service](..\portcls\nf-portcls-iminiportmidi-service.md) | The Service method notifies the miniport driver of a request for service. |
| [IMiniportMidiStream::Read](..\portcls\nf-portcls-iminiportmidistream-read.md) | The Read method reads data from an incoming MIDI stream. |
| [IMiniportMidiStream::SetFormat](..\portcls\nf-portcls-iminiportmidistream-setformat.md) | The SetFormat method sets the KS data format of the MIDI stream. |
| [IMiniportMidiStream::SetState](..\portcls\nf-portcls-iminiportmidistream-setstate.md) | The SetState method sets the stream's transport state to a new state value. |
| [IMiniportMidiStream::Write](..\portcls\nf-portcls-iminiportmidistream-write.md) | The Write method writes data to an outgoing MIDI stream. |
| [IMiniportStreamAudioEngineNode2::SetStreamCurrentWritePositionForLastBuffer](..\portcls\nf-portcls-iminiportstreamaudioenginenode2-setstreamcurrentwritepositionforlastbuffer.md) | Sets the current cursor position in the last audio data stream that was written to the audio buffer. |
| [IMiniportStreamAudioEngineNode::GetLfxState](..\portcls\nf-portcls-iminiportstreamaudioenginenode-getlfxstate.md) | Gets the state of the local effects (LFX) node that is in the path of the audio stream. |
| [IMiniportStreamAudioEngineNode::GetStreamAttributeSteppings](..\portcls\nf-portcls-iminiportstreamaudioenginenode-getstreamattributesteppings.md) | Gets the allowed stepping value for the audio stream attribute. |
| [IMiniportStreamAudioEngineNode::GetStreamChannelCount](..\portcls\nf-portcls-iminiportstreamaudioenginenode-getstreamchannelcount.md) | Gets a count of the number of channels available for the stream. |
| [IMiniportStreamAudioEngineNode::GetStreamChannelMute](..\portcls\nf-portcls-iminiportstreamaudioenginenode-getstreamchannelmute.md) | Gets the state of the Mute node in the path of the audio stream. |
| [IMiniportStreamAudioEngineNode::GetStreamChannelPeakMeter](..\portcls\nf-portcls-iminiportstreamaudioenginenode-getstreamchannelpeakmeter.md) | Gets the value of the PeakMeter node in the path of the audio stream. |
| [IMiniportStreamAudioEngineNode::GetStreamChannelVolume](..\portcls\nf-portcls-iminiportstreamaudioenginenode-getstreamchannelvolume.md) | Gets the current volume level that is applied to the audio stream. |
| [IMiniportStreamAudioEngineNode::GetStreamLinearBufferPosition](..\portcls\nf-portcls-iminiportstreamaudioenginenode-getstreamlinearbufferposition.md) | Gets the number of bytes that the DMA has fetched from the audio buffer since the beginning of the stream. |
| [IMiniportStreamAudioEngineNode::GetStreamPresentationPosition](..\portcls\nf-portcls-iminiportstreamaudioenginenode-getstreampresentationposition.md) | Gets the current cursor position in the audio data stream that is being rendered to the endpoint. |
| [IMiniportStreamAudioEngineNode::SetLfxState](..\portcls\nf-portcls-iminiportstreamaudioenginenode-setlfxstate.md) | Sets the state of the local effects (LFX) node that is in the path of the audio stream. |
| [IMiniportStreamAudioEngineNode::SetStreamChannelMute](..\portcls\nf-portcls-iminiportstreamaudioenginenode-setstreamchannelmute.md) | Sets the state of the Mute node in the path of the audio stream. |
| [IMiniportStreamAudioEngineNode::SetStreamChannelVolume](..\portcls\nf-portcls-iminiportstreamaudioenginenode-setstreamchannelvolume.md) | Sets the volume level to be applied to the audio stream. |
| [IMiniportStreamAudioEngineNode::SetStreamCurrentWritePosition](..\portcls\nf-portcls-iminiportstreamaudioenginenode-setstreamcurrentwriteposition.md) | Sets the current cursor position in the audio data stream that is being captured from the endpoint. |
| [IMiniportStreamAudioEngineNode::SetStreamLoopbackProtection](..\portcls\nf-portcls-iminiportstreamaudioenginenode-setstreamloopbackprotection.md) | Sets the loopback protection status of the audio engine node. |
| [IMiniportTopology::Init](..\portcls\nf-portcls-iminiporttopology-init.md) | The Init method initializes the topology miniport object. |
| [IMiniportWaveCyclic::Init method](..\portcls\nf-portcls-iminiportwavecyclic-init.md) | The Init method initializes the WaveCyclic miniport object. Initialization includes verification of the hardware using the resources specified in the resource list. |
| [IMiniportWaveCyclic::NewStream](..\portcls\nf-portcls-iminiportwavecyclic-newstream.md) | The NewStream method creates a new instance of a logical stream that is associated with a specified physical channel. |
| [IMiniportWaveCyclicStream::GetPosition](..\portcls\nf-portcls-iminiportwavecyclicstream-getposition.md) | The GetPosition method gets the current position of the stream. |
| [IMiniportWaveCyclicStream::NormalizePhysicalPosition](..\portcls\nf-portcls-iminiportwavecyclicstream-normalizephysicalposition.md) | The NormalizePhysicalPosition method converts a physical buffer position to a time-based value. |
| [IMiniportWaveCyclicStream::SetFormat](..\portcls\nf-portcls-iminiportwavecyclicstream-setformat.md) | The SetFormat method sets the KS data format of the wave stream. |
| [IMiniportWaveCyclicStream::SetNotificationFreq](..\portcls\nf-portcls-iminiportwavecyclicstream-setnotificationfreq.md) | The SetNotificationFreq method controls the frequency at which notification interrupts are generated by setting the interval between successive interrupts. |
| [IMiniportWaveCyclicStream::SetState](..\portcls\nf-portcls-iminiportwavecyclicstream-setstate.md) | The SetState method sets the new state of playback or recording for the stream. |
| [IMiniportWaveCyclicStream::Silence](..\portcls\nf-portcls-iminiportwavecyclicstream-silence.md) | The Silence method is used to copy silence samples to a specified buffer. |
| [IMiniportWavePci::Init](..\portcls\nf-portcls-iminiportwavepci-init.md) | The Init method initializes the WavePci miniport object. Initialization includes verification of the hardware using the resources specified in the resource list. |
| [IMiniportWavePci::NewStream](..\portcls\nf-portcls-iminiportwavepci-newstream.md) | The NewStream method creates a new instance of a logical stream associated with a specified physical channel. |
| [IMiniportWavePci::Service](..\portcls\nf-portcls-iminiportwavepci-service.md) | The Service method notifies the miniport driver of a request for service. |
| [IMiniportWavePciStream::GetAllocatorFraming](..\portcls\nf-portcls-iminiportwavepcistream-getallocatorframing.md) | The GetAllocatorFraming method gets the preferred allocator-framing parameters for the stream. |
| [IMiniportWavePciStream::GetPosition](..\portcls\nf-portcls-iminiportwavepcistream-getposition.md) | The GetPosition method gets the current position of the stream. |
| [IMiniportWavePciStream::MappingAvailable](..\portcls\nf-portcls-iminiportwavepcistream-mappingavailable.md) | The MappingAvailable method indicates that a new mapping is available. |
| [IMiniportWavePciStream::NormalizePhysicalPosition](..\portcls\nf-portcls-iminiportwavepcistream-normalizephysicalposition.md) | The NormalizePhysicalPosition method converts a physical buffer position to a time-based value. |
| [IMiniportWavePciStream::RevokeMappings](..\portcls\nf-portcls-iminiportwavepcistream-revokemappings.md) | The RevokeMappings method revokes mappings that were previously obtained through IPortWavePciStream |
| [IMiniportWavePciStream::Service](..\portcls\nf-portcls-iminiportwavepcistream-service.md) | The Service method notifies the miniport driver of a request for service. |
| [IMiniportWavePciStream::SetFormat](..\portcls\nf-portcls-iminiportwavepcistream-setformat.md) | The SetFormat method sets the KS data format of the wave stream. |
| [IMiniportWavePciStream::SetState](..\portcls\nf-portcls-iminiportwavepcistream-setstate.md) | The SetState method changes the state of the stream transport. |
| [IMiniportWaveRT::GetDeviceDescription](..\portcls\nf-portcls-iminiportwavert-getdevicedescription.md) | The GetDeviceDescription method returns a pointer to a DEVICE_DESCRIPTION structure describing the device. |
| [IMiniportWaveRT::Init](..\portcls\nf-portcls-iminiportwavert-init.md) | The Init method initializes the WaveRT miniport driver object. |
| [IMiniportWaveRT::NewStream](..\portcls\nf-portcls-iminiportwavert-newstream.md) | The NewStream method creates a new instance of a WaveRT stream object. |
| [IMiniportWaveRTInputStream::GetReadPacket](..\portcls\nf-portcls-iminiportwavertinputstream-getreadpacket.md) | Returns information about captured data. |
| [IMiniportWaveRTOutputStream::GetOutputStreamPresentationPosition](..\portcls\nf-portcls-iminiportwavertoutputstream-getoutputstreampresentationposition.md) | Returns stream presentation information. |
| [IMiniportWaveRTOutputStream::GetPacketCount](..\portcls\nf-portcls-iminiportwavertoutputstream-getpacketcount.md) | GetPacketCount returns the (1-based) count of packets completely transferred from the WaveRT buffer into hardware. |
| [IMiniportWaveRTOutputStream::SetWritePacket](..\portcls\nf-portcls-iminiportwavertoutputstream-setwritepacket.md) | SetWritePacket informs the driver that the OS has written valid data to the WaveRT buffer. |
| [IMiniportWaveRTStreamNotification::AllocateBufferWithNotification](..\portcls\nf-portcls-iminiportwavertstreamnotification-allocatebufferwithnotification.md) | The AllocateAudioBufferWithNotification method allocates a cyclic buffer for audio data when you want to implement DMA-driven event notification. If you do not want event notification, you must use IMiniportWaveRTStream |
| [IMiniportWaveRTStreamNotification::FreeBufferWithNotification](..\portcls\nf-portcls-iminiportwavertstreamnotification-freebufferwithnotification.md) | The FreeBufferWithNotification method is used to free an audio buffer previously allocated with a call to IMiniportWaveRTStreamNotification |
| [IMiniportWaveRTStreamNotification::RegisterNotificationEvent](..\portcls\nf-portcls-iminiportwavertstreamnotification-registernotificationevent.md) | The RegisterNotificationEvent method registers an event to be notified for DMA-driven event notification. |
| [IMiniportWaveRTStreamNotification::UnregisterNotificationEvent](..\portcls\nf-portcls-iminiportwavertstreamnotification-unregisternotificationevent.md) | The UnregisterNotificationEvent method unregisters an event from DMA driven event notification. |
| [IMusicTechnology::SetTechnology](..\portcls\nf-portcls-imusictechnology-settechnology.md) | The SetTechnology method changes the Technology member of each KSDATARANGE_MUSIC structure in the data ranges for the miniport driver's pins. |
| [IPinCount::PinCount](..\portcls\nf-portcls-ipincount-pincount.md) | The PinCount method queries the miniport driver for its pin count. |
| [IPinName::GetPinName](..\portcls\nf-portcls-ipinname-getpinname.md) | The GetPinName method retrieves the friendly name of an audio endpoint. |
| [IPortClsEtwHelper::MiniportWriteEtwEvent](..\portcls\nf-portcls-iportclsetwhelper-miniportwriteetwevent.md) | The MiniportWriteEtwEvent method is used by an audio miniport driver for providing the information about an Event Tracing for Windows (ETW) event. |
| [IPortClsNotifications::AllocNotificationBuffer](..\portcls\nf-portcls-iportclsnotifications-allocnotificationbuffer.md) | Allocates a buffer of the specified size, in the specified memory pool, for use in sending notifications, to allow for communications between audio modules and UWP apps. |
| [IPortClsNotifications::FreeNotificationBuffer](..\portcls\nf-portcls-iportclsnotifications-freenotificationbuffer.md) | Frees a previously allocated IPortClsNotifications buffer. The buffer is used in sending notifications, to allow for communications between audio modules and UWP apps. |
| [IPortClsNotifications::SendNotification](..\portcls\nf-portcls-iportclsnotifications-sendnotification.md) | Sends a notification to the listening UWP apps, to allow for communications between audio modules and UWP apps. |
| [IPortClsPnp::RegisterAdapterPnpManagement](..\portcls\nf-portcls-iportclspnp-registeradapterpnpmanagement.md) | The RegisterAdapterPowerManagement method registers the PnP management interface of the adapter with PortCls. |
| [IPortClsPnp::UnregisterAdapterPnpManagement](..\portcls\nf-portcls-iportclspnp-unregisteradapterpnpmanagement.md) | The UnRegisterAdapterPowerManagement method unregisters the PnP management interface of the adapter from PortCls. |
| [IPortClsPower::RegisterAdapterPowerManagement](..\portcls\nf-portcls-iportclspower-registeradapterpowermanagement.md) | The RegisterAdapterPowerManagement method registers the power management interface of the adapter with PortCls. |
| [IPortClsPower::SetIdlePowerManagement](..\portcls\nf-portcls-iportclspower-setidlepowermanagement.md) | The SetIdlePowerManagement method provides a way for the adapter driver to opt in or opt out of idle state detection. |
| [IPortClsPower::UnregisterAdapterPowerManagement](..\portcls\nf-portcls-iportclspower-unregisteradapterpowermanagement.md) | The UnregisterAdapterPowerManagement method unregisters the adapter's power management interface with PortCls. |
| [IPortClsRuntimePower::RegisterPowerControlCallback](..\portcls\nf-portcls-iportclsruntimepower-registerpowercontrolcallback.md) | The port class driver (PortCls) uses the RegisterPowerControlCallback method to register a power control callback. |
| [IPortClsRuntimePower::SendPowerControl](..\portcls\nf-portcls-iportclsruntimepower-sendpowercontrol.md) | The port class driver (PortCls) uses the SendPowerControl method to send power control codes to the audio adapter. |
| [IPortClsRuntimePower::UnregisterPowerControlCallback](..\portcls\nf-portcls-iportclsruntimepower-unregisterpowercontrolcallback.md) | The port class driver (PortCls) uses the UnregisterPowerControlCallback method to unregister a power control callback. |
| [IPortClsStreamResourceManager2::AddStreamResource2](..\portcls\nf-portcls-iportclsstreamresourcemanager2-addstreamresource2.md) | AddStreamResource2 adds a stream resource. Two type of stream resources are supported |
| [IPortClsVersion::GetVersion](..\portcls\nf-portcls-iportclsversion-getversion.md) | The GetVersion method returns the version of the Windows operating system that the driver is running on. |
| [IPortDMus::Notify](..\dmusicks\nf-dmusicks-iportdmus-notify.md) | The Notify method should be called from the miniport driver's interrupt service routine (ISR) when a hardware interrupt has occurred. |
| [IPortDMus::RegisterServiceGroup](..\dmusicks\nf-dmusicks-iportdmus-registerservicegroup.md) | The RegisterServiceGroup method registers a service group with the DMus port driver. |
| [IPortEvents::AddEventToEventList](..\portcls\nf-portcls-iportevents-addeventtoeventlist.md) | The AddEventToEventList method adds an event to the port driver's event list. |
| [IPortEvents::GenerateEventList](..\portcls\nf-portcls-iportevents-generateeventlist.md) | The GenerateEventList method notifies clients through the port driver's list of event entries that a particular event has occurred. |
| [IPortMidi::Notify](..\portcls\nf-portcls-iportmidi-notify.md) | The Notify method notifies the port driver that an interrupt indicating the progress of the DMA pointer has occurred. It should be called from the miniport driver's interrupt service routine (ISR). |
| [IPortMidi::RegisterServiceGroup](..\portcls\nf-portcls-iportmidi-registerservicegroup.md) | The RegisterServiceGroup method registers the service group to be used for the IPortMidi |
| [IPortWMIRegistration::RegisterWMIProvider](..\portcls\nf-portcls-iportwmiregistration-registerwmiprovider.md) | The RegisterWMIProvider method registers the Event Tracing for Windows (ETW) capability of the miniport driver with PortCls. |
| [IPortWMIRegistration::UnregisterWMIProvider](..\portcls\nf-portcls-iportwmiregistration-unregisterwmiprovider.md) | The UnregisterWMIProvider method unregisters the Event Tracing for Windows (ETW) interface that was previously registered with a call to the RegisterWMIProvider method. The unregistration disables the ETW registration with PortCls. |
| [IPortWaveCyclic::NewMasterDmaChannel](..\portcls\nf-portcls-iportwavecyclic-newmasterdmachannel.md) | The NewMasterDmaChannel method creates a new instance of a bus-master DMA channel. |
| [IPortWaveCyclic::NewSlaveDmaChannel](..\portcls\nf-portcls-iportwavecyclic-newslavedmachannel.md) | The NewSlaveDmaChannel method creates a new instance of a subordinate DMA channel. |
| [IPortWaveCyclic::Notify](..\portcls\nf-portcls-iportwavecyclic-notify.md) | The Notify method notifies the port driver that an interrupt indicating the progress of the DMA pointer has occurred. It should be called from the miniport driver's interrupt service routine (ISR). |
| [IPortWavePci::NewMasterDmaChannel](..\portcls\nf-portcls-iportwavepci-newmasterdmachannel.md) | The NewMasterDmaChannel method creates a new instance of a bus-master DMA channel. |
| [IPortWavePci::Notify](..\portcls\nf-portcls-iportwavepci-notify.md) | The Notify method notifies the port driver that an interrupt indicating the progress of the DMA pointer has occurred. |
| [IPortWavePciStream::GetMapping](..\portcls\nf-portcls-iportwavepcistream-getmapping.md) | The GetMapping method obtains a mapping from the port driver and associates a tag with the mapping. |
| [IPortWavePciStream::ReleaseMapping](..\portcls\nf-portcls-iportwavepcistream-releasemapping.md) | The ReleaseMapping method releases a mapping that was obtained by a previous call to IPortWavePciStream |
| [IPortWavePciStream::TerminatePacket](..\portcls\nf-portcls-iportwavepcistream-terminatepacket.md) | The TerminatePacket method terminates the packet currently being mapped. |
| [IPortWaveRTStream::AllocateContiguousPagesForMdl](..\portcls\nf-portcls-iportwavertstream-allocatecontiguouspagesformdl.md) | The AllocateContiguousPagesForMdl method allocates a list of contiguous, nonpaged, physical memory pages and returns a pointer to a memory descriptor list (MDL) that describes them. |
| [IPortWaveRTStream::AllocatePagesForMdl](..\portcls\nf-portcls-iportwavertstream-allocatepagesformdl.md) | The AllocatePagesForMdl method allocates a list of nonpaged physical memory pages and returns a pointer to a memory descriptor list (MDL) that describes them. |
| [IPortWaveRTStream::FreePagesFromMdl](..\portcls\nf-portcls-iportwavertstream-freepagesfrommdl.md) | The FreePagesFromMdl method frees a memory descriptor list (MDL). |
| [IPortWaveRTStream::GetPhysicalPageAddress](..\portcls\nf-portcls-iportwavertstream-getphysicalpageaddress.md) | The GetPhysicalPageAddress method returns the physical address for a page within a memory descriptor list (MDL). |
| [IPortWaveRTStream::GetPhysicalPagesCount](..\portcls\nf-portcls-iportwavertstream-getphysicalpagescount.md) | The GetPhysicalPagesCount method returns the count of the physical pages in a memory descriptor list (MDL). |
| [IPortWaveRTStream::MapAllocatedPages](..\portcls\nf-portcls-iportwavertstream-mapallocatedpages.md) | The MapAllocatedPages method maps a list of previously allocated physical pages into a contiguous block of virtual memory that is accessible from kernel-mode. |
| [IPortWaveRTStream::UnmapAllocatedPages](..\portcls\nf-portcls-iportwavertstream-unmapallocatedpages.md) | The UnmapAllocatedPages method releases a mapping. |
| [IPositionNotify::PositionNotify](..\dmusicks\nf-dmusicks-ipositionnotify-positionnotify.md) | Byte position notify for MXF graph. |
| [IPowerNotify::PowerChangeNotify](..\portcls\nf-portcls-ipowernotify-powerchangenotify.md) | The PowerChangeNotify method notifies the miniport driver of changes in the power state. |
| [IPreFetchOffset::SetPreFetchOffset](..\portcls\nf-portcls-iprefetchoffset-setprefetchoffset.md) | The SetPreFetchOffset method sets the prefetch offset, which is the number of bytes of data separating the write cursor from the play cursor in a DirectSound output stream. |
| [IRegistryKey::DeleteKey](..\portcls\nf-portcls-iregistrykey-deletekey.md) | The DeleteKey method deletes the registry key. |
| [IRegistryKey::EnumerateKey](..\portcls\nf-portcls-iregistrykey-enumeratekey.md) | The EnumerateKey method returns information about the subkeys of the open key. |
| [IRegistryKey::EnumerateValueKey](..\portcls\nf-portcls-iregistrykey-enumeratevaluekey.md) | The EnumerateValueKey method returns information about a registry entry that contains a value key. |
| [IRegistryKey::NewSubKey](..\portcls\nf-portcls-iregistrykey-newsubkey.md) | The NewSubKey method either creates a new registry subkey or opens an existing subkey under the key represented by the IRegistryKey object. |
| [IRegistryKey::QueryKey](..\portcls\nf-portcls-iregistrykey-querykey.md) | The QueryKey method retrieves information about a registry key, including the key name, key class, and the number of subkeys and their sizes. |
| [IRegistryKey::QueryRegistryValues](..\portcls\nf-portcls-iregistrykey-queryregistryvalues.md) | The QueryRegistryValues method allows the caller to query several values from the registry with a single call. |
| [IRegistryKey::QueryValueKey](..\portcls\nf-portcls-iregistrykey-queryvaluekey.md) | The QueryValueKey method retrieves information about a registry key's value entries, including their names, types, data sizes, and values. |
| [IRegistryKey::SetValueKey](..\portcls\nf-portcls-iregistrykey-setvaluekey.md) | The SetValueKey method replaces or creates a value entry under the open key. |
| [IResourceList::AddEntryFromParent](..\portcls\nf-portcls-iresourcelist-addentryfromparent.md) | The AddEntryFromParent method adds to a resource list an entry found in the resource list's parent list. |
| [IResourceList::AddEntry](..\portcls\nf-portcls-iresourcelist-addentry.md) | The AddEntry method adds an entry to a resource list. |
| [IResourceList::FindTranslatedEntry](..\portcls\nf-portcls-iresourcelist-findtranslatedentry.md) | The FindTranslatedEntry method returns a pointer to a translated entry of the specified type, or NULL if no such entry is found. |
| [IResourceList::FindUntranslatedEntry](..\portcls\nf-portcls-iresourcelist-finduntranslatedentry.md) | The FindUntranslatedEntry method returns a pointer to an untranslated entry of the specified type, or NULL if no such pointer is found. |
| [IResourceList::NumberOfEntriesOfType](..\portcls\nf-portcls-iresourcelist-numberofentriesoftype.md) | The NumberOfEntriesOfType method returns the number of resource items of a given type in the resource list. For each resource type, a macro is defined to call this method as previously described. |
| [IResourceList::NumberOfEntries](..\portcls\nf-portcls-iresourcelist-numberofentries.md) | The NumberOfEntries method returns the number of resource items in the resource list. |
| [IResourceList::TranslatedList](..\portcls\nf-portcls-iresourcelist-translatedlist.md) | The TranslatedList method returns the list of translated resources. |
| [IResourceList::UntranslatedList](..\portcls\nf-portcls-iresourcelist-untranslatedlist.md) | The UntranslatedList method returns the list of untranslated resources. |
| [IServiceGroup::AddMember](..\portcls\nf-portcls-iservicegroup-addmember.md) | The AddMember method adds a member to the service group. |
| [IServiceGroup::CancelDelayedService](..\portcls\nf-portcls-iservicegroup-canceldelayedservice.md) | The CancelDelayedService method cancels the previously requested delayed service. |
| [IServiceGroup::RemoveMember](..\portcls\nf-portcls-iservicegroup-removemember.md) | The RemoveMember method removes the specified member from the service group. |
| [IServiceGroup::RequestDelayedService](..\portcls\nf-portcls-iservicegroup-requestdelayedservice.md) | The RequestDelayedService method requests service after the specified delay. |
| [IServiceGroup::RequestService](..\portcls\nf-portcls-iservicegroup-requestservice.md) | TBD |
| [IServiceGroup::SupportDelayedService](..\portcls\nf-portcls-iservicegroup-supportdelayedservice.md) | The SupportDelayedService method indicates that the service group should prepare to support delayed service. |
| [IServiceSink::RequestService](..\portcls\nf-portcls-iservicesink-requestservice.md) | The RequestService method is called to forward a service request to an IServiceSink object. |
| [ISynthSinkDMus::RefTimeToSample](..\dmusicks\nf-dmusicks-isynthsinkdmus-reftimetosample.md) | The RefTimeToSample method converts a reference time into a sample time. |
| [ISynthSinkDMus::Render](..\dmusicks\nf-dmusicks-isynthsinkdmus-render.md) | The Render method renders wave data into a destination sink. |
| [ISynthSinkDMus::SampleToRefTime](..\dmusicks\nf-dmusicks-isynthsinkdmus-sampletoreftime.md) | The SampleToRefTime method converts a sample time to a reference time. |
| [ISynthSinkDMus::SyncToMaster](..\dmusicks\nf-dmusicks-isynthsinkdmus-synctomaster.md) | The SyncToMaster method allows synchronization to the master clock in order to avoid drift. |
| [IUnregisterPhysicalConnection::UnregisterPhysicalConnectionFromExternal](..\portcls\nf-portcls-iunregisterphysicalconnection-unregisterphysicalconnectionfromexternal.md) | The UnregisterPhysicalConnectionFromExternal method deletes the registration of a physical connection that was registered by a previous call to PcRegisterPhysicalConnectionFromExternal. |
| [IUnregisterPhysicalConnection::UnregisterPhysicalConnectionToExternal](..\portcls\nf-portcls-iunregisterphysicalconnection-unregisterphysicalconnectiontoexternal.md) | The UnregisterPhysicalConnectionToExternal method deletes the registration of a physical connection that was registered by a previous call to PcRegisterPhysicalConnectionToExternal. |
| [IUnregisterPhysicalConnection::UnregisterPhysicalConnection](..\portcls\nf-portcls-iunregisterphysicalconnection-unregisterphysicalconnection.md) | The UnregisterPhysicalConnection method deletes the registration of a physical connection that was registered by a previous call to PcRegisterPhysicalConnection. |
| [IUnregisterSubdevice::UnregisterSubdevice](..\portcls\nf-portcls-iunregistersubdevice-unregistersubdevice.md) | The UnregisterSubdevice method deletes the registration of a subdevice that was previously registered by a call to PcRegisterSubdevice. |
