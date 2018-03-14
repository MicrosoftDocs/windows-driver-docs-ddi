---
UID: NA:ksmedia
ms.assetid: 8877c4ae-aa0c-3131-b21b-33fa24797743
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Ksmedia.h header



This header is used by Streaming media devices, Audio, Display. For more information, see
- [Streaming media devices](../_stream/index.md)
- [Audio](../_audio/index.md)
- [Display](../_display/index.md)

Ksmedia.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [KSAC3_ALTERNATE_AUDIO structure](ns-ksmedia-ksac3_alternate_audio.md) | The KSAC3_ALTERNATE_AUDIO structure specifies whether the two mono channels in an AC-3-encoded stream should be interpreted as a stereo pair or as two independent program channels. |
| [KSAC3_BIT_STREAM_MODE structure](ns-ksmedia-ksac3_bit_stream_mode.md) | The KSAC3_BIT_STREAM_MODE structure specifies the bit-stream mode, which is the type of audio service that is encoded into an AC-3 stream. |
| [KSAC3_DIALOGUE_LEVEL structure](ns-ksmedia-ksac3_dialogue_level.md) | The KSAC3_DIALOGUE_LEVEL structure specifies the average volume level of spoken dialog within the audio program encoded in an AC-3 stream. |
| [KSAC3_DOWNMIX structure](ns-ksmedia-ksac3_downmix.md) | The KSAC3_DOWNMIX structure specifies whether the program channels in an AC-3-encoded stream need to be downmixed to accommodate the speaker configuration. |
| [KSAC3_ERROR_CONCEALMENT structure](ns-ksmedia-ksac3_error_concealment.md) | The KSAC3_ERROR_CONCEALMENT structure specifies how errors in an AC-3-encoded stream should be concealed during playback. |
| [KSAC3_ROOM_TYPE structure](ns-ksmedia-ksac3_room_type.md) | The KSAC3_ROOM_TYPE structure specifies the type of audio mixing room in which an AC-3-encoded stream was produced. |
| [KSAUDIO_CHANNEL_CONFIG structure](ns-ksmedia-ksaudio_channel_config.md) | The KSAUDIO_CHANNEL_CONFIG structure specifies the configuration of channels within the data format of an audio stream. |
| [KSAUDIO_COPY_PROTECTION structure](ns-ksmedia-ksaudio_copy_protection.md) | The KSAUDIO_COPY_PROTECTION structure specifies the copy-protection status of an audio stream. |
| [KSAUDIO_DYNAMIC_RANGE structure](ns-ksmedia-ksaudio_dynamic_range.md) | The KSAUDIO_DYNAMIC_RANGE structure specifies the dynamic range of an audio stream. This structure is used to get or set the data value for the KSPROPERTY_AUDIO_DYNAMIC_RANGE property. |
| [KSAUDIO_MICROPHONE_COORDINATES structure](ns-ksmedia-ksaudio_microphone_coordinates.md) | The KSAUDIO_MICROPHONE_COORDINATES structure specifies the type and the coordinates of a single microphone in the microphone array. |
| [KSAUDIO_MIC_ARRAY_GEOMETRY structure](ns-ksmedia-ksaudio_mic_array_geometry.md) | The KSAUDIO_MIC_ARRAY_GEOMETRY structure specifies the type and the geometry of the microphone array. |
| [KSAUDIO_MIXCAP_TABLE structure](ns-ksmedia-ksaudio_mixcap_table.md) | The KSAUDIO_MIXCAP_TABLE structure specifies the mixing capabilities of a supermixer node (KSNODETYPE_SUPERMIX). This structure is used to get or set the data value for the KSPROPERTY_AUDIO_MIX_LEVEL_CAPS property. |
| [KSAUDIO_MIXLEVEL structure](ns-ksmedia-ksaudio_mixlevel.md) | The KSAUDIO_MIXLEVEL structure specifies the mixing level of an input-output path in a supermixer node (KSNODETYPE_SUPERMIX). |
| [KSAUDIO_MIX_CAPS structure](ns-ksmedia-ksaudio_mix_caps.md) | The KSAUDIO_MIX_CAPS structure specifies the mixing capabilities of a particular data path from one input channel of a supermixer node (KSNODETYPE_SUPERMIX) to an output channel of the same node. |
| [KSAUDIO_POSITION structure](ns-ksmedia-ksaudio_position.md) | The KSAUDIO_POSITION structure specifies the current positions of the play and write cursors in the sound buffer for an audio stream. |
| [KSAUDIO_POSITIONEX structure](ns-ksmedia-ksaudio_positionex.md) | The KSAUDIO_POSITIONEX structure specifies the stream position and the associated timestamp information for a kernel streaming (KS)-based audio driver. |
| [KSAUDIO_PREFERRED_STATUS structure](ns-ksmedia-ksaudio_preferred_status.md) | The KSAUDIO_PREFERRED_STATUS structure specifies the status of a preferred device. |
| [KSAUDIO_PRESENTATION_POSITION structure](ns-ksmedia-ksaudio_presentation_position.md) | The KSAUDIO_PRESENTATION_POSITION structure specifies the current cursor position in audio data stream that is being rendered to the endpoint. |
| [KSCAMERA_PERFRAMESETTING_CAP_HEADER structure](ns-ksmedia-kscamera_perframesetting_cap_header.md) | This structure contains the header information for the per frame settings capabilities. |
| [KSCAMERA_PERFRAMESETTING_CAP_ITEM_HEADER structure](ns-ksmedia-kscamera_perframesetting_cap_item_header.md) | This structure contains the header information for a per-frame settings item. |
| [KSCAMERA_PERFRAMESETTING_CUSTOM_ITEM structure](ns-ksmedia-kscamera_perframesetting_custom_item.md) | This structure contains a custom item. |
| [KSCAMERA_PERFRAMESETTING_FRAME_HEADER structure](ns-ksmedia-kscamera_perframesetting_frame_header.md) | This structure contains the header information for a frame in a per-frame settings payload. |
| [KSCAMERA_PERFRAMESETTING_HEADER structure](ns-ksmedia-kscamera_perframesetting_header.md) | This structure contains header information for the per-frame settings payload. |
| [KSCAMERA_PERFRAMESETTING_ITEM_HEADER structure](ns-ksmedia-kscamera_perframesetting_item_header.md) | This structure contains the header information for a per-frame settings item. |
| [KSDATAFORMAT_DSOUND structure](ns-ksmedia-ksdataformat_dsound.md) | The KSDATAFORMAT_DSOUND structure provides detailed information about a DirectSound audio stream. |
| [KSDATAFORMAT_WAVEFORMATEX structure](ns-ksmedia-ksdataformat_waveformatex.md) | The KSDATAFORMAT_WAVEFORMATEX structure provides detailed information about the data format of an audio stream consisting of wave data. |
| [KSDATARANGE_AUDIO structure](ns-ksmedia-ksdatarange_audio.md) | The KSDATARANGE_AUDIO structure specifies a range of audio formats. |
| [KSDATARANGE_MUSIC structure](ns-ksmedia-ksdatarange_music.md) | The KSDATARANGE_MUSIC structure specifies a range of DirectMusic MIDI formats. |
| [KSDS3D_BUFFER_ALL structure](ns-ksmedia-ksds3d_buffer_all.md) | The KSDS3D_BUFFER_ALL structure specifies all the 3D characteristics of a DirectSound 3D buffer. |
| [KSDS3D_BUFFER_CONE_ANGLES structure](ns-ksmedia-ksds3d_buffer_cone_angles.md) | A KSDS3D_BUFFER_CONE_ANGLES structure specifies the inside and outside cone angles. |
| [KSDS3D_HRTF_FILTER_FORMAT_MSG structure](ns-ksmedia-ksds3d_hrtf_filter_format_msg.md) | The KSDS3D_HRTF_FILTER_FORMAT_MSG structure specifies the filter format to use for a head-relative transfer function (HRTF). |
| [KSDS3D_HRTF_INIT_MSG structure](ns-ksmedia-ksds3d_hrtf_init_msg.md) | The KSDS3D_HRTF_INIT_MSG structure specifies the parameter settings to use to initialize the head-relative transfer function (HRTF). |
| [KSDS3D_HRTF_PARAMS_MSG structure](ns-ksmedia-ksds3d_hrtf_params_msg.md) | The KSDS3D_HRTF_PARAMS_MSG structure specifies the parameter settings to apply to a head-relative transfer function (HRTF). |
| [KSDS3D_ITD_PARAMS structure](ns-ksmedia-ksds3d_itd_params.md) | The KSDS3D_ITD_PARAMS structure specifies the parameters applied by the interaural time delay (ITD) algorithm to the left or right channel in a 3D node (KSNODETYPE_3D_EFFECTS). |
| [KSDS3D_ITD_PARAMS_MSG structure](ns-ksmedia-ksds3d_itd_params_msg.md) | The KSDS3D_ITD_PARAMS_MSG structure specifies the parameters used by the interaural time delay (ITD) algorithm in a 3D node (KSNODETYPE_3D_EFFECTS). |
| [KSDS3D_LISTENER_ALL structure](ns-ksmedia-ksds3d_listener_all.md) | The KSDS3D_LISTENER_ALL structure specifies all the properties of the DirectSound 3D listener. This structure is used to get or set the data value for the KSPROPERTY_DIRECTSOUND3DLISTENER_ALL property. |
| [KSDS3D_LISTENER_ORIENTATION structure](ns-ksmedia-ksds3d_listener_orientation.md) | A KSD3D_LISTENER_ORIENTATION structure specifies the position vector of the 3D listener. This structure is used to get or set the data value for the KSPROPERTY_DIRECTSOUND3DLISTENER_ORIENTATION property. |
| [KSDSOUND_BUFFERDESC structure](ns-ksmedia-ksdsound_bufferdesc.md) | The KSDSOUND_BUFFERDESC structure describes a DirectSound buffer. |
| [KSEVENT_TUNER_INITIATE_SCAN_S structure](ns-ksmedia-ksevent_tuner_initiate_scan_s.md) | The KSEVENT_TUNER_INITIATE_SCAN_S structure is used in the KSEVENT_TUNER_INITIATE_SCAN event within the EVENTSETID_TUNER event set. |
| [KSMUSICFORMAT structure](ns-ksmedia-ksmusicformat.md) | The KSMUSICFORMAT structure is used to send and receive information about MIDI data that is input from and output to WDM audio devices. |
| [KSNODEPROPERTY structure](ns-ksmedia-ksnodeproperty.md) | The KSNODEPROPERTY structure specifies a node and a property of that node. |
| [KSNODEPROPERTY_AUDIO_CHANNEL structure](ns-ksmedia-ksnodeproperty_audio_channel.md) | The KSNODEPROPERTY_AUDIO_CHANNEL structure specifies a property of a channel in a node. |
| [KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S structure](ns-ksmedia-ksproperty_allocator_control_capture_caps_s.md) | The KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S structure specifies if interleaved capture is supported. |
| [KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S structure](ns-ksmedia-ksproperty_allocator_control_capture_interleave_s.md) | The KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S structure specifies if interleaved capture is possible. |
| [KSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE_S structure](ns-ksmedia-ksproperty_allocator_control_surface_size_s.md) | The KSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE_S structure specifies the width and height of an overlay surface. |
| [KSPROPERTY_CAMERACONTROL_FLASH_S structure](ns-ksmedia-ksproperty_cameracontrol_flash_s.md) | Describes flash control properties in the PROPSETID_VIDCAP_CAMERACONTROL_FLASH camera control property set. This structure specifies property values that are used by applications to configure the camera's flash. |
| [KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S structure](ns-ksmedia-ksproperty_cameracontrol_focal_length_s.md) | The KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S structure returns filter-specific data requested using the KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH property. |
| [KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S structure](ns-ksmedia-ksproperty_cameracontrol_image_pin_capability_s.md) | Describes image pin control properties in the PROPSETID_VIDCAP_CAMERACONTROL_IMAGE_PIN_CAPABILITY camera control property set. |
| [KSPROPERTY_CAMERACONTROL_NODE_FOCAL_LENGTH_S structure](ns-ksmedia-ksproperty_cameracontrol_node_focal_length_s.md) | The KSPROPERTY_CAMERACONTROL_NODE_FOCAL_LENGTH_S structure returns node-specific data requested using the KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH property. |
| [KSPROPERTY_CAMERACONTROL_NODE_S structure](ns-ksmedia-ksproperty_cameracontrol_node_s.md) | The KSPROPERTY_CAMERACONTROL_NODE_S structure describes node-based properties in the PROPSETID_VIDCAP_CAMERACONTROL property set. This structure specifies property values in requests to the USB Video Class driver. |
| [KSPROPERTY_CAMERACONTROL_NODE_S2 structure](ns-ksmedia-ksproperty_cameracontrol_node_s2.md) | The KSPROPERTY_CAMERACONTROL_NODE_S2 structure describes node-based properties in the PROPSETID_VIDCAP_CAMERACONTROL property set that use two values at the same time. This structure specifies property values in requests to the USB video class driver. |
| [KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S structure](ns-ksmedia-ksproperty_cameracontrol_region_of_interest_s.md) | Describes region of interest (ROI) control properties in the PROPSETID_VIDCAP_CAMERACONTROL_REGION_OF_INTEREST camera control property set. |
| [KSPROPERTY_CAMERACONTROL_S structure](ns-ksmedia-ksproperty_cameracontrol_s.md) | The KSPROPERTY_CAMERACONTROL_S structure describes filter-based properties in the PROPSETID_VIDCAP_CAMERACONTROL property set. |
| [KSPROPERTY_CAMERACONTROL_S2 structure](ns-ksmedia-ksproperty_cameracontrol_s2.md) | The KSPROPERTY_CAMERACONTROL_S2 structure describes filter-based properties in the PROPSETID_VIDCAP_CAMERACONTROL property set that use two values at the same time. |
| [KSPROPERTY_CAMERACONTROL_S_EX structure](ns-ksmedia-ksproperty_cameracontrol_s_ex.md) | Specifies a camera control operation, including setting the flash, the image pin control properties, the region of interest in the image, or video stabilization. |
| [KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S structure](ns-ksmedia-ksproperty_cameracontrol_videostabilization_mode_s.md) | Describes video stabilization control properties in the PROPSETID_VIDCAP_CAMERACONTROL_VIDEO_STABILIZATION camera control property set. This structure specifies property values that are used in requests to the camera driver. |
| [KSPROPERTY_CROSSBAR_CAPS_S structure](ns-ksmedia-ksproperty_crossbar_caps_s.md) | The KSPROPERTY_CROSSBAR_CAPS_S structure describes the crossbar capabilities for a device. |
| [KSPROPERTY_CROSSBAR_PININFO_S structure](ns-ksmedia-ksproperty_crossbar_pininfo_s.md) | The KSPROPERTY_CROSSBAR_PININFO_S structure describes the crossbar pin information for a device. |
| [KSPROPERTY_CROSSBAR_ROUTE_S structure](ns-ksmedia-ksproperty_crossbar_route_s.md) | The KSPROPERTY_CROSSBAR_ROUTE_S structure describes whether a particular routing is possible and specifies the current routing for a pin. |
| [KSPROPERTY_DROPPEDFRAMES_CURRENT_S structure](ns-ksmedia-ksproperty_droppedframes_current_s.md) | The KSPROPERTY_DROPPEDFRAMES_CURRENT_S structure describes the dropped frame information from the minidriver. |
| [KSPROPERTY_EXTDEVICE_S structure](ns-ksmedia-ksproperty_extdevice_s.md) | The KSPROPERTY_EXTDEVICE_S structure describes an external device and its capabilities. |
| [KSPROPERTY_EXTXPORT_NODE_S structure](ns-ksmedia-ksproperty_extxport_node_s.md) | The KSPROPERTY_EXTXPORT_NODE_S structure describes an external transport and its capabilities. |
| [KSPROPERTY_EXTXPORT_S structure](ns-ksmedia-ksproperty_extxport_s.md) | The KSPROPERTY_EXTXPORT_S structure describes an external transport and its capabilities. |
| [KSPROPERTY_SELECTOR_NODE_S structure](ns-ksmedia-ksproperty_selector_node_s.md) | The KSPROPERTY_SELECTOR_NODE_S structure describes node-based property settings in the PROPSETID_VIDCAP_SELECTOR property set. |
| [KSPROPERTY_SELECTOR_S structure](ns-ksmedia-ksproperty_selector_s.md) | The KSPROPERTY_SELECTOR_S structure describes filter-based property settings in the PROPSETID_VIDCAP_SELECTOR property set. |
| [KSPROPERTY_TIMECODE_NODE_S structure](ns-ksmedia-ksproperty_timecode_node_s.md) | The KSPROPERTY_TIMECODE_NODE_S structure describes a timecode. |
| [KSPROPERTY_TIMECODE_S structure](ns-ksmedia-ksproperty_timecode_s.md) | The KSPROPERTY_TIMECODE_S structure describes a timecode. |
| [KSPROPERTY_TUNER_CAPS_S structure](ns-ksmedia-ksproperty_tuner_caps_s.md) | The KSPROPERTY_TUNER_CAPS_S structure describes the hardware capabilities of TV and radio tuning devices. |
| [KSPROPERTY_TUNER_FREQUENCY_S structure](ns-ksmedia-ksproperty_tuner_frequency_s.md) | The KSPROPERTY_TUNER_FREQUENCY_S structure describes the frequency of a TV or radio tuner device. |
| [KSPROPERTY_TUNER_IF_MEDIUM_S structure](ns-ksmedia-ksproperty_tuner_if_medium_s.md) | The KSPROPERTY_TUNER_IF_MEDIUM_S structure returns the Medium GUID for the pin that is capable of supporting tuning to an intermediate frequency. |
| [KSPROPERTY_TUNER_INPUT_S structure](ns-ksmedia-ksproperty_tuner_input_s.md) | The KSPROPERTY_TUNER_INPUT_S structure describes the input connection index of a tuner device for devices that support multiple inputs. |
| [KSPROPERTY_TUNER_MODE_CAPS_S structure](ns-ksmedia-ksproperty_tuner_mode_caps_s.md) | The KS_PROPERTY_TUNER_MODE_CAPS_S structure describes the capabilities of TV and radio tuner devices. |
| [KSPROPERTY_TUNER_MODE_S structure](ns-ksmedia-ksproperty_tuner_mode_s.md) | The KSPROPERTY_TUNER_MODE_S structure describes the mode of a TV or radio tuner device. |
| [KSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S structure](ns-ksmedia-ksproperty_tuner_networktype_scan_caps_s.md) | The KSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S structure describes the scanning capabilities of a broadcast network type that a tuning device supports. |
| [KSPROPERTY_TUNER_SCAN_CAPS_S structure](ns-ksmedia-ksproperty_tuner_scan_caps_s.md) | The KSPROPERTY_TUNER_SCAN_CAPS_S structure describes the hardware scanning capabilities of a tuning device. |
| [KSPROPERTY_TUNER_SCAN_STATUS_S structure](ns-ksmedia-ksproperty_tuner_scan_status_s.md) | The KSPROPERTY_TUNER_SCAN_STATUS_S structure describes status for a scanning operation. |
| [KSPROPERTY_TUNER_STANDARD_MODE_S structure](ns-ksmedia-ksproperty_tuner_standard_mode_s.md) | The KSPROPERTY_TUNER_STANDARD_MODE_S structure describes whether the tuning device can identify the tuner standard from the signal itself. |
| [KSPROPERTY_TUNER_STANDARD_S structure](ns-ksmedia-ksproperty_tuner_standard_s.md) | The KSPROPERTY_TUNER_STANDARD_S structure describe the standard of a TV tuner device, such as PAL, NTSC or SECAM. |
| [KSPROPERTY_TUNER_STATUS_S structure](ns-ksmedia-ksproperty_tuner_status_s.md) | The KSPROPERTY_TUNER_STATUS_S structure describes the progress of a tuning operation for TV and radio tuner devices, including present tuning frequency. |
| [KSPROPERTY_TVAUDIO_CAPS_S structure](ns-ksmedia-ksproperty_tvaudio_caps_s.md) | The KSPROPERTY_TVAUDIO_CAPS_S structure describes the capability of a TV audio device, such as stereo versus mono audio support and language capabilities. |
| [KSPROPERTY_TVAUDIO_S structure](ns-ksmedia-ksproperty_tvaudio_s.md) | The KSPROPERTY_TVAUDIO_S structure describes the current TV audio mode, such as stereo or mono audio and language settings. |
| [KSPROPERTY_VIDEOCOMPRESSION_GETINFO_S structure](ns-ksmedia-ksproperty_videocompression_getinfo_s.md) | The KSPROPERTY_VIDEOCOMPRESSION_GETINFO_S structure describes information about the video compression capabilities supported by a device. |
| [KSPROPERTY_VIDEOCOMPRESSION_S structure](ns-ksmedia-ksproperty_videocompression_s.md) | The KSPROPERTY_VIDEOCOMPRESSION_S structure describes a single KSPROPERTY_VIDEOCOMPRESSION_Xxx property of a specified stream. |
| [KSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE_S structure](ns-ksmedia-ksproperty_videocontrol_actual_frame_rate_s.md) | The KSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE_S structure describes actual frame rate information in response to KSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE property requests. |
| [KSPROPERTY_VIDEOCONTROL_CAPS_S structure](ns-ksmedia-ksproperty_videocontrol_caps_s.md) | The KSPROPERTY_VIDEOCONTROL_CAPS_S structure describes the video-control capabilities of a minidriver, such as image flipping or event triggering abilities. |
| [KSPROPERTY_VIDEOCONTROL_FRAME_RATES_S structure](ns-ksmedia-ksproperty_videocontrol_frame_rates_s.md) | The KSPROPERTY_VIDEOCONTROL_FRAME_RATES structure describes available frame rates in 100-nanosecond units. |
| [KSPROPERTY_VIDEOCONTROL_MODE_S structure](ns-ksmedia-ksproperty_videocontrol_mode_s.md) | The KSPROPERTY_VIDEOCONTROL_MODE_S structure describes video-control modes for a stream, such as image flipping or event triggering abilities. |
| [KSPROPERTY_VIDEODECODER_CAPS_S structure](ns-ksmedia-ksproperty_videodecoder_caps_s.md) | The KSPROPERTY_VIDEODECODER_CAPS_S structure describes the hardware capabilities of the video decoder device. |
| [KSPROPERTY_VIDEODECODER_S structure](ns-ksmedia-ksproperty_videodecoder_s.md) | The KSPROPERTY_VIDEODECODER_S structure describes property settings in the PROPSETID_VIDCAP_VIDEODECODER property set. |
| [KSPROPERTY_VIDEODECODER_STATUS_S structure](ns-ksmedia-ksproperty_videodecoder_status_s.md) | The KSPROPERTY_VIDEODECODER_STATUS_S structure describes the present status of a video decoding device, such as number of lines in the incoming analog signal and whether the signal is locked in. |
| [KSPROPERTY_VIDEOPROCAMP_NODE_S structure](ns-ksmedia-ksproperty_videoprocamp_node_s.md) | The KSPROPERTY_VIDEOPROCAMP_NODE_S structure describes node-based property settings in the PROPSETID_VIDCAP_VIDEOPROCAMP property set. |
| [KSPROPERTY_VIDEOPROCAMP_NODE_S2 structure](ns-ksmedia-ksproperty_videoprocamp_node_s2.md) | The KSPROPERTY_VIDEOPROCAMP_NODE_S2 structure describes node-based property settings in the PROPSETID_VIDCAP_VIDEOPROCAMP property set that use two values at the same time. |
| [KSPROPERTY_VIDEOPROCAMP_S structure](ns-ksmedia-ksproperty_videoprocamp_s.md) | The KSPROPERTY_VIDEOPROCAMP_S structure describes filter-based property settings in the PROPSETID_VIDCAP_VIDEOPROCAMP property set. |
| [KSRTAUDIO_BUFFER structure](ns-ksmedia-ksrtaudio_buffer.md) | The KSRTAUDIO_BUFFER structure specifies the buffer address, size, and a call memory barrier flag for a cyclic audio data buffer. |
| [KSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION structure](ns-ksmedia-ksrtaudio_buffer_property_with_notification.md) | The KSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION structure appends a buffer base address, a requested buffer size, and a notification count to a KSPROPERTY structure. |
| [KSRTAUDIO_GETREADPACKET_INFO structure](ns-ksmedia-ksrtaudio_getreadpacket_info.md) | The KSRTAUDIO_GETREADPACKET_INFO structure describes information for an audio packet. |
| [KSRTAUDIO_HWLATENCY structure](ns-ksmedia-ksrtaudio_hwlatency.md) | The KSRTAUDIO_HWLATENCY structure describes the latency that the audio hardware adds to a wave stream during playback or recording. |
| [KSRTAUDIO_HWREGISTER structure](ns-ksmedia-ksrtaudio_hwregister.md) | The KSRTAUDIO_HWREGISTER structure specifies the address and additional information about a hardware register requested by the client. |
| [KSRTAUDIO_HWREGISTER_PROPERTY structure](ns-ksmedia-ksrtaudio_hwregister_property.md) | The KSRTAUDIO_HWREGISTRY_PROPERTY structure appends a register base address to a KSPROPERTY structure. |
| [KSRTAUDIO_NOTIFICATION_EVENT_PROPERTY structure](ns-ksmedia-ksrtaudio_notification_event_property.md) | The KSRTAUDIO_NOTIFICATION_EVENT_PROPERTY structure appends an event handle to a KSPROPERTY structure |
| [KSRTAUDIO_SETWRITEPACKET_INFO structure](ns-ksmedia-ksrtaudio_setwritepacket_info.md) | The KSRTAUDIO_SETWRITEPACKET_INFO structure describes information associated with an audio packet. |
| [KSVPMAXPIXELRATE structure](ns-ksmedia-ksvpmaxpixelrate.md) | The KSVPMAXPIXELRATE structure is used to describe the maximum pixel rate of a video port. |
| [KSVPSURFACEPARAMS structure](ns-ksmedia-ksvpsurfaceparams.md) | The KSVPSURFACEPARAMS structure is used to describe the surface parameters of a video port surface. |
| [KSWAVE_BUFFER structure](ns-ksmedia-kswave_buffer.md) | The KSWAVE_BUFFER structure is used to describe a sample buffer. |
| [KSWAVE_COMPATCAPS structure](ns-ksmedia-kswave_compatcaps.md) | The KSWAVE_COMPATCAPS structure is used to describe the compatible capabilities of a device. |
| [KSWAVE_INPUT_CAPABILITIES structure](ns-ksmedia-kswave_input_capabilities.md) | The KSWAVE_INPUT_CAPABILITIES structure is used to describe the input capabilities of a device. |
| [KSWAVE_OUTPUT_CAPABILITIES structure](ns-ksmedia-kswave_output_capabilities.md) | The KSWAVE_OUTPUT_CAPABILITIES structure is used to describe the output capabilities of a device. |
| [KSWAVE_VOLUME structure](ns-ksmedia-kswave_volume.md) | The KSWAVE_VOLUME structure is used to describe sample volume. |
| [KS_AM_ExactRateChange structure](ns-ksmedia-ks_am_exactratechange.md) | The KS_AM_ExactRateChange structure is not yet implemented. |
| [KS_AM_SimpleRateChange structure](ns-ksmedia-ks_am_simpleratechange.md) | The KS_AM_SimpleRateChange structure is used to describe a simple rate change (fast-forward or rewind) for an MPEG2 stream. |
| [LOOPEDSTREAMING_POSITION_EVENT_DATA structure](ns-ksmedia-loopedstreaming_position_event_data.md) | The LOOPEDSTREAMING_POSITION_EVENT_DATA structure describes a position event in a looped buffer. |
| [MEDIUM_INFO structure](ns-ksmedia-medium_info.md) | The MEDIUM_INFO structure describes the media loaded into an external device. |
| [SOUNDDETECTOR_PATTERNHEADER structure](ns-ksmedia-sounddetector_patternheader.md) | The SOUNDDETECTOR_PATTERNHEADER structure specifies the pattern header for the sound detector in the KSPROPERTY_SOUNDDETECTOR_PATTERNS property. |
| [SYSAUDIO_ATTACH_VIRTUAL_SOURCE structure](ns-ksmedia-sysaudio_attach_virtual_source.md) | The SYSAUDIO_ATTACH_VIRTUAL_SOURCE structure is used to attach a mixer-line virtual source (for example, a volume or mute control) to a mixer pin on the virtual audio device. |
| [SYSAUDIO_CREATE_VIRTUAL_SOURCE structure](ns-ksmedia-sysaudio_create_virtual_source.md) | The SYSAUDIO_CREATE_VIRTUAL_SOURCE structure is used to create a mixer-line virtual source such as a volume control or mute. |
| [SYSAUDIO_INSTANCE_INFO structure](ns-ksmedia-sysaudio_instance_info.md) | The SYSAUDIO_INSTANCE_INFO structure specifies which virtual audio device to open and includes flags for configuring that device. |
| [SYSAUDIO_SELECT_GRAPH structure](ns-ksmedia-sysaudio_select_graph.md) | The SYSAUDIO_SELECT_GRAPH structure is used to specify a graph that includes an optional node such as an AEC control. |
| [TRANSPORT_STATE structure](ns-ksmedia-transport_state.md) | The TRANSPORT_STATE structure |
| [TUNER_ANALOG_CAPS_S structure](ns-ksmedia-tuner_analog_caps_s.md) | The TUNER_ANALOG_CAPS_S structure describes the hardware scanning capabilities of a tuning device that supports an analog broadcast network. |
| [VRAM_SURFACE_INFO structure](ns-ksmedia-vram_surface_info.md) | The VRAM_SURFACE_INFO structure describes a region of system or display memory into which an AVStream minidriver captures audio or video data. |
| [VRAM_SURFACE_INFO_PROPERTY_S structure](ns-ksmedia-vram_surface_info_property_s.md) | The VRAM_SURFACE_INFO_PROPERTY_S structure describes property items in the KSPROPSETID_VramCapture property set. |
| [WAVEFORMATEXTENSIBLE structure](ns-ksmedia-waveformatextensible.md) | The WAVEFORMATEXTENSIBLE structure specifies the format of an audio wave stream. |
| [_DDPIXELFORMAT structure](ns-ksmedia-_ddpixelformat.md) | The DDPIXELFORMAT structure describes the pixel format of a DirectDrawSurface object. |
| [_DDVIDEOPORTCONNECT structure](ns-ksmedia-_ddvideoportconnect.md) | The DDVIDEOPORTCONNECT structure describes a hardware video port connection. |
| [_DS3DVECTOR structure](ns-ksmedia-_ds3dvector.md) | The DS3DVECTOR structure contains three-dimensional position coordinates, position vector components, or velocity vector components. |
| [_KSAUDIOMODULE_DESCRIPTOR structure](ns-ksmedia-_ksaudiomodule_descriptor.md) | The KSAUDIOMODULE_DESCRIPTOR structure describes the static, external properties of audio modules. |
| [_KSAUDIOMODULE_NOTIFICATION structure](ns-ksmedia-_ksaudiomodule_notification.md) | The KSAUDIOMODULE_NOTIFICATION structure describes the properties associated with audio modules change notification. |
| [_KSAUDIOMODULE_PROPERTY structure](ns-ksmedia-_ksaudiomodule_property.md) | The KSAUDIOMODULE_DESCRIPTOR structure describes the static, external properties of the audio modules. |
| [_KSAUDIO_PACKETSIZE_CONSTRAINTS structure](ns-ksmedia-_ksaudio_packetsize_constraints.md) | The KSAUDIO_PACKETSIZE_CONSTRAINTS structure describes the physical hardware constraints. |
| [_KSAUDIO_PACKETSIZE_CONSTRAINTS2 structure](ns-ksmedia-_ksaudio_packetsize_constraints2.md) | The KSAUDIO_PACKETSIZE_CONSTRAINTS2 structure describes the physical hardware constraints. |
| [_KSAUDIO_PACKETSIZE_SIGNALPROCESSINGMODE_CONSTRAINT structure](ns-ksmedia-_ksaudio_packetsize_signalprocessingmode_constraint.md) | The KSAUDIO_PACKETSIZE_PROCESSINGMODE_CONSTRAINT structure describes the constraints specific to any signal processing mode. |
| [_KSCAMERA_EXTENDEDPROP_PROFILE structure](ns-ksmedia-_kscamera_extendedprop_profile.md) | The payload of the KSPROPERTY_CAMERACONTROL_EXTENDED_PROFILE control contains KSCAMERA_EXTENDEDPROP_HEADER + KSCAMERA_EXTENDEDPROP_PROFILE. |
| [_KSCAMERA_PROFILE_CONCURRENCYINFO structure](ns-ksmedia-_kscamera_profile_concurrencyinfo.md) | An array of KSCAMERA_PROFILE_CONCURRENCYINFO structures form the Camera.Concurrency parameter of the KSDEVICE_PROFILE_INFO structure (whose array size is specified by Camera.CountOfConcurrency parameter) indicating which profiles the profile identified in the KSCAMERA_PROFILE_INFO structure may run simultaneously on different cameras. |
| [_KSCAMERA_PROFILE_INFO structure](ns-ksmedia-_kscamera_profile_info.md) | The KSCAMERA_PROFILE_INFO structure is used to uniquely identify a given profile. |
| [_KSCAMERA_PROFILE_MEDIAINFO structure](ns-ksmedia-_kscamera_profile_mediainfo.md) | This structure contains the relevant media type information presented for each camera profile. |
| [_KSCAMERA_PROFILE_PININFO structure](ns-ksmedia-_kscamera_profile_pininfo.md) | This structure specifies the available list of media types for each of the camera driver pins. |
| [_KSDEVICE_PROFILE_INFO structure](ns-ksmedia-_ksdevice_profile_info.md) | The KSDEVICE_PROFILE_INFO is a generic structure designed to handle profile information for various device types. |
| [_KSMPEGVID_RECT structure](ns-ksmedia-_ksmpegvid_rect.md) | KSMPEGVID_RECT structure |
| [_KSPROPERTY_SPHLI structure](ns-ksmedia-_ksproperty_sphli.md) | The KSPROPERTY_SPHLI structure is used to describe a rectangle of subpicture or screen whose color or contrast is to be changed. |
| [_KSPROPERTY_SPPAL structure](ns-ksmedia-_ksproperty_sppal.md) | The KSPROPERTY_SPPAL structure is used to describe the palette of a subpicture display. |
| [_KS_COLCON structure](ns-ksmedia-_ks_colcon.md) | The KS_COLCON structure is used to describe color and contrast settings. |
| [_KS_COPY_MACROVISION structure](ns-ksmedia-_ks_copy_macrovision.md) | The KS_COPY_MACROVISION structure specifies the Macrovision level of the data stream. |
| [_KS_DVDCOPY_BUSKEY structure](ns-ksmedia-_ks_dvdcopy_buskey.md) | The KS_DVDCOPY_BUSKEY structure is used to describe the bus key information for the DVD copyright protection authentication process. |
| [_KS_DVDCOPY_CHLGKEY structure](ns-ksmedia-_ks_dvdcopy_chlgkey.md) | The KS_DVDCOPY_CHLGKEY structure is used to describe the challenge key information for the DVD copyright protection authentication process. |
| [_KS_DVDCOPY_DISCKEY structure](ns-ksmedia-_ks_dvdcopy_disckey.md) | The KS_DVDCOPY_DISCKEY structure is used to describe the disc key information for the DVD copyright protection authentication process. |
| [_KS_DVDCOPY_REGION structure](ns-ksmedia-_ks_dvdcopy_region.md) | The KS_DVDCOPY_REGION structure is used to describe the copy control region according to language restrictions. |
| [_KS_DVDCOPY_SET_COPY_STATE structure](ns-ksmedia-_ks_dvdcopy_set_copy_state.md) | The KS_DVDCOPY_SET_COPY_STATE structure is used to specify the copyright protection state of the DVD decoder stream. |
| [_KS_DVDCOPY_TITLEKEY structure](ns-ksmedia-_ks_dvdcopy_titlekey.md) | The KS_DVDCOPY_TITLEKEY structure is used to describe the title key information for the DVD copyright protection authentication process. |
| [_KS_DVD_YCrCb structure](ns-ksmedia-_ks_dvd_ycrcb.md) | The KS_DVD_YCrCb structure is used to describe a color in the YCrCb colorspace. |
| [_KS_DVD_YUV structure](ns-ksmedia-_ks_dvd_yuv.md) | The KS_DVD_YUV structure is used to describe a color in the YUV colorspace. |
| [_KS_VIDEO_STREAM_CONFIG_CAPS structure](ns-ksmedia-_ks_video_stream_config_caps.md) | The KS_VIDEO_STREAM_CONFIG_CAPS structure describes the configuration and capabilities of a video stream, including analog video standard (for example, NTSC, PAL or SECAM), scaling, and cropping capabilities; minimum and maximum frame rates; and minimum and maximum data rates. |
| [_tagKSAUDIOENGINE_BUFFER_SIZE_RANGE structure](ns-ksmedia-_tagksaudioengine_buffer_size_range.md) | The KSAUDIOENGINE_BUFFER_SIZE_RANGE structure specifies the minimum and maximum buffer size that the hardware audio engine can support at the instance when it is called. |
| [_tagKSAUDIOENGINE_DESCRIPTOR structure](ns-ksmedia-_tagksaudioengine_descriptor.md) | The KSAUDIOENGINE_DESCRIPTOR structure describes the static, external properties of the audio engine. |
| [_tagKSAUDIOENGINE_VOLUMELEVEL structure](ns-ksmedia-_tagksaudioengine_volumelevel.md) | The KSAUDIOENGINE_VOLUMELEVEL structure specifies the target volume level, ramp type, and duration within which the volume level should change, for a given volume level request via the KSPROPERTY_AUDIOENGINE_VOLUMELEVEL property. |
| [_tagKSJACK_SINK_INFORMATION structure](ns-ksmedia-_tagksjack_sink_information.md) | The KSJACK_SINK_INFORMATION structure specifies information about a display-related digital audio device, such as an HDMI device or a display port. |
| [_tagKSTELEPHONY_CALLCONTROL structure](ns-ksmedia-_tagkstelephony_callcontrol.md) | The KSTELEPHONY_CALLCONTROL structure specifies the phone call type and control operation to use for the KSPROPERTY_TELEPHONY_CALLCONTROL property. |
| [_tagKSTELEPHONY_CALLINFO structure](ns-ksmedia-_tagkstelephony_callinfo.md) | The KSTELEPHONY_CALLINFO structure specifies the type and state of a phone call for the KSPROPERTY_TELEPHONY_CALLINFO property. |
| [_tagKSTELEPHONY_PROVIDERCHANGE structure](ns-ksmedia-_tagkstelephony_providerchange.md) | The KSTELEPHONY_PROVIDERCHANGE structure specifies the phone call type and provider change operation to use for the KSPROPERTY_TELEPHONY_PROVIDERCHANGE property. |
| [_tagKSTOPOLOGY_ENDPOINTID structure](ns-ksmedia-_tagkstopology_endpointid.md) | The KSTOPOLOGY_ENDPOINTID structure specifies the name and the pin ID of a topology endpoint. |
| [_tagKSTOPOLOGY_ENDPOINTIDPAIR structure](ns-ksmedia-_tagkstopology_endpointidpair.md) | The KSTOPOLOGY_ENDPOINTIDPAIR structure specifies the render and capture endpoint IDs to use for the KSPROPERTY_TELEPHONY_ENDPOINTIDPAIR property. |
| [_timecode structure](ns-ksmedia-_timecode.md) | The TIMECODE union describes a timecode from an external device. This structure is no longer used. |
| [tagDEVCAPS structure](ns-ksmedia-tagdevcaps.md) | The DEVCAPS structure describes the capabilities of an external device. |
| [tagKSATTRIBUTE_AUDIOSIGNALPROCESSING_MODE structure](ns-ksmedia-tagksattribute_audiosignalprocessing_mode.md) | The KSATTRIBUTE_AUDIOSIGNALPROCESSING_MODE structure specifies an audio signal processing mode. |
| [tagKSCAMERA_EXTENDEDPROP_CAMERAOFFSET structure](ns-ksmedia-tagkscamera_extendedprop_cameraoffset.md) | The KSCAMERA_EXTENDEDPROP_CAMERAOFFSET structure contains the parameters for the Camera Angle Offset Control property. |
| [tagKSCAMERA_EXTENDEDPROP_EVCOMPENSATION structure](ns-ksmedia-tagkscamera_extendedprop_evcompensation.md) | The EV Compensation Control provides for exposure control that is adjusted by increments of EV compensation steps. |
| [tagKSCAMERA_EXTENDEDPROP_FIELDOFVIEW structure](ns-ksmedia-tagkscamera_extendedprop_fieldofview.md) | The Field of View Control property describes the current Field of View (FOV) of the camera along with the pitch angle of the camera position. |
| [tagKSCAMERA_EXTENDEDPROP_HEADER structure](ns-ksmedia-tagkscamera_extendedprop_header.md) | The KSCAMERA_EXTENDEDPROP_HEADER structure is the payload header for an extend control property. |
| [tagKSCAMERA_EXTENDEDPROP_METADATAINFO structure](ns-ksmedia-tagkscamera_extendedprop_metadatainfo.md) | This structure represents the metadata information for the extended property control. |
| [tagKSCAMERA_EXTENDEDPROP_PHOTOMODE structure](ns-ksmedia-tagkscamera_extendedprop_photomode.md) | The KSCAMERA_EXTENDEDPROP_PHOTOMODE structure contains the property data for the history frame counts in photo mode. |
| [tagKSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPS structure](ns-ksmedia-tagkscamera_extendedprop_roi_configcaps.md) | This structure contains the capabilities for an ROI control. |
| [tagKSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPSHEADER structure](ns-ksmedia-tagkscamera_extendedprop_roi_configcapsheader.md) | This structure contains the header information for ROI capabilities. |
| [tagKSCAMERA_EXTENDEDPROP_ROI_EXPOSURE structure](ns-ksmedia-tagkscamera_extendedprop_roi_exposure.md) | This structure contains the ROI info structure for exposure. |
| [tagKSCAMERA_EXTENDEDPROP_ROI_FOCUS structure](ns-ksmedia-tagkscamera_extendedprop_roi_focus.md) | This structure contains the ROI info structure for focus. |
| [tagKSCAMERA_EXTENDEDPROP_ROI_INFO structure](ns-ksmedia-tagkscamera_extendedprop_roi_info.md) | This structure contains information about an ROI. |
| [tagKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROL structure](ns-ksmedia-tagkscamera_extendedprop_roi_ispcontrol.md) | This structure contains information for an ROI ISP control. |
| [tagKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER structure](ns-ksmedia-tagkscamera_extendedprop_roi_ispcontrolheader.md) | This structure contains the header information for ROI ISP controls. |
| [tagKSCAMERA_EXTENDEDPROP_ROI_WHITEBALANCE structure](ns-ksmedia-tagkscamera_extendedprop_roi_whitebalance.md) | This structure contains the ROI info structure for white balance. |
| [tagKSCAMERA_EXTENDEDPROP_VALUE structure](ns-ksmedia-tagkscamera_extendedprop_value.md) | The KSCAMERA_EXTENDEDPROP_VALUE structure is a data type union used to express an extended property value. |
| [tagKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING structure](ns-ksmedia-tagkscamera_extendedprop_videoprocsetting.md) | The KSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING is a property payload structure for video processing settings related to white balance, exposure mode, and focus mode. |
| [tagKSCAMERA_MAXVIDEOFPS_FORPHOTORES structure](ns-ksmedia-tagkscamera_maxvideofps_forphotores.md) | The KSCAMERA_MAXVIDEOFPS_FORPHOTORES structure contains the property data for maximum frame rate at a particular resolution for a camera supporting preview and capture. |
| [tagKSCAMERA_METADATA_ITEMHEADER structure](ns-ksmedia-tagkscamera_metadata_itemheader.md) | This structure contains the metadata header information that is filled by the camera driver. |
| [tagKSCAMERA_METADATA_PHOTOCONFIRMATION structure](ns-ksmedia-tagkscamera_metadata_photoconfirmation.md) | This structure contains the photo confirmation metadata information that is filled by the camera driver. |
| [tagKS_AMVPDATAINFO structure](ns-ksmedia-tagks_amvpdatainfo.md) | The KS_AMVPDATAINFO structure is used to describe the properties of a video port. |
| [tagKS_AMVPDIMINFO structure](ns-ksmedia-tagks_amvpdiminfo.md) | The KS_AMVPDIMINFO structure is used to describe the dimensions of a video port. |
| [tagKS_AMVPSIZE structure](ns-ksmedia-tagks_amvpsize.md) | The KS_AMVPSIZE structure is used to describe the dimension of a video port (width by height). |
| [tagKS_AnalogVideoInfo structure](ns-ksmedia-tagks_analogvideoinfo.md) | The KS_ANALOGVIDEOINFO structure describes an analog video stream. |
| [tagKS_BITMAPINFOHEADER structure](ns-ksmedia-tagks_bitmapinfoheader.md) | The KS_BITMAPINFOHEADER structure describes details about the video stream, such as image dimensions and pixel depth. |
| [tagKS_DATAFORMAT_H264VIDEOINFO structure](ns-ksmedia-tagks_dataformat_h264videoinfo.md) | The KS_DATAFORMAT_H264VIDEOINFO structure describes the data formats range available for a stream. |
| [tagKS_DATAFORMAT_IMAGEINFO structure](ns-ksmedia-tagks_dataformat_imageinfo.md) | Specifies an image data format that is used for an independent image pin (or stream). |
| [tagKS_DATAFORMAT_VBIINFOHEADER structure](ns-ksmedia-tagks_dataformat_vbiinfoheader.md) | The KS_DATAFORMAT_VBIINFOHEADER structure describes a vertical blanking interval (VBI) stream. |
| [tagKS_DATAFORMAT_VIDEOINFOHEADER structure](ns-ksmedia-tagks_dataformat_videoinfoheader.md) | The KS_DATAFORMAT_VIDEOINFOHEADER structure describes a video stream that does not include bob or weave settings. |
| [tagKS_DATAFORMAT_VIDEOINFOHEADER2 structure](ns-ksmedia-tagks_dataformat_videoinfoheader2.md) | The KS_DATAFORMAT_VIDEOINFOHEADER2 structure describes a video stream that includes settings for bob or weave. |
| [tagKS_DATAFORMAT_VIDEOINFO_PALETTE structure](ns-ksmedia-tagks_dataformat_videoinfo_palette.md) | The KS_DATAFORMAT_VIDEOINFO_PALETTE structure describes color palette information. |
| [tagKS_DATARANGE_ANALOGVIDEO structure](ns-ksmedia-tagks_datarange_analogvideo.md) | The KS_DATARANGE_ANALOGVIDEO structure describes an analog video stream. |
| [tagKS_DATARANGE_H264_VIDEO structure](ns-ksmedia-tagks_datarange_h264_video.md) | The KS_DATARANGE_H264_VIDEO structure describes the range of MPEG-2 video formats available for a stream. |
| [tagKS_DATARANGE_IMAGE structure](ns-ksmedia-tagks_datarange_image.md) | Specifies an image data range that is used in the KSPIN_DESCRIPTOR structure that describes a pin (or stream). |
| [tagKS_DATARANGE_MPEG1_VIDEO structure](ns-ksmedia-tagks_datarange_mpeg1_video.md) | The KS_DATARANGE_MPEG1_VIDEO structure describes the range of MPEG-1 video formats available for a stream. |
| [tagKS_DATARANGE_MPEG2_VIDEO structure](ns-ksmedia-tagks_datarange_mpeg2_video.md) | The KS_DATARANGE_MPEG2_VIDEO structure describes the range of MPEG-2 video formats available for a stream. |
| [tagKS_DATARANGE_VIDEO structure](ns-ksmedia-tagks_datarange_video.md) | The KS_DATARANGE_VIDEO structure describes a range of video streams without bob or weave settings. |
| [tagKS_DATARANGE_VIDEO2 structure](ns-ksmedia-tagks_datarange_video2.md) | The KS_DATARANGE_VIDEO2 structure describes a video stream including bob or weave settings. |
| [tagKS_DATARANGE_VIDEO_PALETTE structure](ns-ksmedia-tagks_datarange_video_palette.md) | The KS_DATARANGE_VIDEO_PALETTE structure describes a stream and its color capabilities. |
| [tagKS_DATARANGE_VIDEO_VBI structure](ns-ksmedia-tagks_datarange_video_vbi.md) | The KS_DATARANGE_VIDEO_VBI structure describes a range of data formats containing vertical blanking interval (VBI) data. |
| [tagKS_FRAME_INFO structure](ns-ksmedia-tagks_frame_info.md) | The KS_FRAME_INFO structure extends the KSSTREAM_HEADER structure for video streams. |
| [tagKS_H264VIDEOINFO structure](ns-ksmedia-tagks_h264videoinfo.md) | The KS_H264VIDEOINFO describes the device capabilities that apply to the current media type. |
| [tagKS_MPEAUDIOINFO structure](ns-ksmedia-tagks_mpeaudioinfo.md) | The KS_MPEGAUDIOINFO structure describes an MPEG audio stream. |
| [tagKS_MPEG1VIDEOINFO structure](ns-ksmedia-tagks_mpeg1videoinfo.md) | The KS_MPEG1VIDEOINFO structure describes an MPEG-1 video stream. |
| [tagKS_MPEGVIDEOINFO2 structure](ns-ksmedia-tagks_mpegvideoinfo2.md) | The KS_MPEGVIDEOINFO2 structure describes an MPEG-2 video stream, including bob or weave settings. |
| [tagKS_RGBQUAD structure](ns-ksmedia-tagks_rgbquad.md) | The KS_RGBQUAD structure describes a color consisting of relative intensities of red, green, and blue, ranging from 0 to 255 (0x0 to 0xff). |
| [tagKS_TVTUNER_CHANGE_INFO structure](ns-ksmedia-tagks_tvtuner_change_info.md) | The KS_TVTUNER_CHANGE_INFO structure provides vertical blanking interval (VBI) codecs with information about the currently tuned channel. |
| [tagKS_VBIINFOHEADER structure](ns-ksmedia-tagks_vbiinfoheader.md) | The KS_VBIINFOHEADER structure describes raw vertical blanking interval (VBI) streams. |
| [tagKS_VBI_FRAME_INFO structure](ns-ksmedia-tagks_vbi_frame_info.md) | The KS_VBI_FRAME_INFO structure extends the KSSTREAM_HEADER structure for vertical blanking interval (VBI) streams. |
| [tagKS_VIDEOINFO structure](ns-ksmedia-tagks_videoinfo.md) | The KS_VIDEOINFO structure describes the bitmap and color information for a video stream. |
| [tagKS_VIDEOINFOHEADER structure](ns-ksmedia-tagks_videoinfoheader.md) | The KS_VIDEOINFOHEADER structure describes the bitmap and color information for a video stream. |
| [tagKS_VIDEOINFOHEADER2 structure](ns-ksmedia-tagks_videoinfoheader2.md) | The KS_VIDEOINFOHEADER2 structure describes the details of a video stream, including bob or weave settings, copy protection, and pixel aspect ratio. |
| [tagTIMECODE_SAMPLE structure](ns-ksmedia-tagtimecode_sample.md) | The TIMECODE_SAMPLE structure describes a complete timecode. |
| [tagTRANSPORTAUDIOPARMS structure](ns-ksmedia-tagtransportaudioparms.md) | The TRANSPORTAUDIOPARMS structure is defined but not used. |
| [tagTRANSPORTBASICPARMS structure](ns-ksmedia-tagtransportbasicparms.md) | The TRANSPORTBASICPARMS structure is defined but not used. |
| [tagTRANSPORTSTATUS structure](ns-ksmedia-tagtransportstatus.md) | The TRANSPORTSTATUS structure describes the current transport status. |
| [tagTRANSPORTVIDEOPARMS structure](ns-ksmedia-tagtransportvideoparms.md) | The TRANSPORTVIDEOPARMS structure is defined but not presently used. It may be used in the future. |
| [tag_KS_TRUECOLORINFO structure](ns-ksmedia-tag_ks_truecolorinfo.md) | The KS_TRUECOLORINFO structure describes color palette and bitmask information for video images that also contain a palette. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [*PCAPTURE_MEMORY_ALLOCATION_FLAGS enumeration](ne-ksmedia-pcapture_memory_allocation_flags.md) | The CAPTURE_MEMORY_ALLOCATION_FLAGS enumeration defines types of memory surfaces to which AVStream minidrivers can capture audio and video data. |
| [AUDIO_CURVE_TYPE enumeration](ne-ksmedia-audio_curve_type.md) | The AUDIO_CURVE_TYPE enumeration defines constants that specify a curve algorithm to be applied to set a volume level. |
| [KSCAMERA_EXTENDEDPROP_FOCUSSTATE enumeration](ne-ksmedia-kscamera_extendedprop_focusstate.md) | This enumeration contains the focus states. |
| [KSCAMERA_EXTENDEDPROP_MetadataAlignment enumeration](ne-ksmedia-kscamera_extendedprop_metadataalignment.md) | This enumeration contains identifiers for the metadata alignment. |
| [KSCAMERA_EXTENDEDPROP_ROITYPE enumeration](ne-ksmedia-kscamera_extendedprop_roitype.md) | This enumeration contains the ROI types. |
| [KSCAMERA_MetadataId enumeration](ne-ksmedia-kscamera_metadataid.md) | This enumeration contains identifiers for a metadata item. |
| [KSCAMERA_PERFRAMESETTING_ITEM_TYPE enumeration](ne-ksmedia-kscamera_perframesetting_item_type.md) | This enumeration contains the different item types for the per-frame settings DDI. |
| [KSEVENT_CAMERACONTROL enumeration](ne-ksmedia-ksevent_cameracontrol.md) | Specifies camera control event notifications that the driver generates to indicate that an operation has been completed or canceled. |
| [KSEVENT_CAMERAEVENT enumeration](ne-ksmedia-ksevent_cameraevent.md) | KSEVENT_CAMERAEVENT enumerates a kernel streaming event set that can be used by the pipeline to enable or disable camera event notifications from the driver. |
| [KSPROPERTY_CAMERACONTROL_EXTENDED_PROPERTY enumeration](ne-ksmedia-ksproperty_cameracontrol_extended_property.md) | This enumeration contains extended camera controls. |
| [KSPROPERTY_CAMERACONTROL_FLASH enumeration](ne-ksmedia-ksproperty_cameracontrol_flash.md) | Used to specify camera flash control. |
| [KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY enumeration](ne-ksmedia-ksproperty_cameracontrol_image_pin_capability.md) | Used to identify whether the camera's image pin and record pin are mutually exclusive. If they are mutually exclusive, then when the record pin is active, the image pin cannot be active, and vice-versa. |
| [KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_PROPERTY enumeration](ne-ksmedia-ksproperty_cameracontrol_perframesetting_property.md) | This enumeration contains the property IDs defined for the per-frame property set. |
| [KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST enumeration](ne-ksmedia-ksproperty_cameracontrol_region_of_interest.md) | Used to specify a camera region of interest. |
| [KSPROPERTY_CAMERACONTROL_VIDEO_STABILIZATION_MODE enumeration](ne-ksmedia-ksproperty_cameracontrol_video_stabilization_mode.md) | Used to specify camera video stabilization. |
| [KS_AMPixAspectRatio enumeration](ne-ksmedia-ks_ampixaspectratio.md) | The KS_AMPixAspectRatio enumeration defines the pixel aspect ratio that corresponds to a 720 480 NTSC video signal or a 720 × 576 PAL video signal. |
| [KS_AMVP_MODE enumeration](ne-ksmedia-ks_amvp_mode.md) | The KS_AMVP_MODE enumeration defines video port display modes. |
| [KS_AMVP_SELECTFORMATBY enumeration](ne-ksmedia-ks_amvp_selectformatby.md) | The KS_AMVP_SELECTFORMATBY enumeration specifies the criteria that the Overlay Mixer Filter should use to select the video format. |
| [KS_AnalogVideoStandard enumeration](ne-ksmedia-ks_analogvideostandard.md) | The KS_AnalogVideoStandard enumeration defines various analog video standards that are used worldwide. |
| [KS_CameraControlAsyncOperation enumeration](ne-ksmedia-ks_cameracontrolasyncoperation.md) | Defines notifications that the driver uses to start and stop an asynchronous camera operation, including setting the flash, the image pin control properties, the region of interest in the image, or video stabilization. |
| [KS_CompressionCaps enumeration](ne-ksmedia-ks_compressioncaps.md) | The KS_CompressionCaps enumeration defines compression capabilities of a device. |
| [KS_DVDCOPYSTATE enumeration](ne-ksmedia-ks_dvdcopystate.md) | The KS_DVDCOPYSTATE enumeration describes the progress of the DVD copyright protection initialization, authentication and key negotiation sequence. |
| [KS_MPEG2Level enumeration](ne-ksmedia-ks_mpeg2level.md) | The KS_MPEG2Level enumeration describes MPEG-2 levels. |
| [KS_MPEG2Profile enumeration](ne-ksmedia-ks_mpeg2profile.md) | The KS_MPEG2Profile enumeration describes MPEG-2 profiles. |
| [KS_TUNER_STRATEGY enumeration](ne-ksmedia-ks_tuner_strategy.md) | The KS_TUNER_STRATEGY enumeration defines tuning method strategies. |
| [KS_TUNER_TUNING_FLAGS enumeration](ne-ksmedia-ks_tuner_tuning_flags.md) | The KS_TUNER_TUNING_FLAGS enumeration defines tuning flags that describe the granularity of a tuning operation. |
| [KS_VIDEODECODER_FLAGS enumeration](ne-ksmedia-ks_videodecoder_flags.md) | The KS_VIDEODECODER_FLAGS enumeration defines video decoder capabilities. |
| [KS_VideoControlFlags enumeration](ne-ksmedia-ks_videocontrolflags.md) | The KS_VideoControlFlags enumeration defines video control capabilities for a specific stream. |
| [KS_VideoStreamingHints enumeration](ne-ksmedia-ks_videostreaminghints.md) | The KS_VideoStreamingHints enumeration defines video compression hints. |
| [TELEPHONY_CALLCONTROLOP enumeration](ne-ksmedia-telephony_callcontrolop.md) | The TELEPHONY_CALLCONTROLOP enumeration defines constants that specify an operation to perform on a phone call. |
| [TELEPHONY_CALLSTATE enumeration](ne-ksmedia-telephony_callstate.md) | The TELEPHONY_CALLSTATE enumeration defines constants that specify the state of a phone call. |
| [TELEPHONY_CALLTYPE enumeration](ne-ksmedia-telephony_calltype.md) | The TELEPHONY_CALLTYPE enumeration defines constants that specify the type of phone call. |
| [TELEPHONY_PROVIDERCHANGEOP enumeration](ne-ksmedia-telephony_providerchangeop.md) | The TELEPHONY_PROVIDERCHANGEOP enumeration defines constants that specify the requested provider change operation. |
| [VIDEOENCODER_BITRATE_MODE enumeration](ne-ksmedia-videoencoder_bitrate_mode.md) | The VIDEOENCODER_BITRATE_MODE enumeration describes the bit rate encoding modes supported by the device. |
