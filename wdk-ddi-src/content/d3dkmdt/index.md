---
UID: NA:d3dkmdt
ms.assetid: 019f4ae8-bb25-3ccb-9dae-26b111c96303
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# D3Dkmdt.h header



This header is used by Display. For more information, see
- [Display](../_display/index.md)

D3Dkmdt.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [D3DKMDT_VPPR_GET_CONTENT_ROTATION function](nf-d3dkmdt-d3dkmdt_vppr_get_content_rotation.md) | A helper function that extracts the combined rotation that the user sees from the default display orientation from a given value of the D3DKMDT_VIDPN_PRESENT_PATH_ROTATION enumeration. |
| [D3DKMDT_VPPR_GET_CONTENT_ROTATION_PART function](nf-d3dkmdt-d3dkmdt_vppr_get_content_rotation_part.md) | A helper function that extracts the rotation angle from a given value of the D3DKMDT_VIDPN_PRESENT_PATH_ROTATION enumeration. |
| [D3DKMDT_VPPR_GET_OFFSET_ROTATION function](nf-d3dkmdt-d3dkmdt_vppr_get_offset_rotation.md) | A helper function that extracts the offset angle from a given value of the D3DKMDT_VIDPN_PRESENT_PATH_ROTATION enumeration. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_D3DKMDT_2DREGION structure](ns-d3dkmdt-_d3dkmdt_2dregion.md) | The D3DKMDT_2DREGION structure is used to represent a point or an offset in a two-dimensional space. |
| [_D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES structure](ns-d3dkmdt-_d3dkmdt_color_coeff_dynamic_ranges.md) | The D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES contains values that indicate the dynamic range of each color channel of a video present target or a monitor. |
| [_D3DKMDT_FREQUENCY_RANGE structure](ns-d3dkmdt-_d3dkmdt_frequency_range.md) | The D3DKMDT_FREQUENCY_RANGE structure contains the minimum and maximum refresh rates supported by a monitor. |
| [_D3DKMDT_GAMMA_RAMP structure](ns-d3dkmdt-_d3dkmdt_gamma_ramp.md) | The D3DKMDT_GAMMA_RAMP structure contains descriptive information about a gamma lookup table and a pointer to the lookup table. |
| [_D3DKMDT_GDISURFACEDATA structure](ns-d3dkmdt-_d3dkmdt_gdisurfacedata.md) | The D3DKMDT_GDISURFACEDATA structure describes surfaces that are used by GDI hardware acceleration and the Desktop Window Manager (DWM). |
| [_D3DKMDT_GDISURFACEFLAGS structure](ns-d3dkmdt-_d3dkmdt_gdisurfaceflags.md) | The D3DKMDT_GDISURFACEFLAGS structure is reserved for system use. Do not use it in your driver. |
| [_D3DKMDT_GRAPHICS_RENDERING_FORMAT structure](ns-d3dkmdt-_d3dkmdt_graphics_rendering_format.md) | The D3DKMDT_GRAPHICS_RENDERING_FORMAT structure contains information about a primary rendering surface. |
| [_D3DKMDT_MONITOR_DESCRIPTOR structure](ns-d3dkmdt-_d3dkmdt_monitor_descriptor.md) | The D3DKMDT_MONITOR_DESCRIPTOR structure contains a pointer to a monitor descriptor along with information about the monitor descriptor. |
| [_D3DKMDT_MONITOR_FREQUENCY_RANGE structure](ns-d3dkmdt-_d3dkmdt_monitor_frequency_range.md) | The D3DKMDT_MONITOR_FREQUENCY_RANGE structure contains information about a range of frequencies supported by a monitor. |
| [_D3DKMDT_MONITOR_SOURCE_MODE structure](ns-d3dkmdt-_d3dkmdt_monitor_source_mode.md) | The D3DKMDT_MONITOR_SOURCE_MODE structure contains information about a monitor source mode. |
| [_D3DKMDT_PALETTEDATA structure](ns-d3dkmdt-_d3dkmdt_palettedata.md) | The D3DKMDT_PALETTEDATA structure describes a palette entry for the display. |
| [_D3DKMDT_PREEMPTION_CAPS structure](ns-d3dkmdt-_d3dkmdt_preemption_caps.md) | Specifies the capabilities for the preemption of graphic processing unit (GPU) graphics requests that the display miniport driver supports. |
| [_D3DKMDT_SHADOWSURFACEDATA structure](ns-d3dkmdt-_d3dkmdt_shadowsurfacedata.md) | The D3DKMDT_SHADOWSURFACEDATA structure describes a lockable shadow surface, which matches the primary surface in format and resolution for a given display mode. |
| [_D3DKMDT_SHAREDPRIMARYSURFACEDATA structure](ns-d3dkmdt-_d3dkmdt_sharedprimarysurfacedata.md) | The D3DKMDT_SHAREDPRIMARYSURFACEDATA structure describes a shared primary surface. |
| [_D3DKMDT_STAGINGSURFACEDATA structure](ns-d3dkmdt-_d3dkmdt_stagingsurfacedata.md) | The D3DKMDT_STAGINGSURFACEDATA structure describes the lockable staging surface that data is transferred into from an application's back buffer. |
| [_D3DKMDT_VIDEO_PRESENT_SOURCE structure](ns-d3dkmdt-_d3dkmdt_video_present_source.md) | The D3DKMDT_VIDEO_PRESENT_SOURCE structure contains the unique identifier of a video present source. |
| [_D3DKMDT_VIDEO_PRESENT_TARGET structure](ns-d3dkmdt-_d3dkmdt_video_present_target.md) | The D3DKMDT_VIDEO_PRESENT_TARGET structure contains information about a video present target. |
| [_D3DKMDT_VIDEO_SIGNAL_INFO structure](ns-d3dkmdt-_d3dkmdt_video_signal_info.md) | The D3DKMDT_VIDEO_SIGNAL_INFO structure contains information about a video signal driven by a video output on a display adapter. |
| [_D3DKMDT_VIDPN_HW_CAPABILITY structure](ns-d3dkmdt-_d3dkmdt_vidpn_hw_capability.md) | The D3DKMDT_VIDPN_HW_CAPABILITY structure describes the capabilities of the display miniport driver to perform display operations on a specified functional VidPN without dedicated GPU hardware support. |
| [_D3DKMDT_VIDPN_PRESENT_PATH structure](ns-d3dkmdt-_d3dkmdt_vidpn_present_path.md) | The D3DKMDT_VIDPN_PRESENT_PATH structure contains information about a video present path. |
| [_D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION structure](ns-d3dkmdt-_d3dkmdt_vidpn_present_path_copyprotection.md) | The D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION structure contains information about the copy protection that is supported (as well as the copy protection that is currently active) on a particular VidPN present path. |
| [_D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT structure](ns-d3dkmdt-_d3dkmdt_vidpn_present_path_copyprotection_support.md) | The D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT structure is used to indicate the types of copy protection that are supported by a particular VidPN present path. |
| [_D3DKMDT_VIDPN_PRESENT_PATH_ROTATION_SUPPORT structure](ns-d3dkmdt-_d3dkmdt_vidpn_present_path_rotation_support.md) | The D3DKMDT_VIDPN_PRESENT_PATH_ROTATION_SUPPORT structure is used to indicate the angles of rotation that are supported by a particular VidPN present path. |
| [_D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT structure](ns-d3dkmdt-_d3dkmdt_vidpn_present_path_scaling_support.md) | The D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT structure is used to indicate the types of scaling (and centering) that are supported by a particular VidPN present path. |
| [_D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION structure](ns-d3dkmdt-_d3dkmdt_vidpn_present_path_transformation.md) | The D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION structure contains information about the transformations (for example, rotation, scaling, centering) that are pinned and the transformations that are supported for a path in a video present network (VIDPN). |
| [_D3DKMDT_VIDPN_SOURCE_MODE structure](ns-d3dkmdt-_d3dkmdt_vidpn_source_mode.md) | The D3DKMDT_VIDPN_SOURCE_MODE structure contains information about a video present network (VidPN) source mode. |
| [_D3DKMDT_VIDPN_TARGET_MODE structure](ns-d3dkmdt-_d3dkmdt_vidpn_target_mode.md) | The D3DKMDT_VIDPN_TARGET_MODE structure contains information about a video present network (VidPN) target mode. |
| [_D3DKMDT_WIRE_FORMAT_AND_PREFERENCE structure](ns-d3dkmdt-_d3dkmdt_wire_format_and_preference.md) | Holds information about the preferred pixel encoding format. |
| [_D3DKMT_MOVE_RECT structure](ns-d3dkmdt-_d3dkmt_move_rect.md) | Provides information on a screen-to-screen move and a dirty rectangle copy operation. |
| [_DISPLAYID_DETAILED_TIMING_TYPE_I structure](ns-d3dkmdt-_displayid_detailed_timing_type_i.md) | The DISPLAYID_DETAILED_TIMING_TYPE_I structure specifies an additional target mode set for a video present target. |
| [_DXGKARG_SETPALETTE structure](ns-d3dkmdt-_dxgkarg_setpalette.md) | The DXGKARG_SETPALETTE structure describes the palette to set for a display. |
| [_DXGKMDT_OPM_ACP_AND_CGMSA_SIGNALING structure](ns-d3dkmdt-_dxgkmdt_opm_acp_and_cgmsa_signaling.md) | The DXGKMDT_OPM_ACP_AND_CGMSA_SIGNALING structure describes how the signal that goes through the physical connector that is associated with the protected output object is protected. |
| [_DXGKMDT_OPM_ACTUAL_OUTPUT_FORMAT structure](ns-d3dkmdt-_dxgkmdt_opm_actual_output_format.md) | The DXGKMDT_OPM_ACTUAL_OUTPUT_FORMAT structure describes the format of the signal that is transmitted from a physical connector that is associated with a protected output to a monitor. |
| [_DXGKMDT_OPM_CONFIGURE_PARAMETERS structure](ns-d3dkmdt-_dxgkmdt_opm_configure_parameters.md) | The DXGKMDT_OPM_CONFIGURE_PARAMETERS structure contains parameters that are used to configure a protected output object in a call to the DxgkDdiOPMConfigureProtectedOutput function. |
| [_DXGKMDT_OPM_CONNECTED_HDCP_DEVICE_INFORMATION structure](ns-d3dkmdt-_dxgkmdt_opm_connected_hdcp_device_information.md) | The DXGKMDT_OPM_CONNECTED_HDCP_DEVICE_INFORMATION structure contains High-bandwidth Digital Content Protection (HDCP) information that is retrieved in a call to the DxgkDdiOPMGetInformation function. |
| [_DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS structure](ns-d3dkmdt-_dxgkmdt_opm_copp_compatible_get_info_parameters.md) | The DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS structure contains parameters that are used to retrieve information from a protected output object in a call to the DxgkDdiOPMGetCOPPCompatibleInformation function. |
| [_DXGKMDT_OPM_ENCRYPTED_PARAMETERS structure](ns-d3dkmdt-_dxgkmdt_opm_encrypted_parameters.md) | The DXGKMDT_OPM_ENCRYPTED_PARAMETERS structure contains data that is encrypted with the public key from an appropriate certificate. |
| [_DXGKMDT_OPM_GET_INFO_PARAMETERS structure](ns-d3dkmdt-_dxgkmdt_opm_get_info_parameters.md) | The DXGKMDT_OPM_GET_INFO_PARAMETERS structure contains parameters that are used to retrieve information from a protected output object in a call to the DxgkDdiOPMGetInformation function. |
| [_DXGKMDT_OPM_HDCP_KEY_SELECTION_VECTOR structure](ns-d3dkmdt-_dxgkmdt_opm_hdcp_key_selection_vector.md) | The DXGKMDT_OPM_HDCP_KEY_SELECTION_VECTOR structure contains a key-selection vector (KSV) for a High-bandwidth Digital Content Protection (HDCP) protected output. |
| [_DXGKMDT_OPM_OMAC structure](ns-d3dkmdt-_dxgkmdt_opm_omac.md) | The DXGKMDT_OPM_OMAC structure contains a One-key Cipher Block Chaining (CBC)-mode message authentication code (OMAC) for message authenticity. |
| [_DXGKMDT_OPM_OUTPUT_ID structure](ns-d3dkmdt-_dxgkmdt_opm_output_id.md) | The DXGKMDT_OPM_OUTPUT_ID structure identifies the output connector. |
| [_DXGKMDT_OPM_RANDOM_NUMBER structure](ns-d3dkmdt-_dxgkmdt_opm_random_number.md) | The DXGKMDT_OPM_RANDOM_NUMBER structure contains a 128-bit cryptographically secure random number. |
| [_DXGKMDT_OPM_REQUESTED_INFORMATION structure](ns-d3dkmdt-_dxgkmdt_opm_requested_information.md) | The DXGKMDT_OPM_REQUESTED_INFORMATION structure contains information that was requested in a call to the DxgkDdiOPMGetInformation or DxgkDdiOPMGetCOPPCompatibleInformation function. |
| [_DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS structure](ns-d3dkmdt-_dxgkmdt_opm_set_acp_and_cgmsa_signaling_parameters.md) | The DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS structure contains parameters to set Analog Content Protection (ACP) and Content Generation Management System Analog (CGMS-A) signaling for a protected output. |
| [_DXGKMDT_OPM_SET_HDCP_SRM_PARAMETERS structure](ns-d3dkmdt-_dxgkmdt_opm_set_hdcp_srm_parameters.md) | The DXGKMDT_OPM_SET_HDCP_SRM_PARAMETERS structure contains parameters to set the version of a High-bandwidth Digital Content Protection (HDCP) System Renewability Message (SRM) for a protected output. |
| [_DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS structure](ns-d3dkmdt-_dxgkmdt_opm_set_protection_level_parameters.md) | The DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS structure contains parameters to set the protection level of a protected output in a call to the DxgkDdiOPMConfigureProtectedOutput function. |
| [_DXGKMDT_OPM_STANDARD_INFORMATION structure](ns-d3dkmdt-_dxgkmdt_opm_standard_information.md) | The DXGKMDT_OPM_STANDARD_INFORMATION structure contains information that is retrieved in a call to the DxgkDdiOPMGetInformation or DxgkDdiOPMGetCOPPCompatibleInformation function. The type of information is described in the ulInformation member. |
| [_DXGK_BACKLIGHT_INFO structure](ns-d3dkmdt-_dxgk_backlight_info.md) | Contains the current level of backlight reduction that is applied to the integrated display panel. Used by Windows Display Driver Model (WDDM) 1.2 and later display miniport drivers that support adaptive brightness control. |
| [_DXGK_BRIGHTNESS_CAPS structure](ns-d3dkmdt-_dxgk_brightness_caps.md) | Identifies brightness control capabilities of an integrated display panel that the display miniport driver provides through a call to its DxgkDdiGetBrightnessCaps function. |
| [_DXGK_BRIGHTNESS_STATE structure](ns-d3dkmdt-_dxgk_brightness_state.md) | Used to enable smooth brightness control for an integrated display panel. |
| [_DXGK_DISPLAY_INFORMATION structure](ns-d3dkmdt-_dxgk_display_information.md) | Contains the display information that is passed between the operating system and the display miniport driver when the driver is started or stopped in response to a Plug and Play (PnP) event. |
| [_DXGK_FAULT_ERROR_CODE structure](ns-d3dkmdt-_dxgk_fault_error_code.md) | The DXGK_FAULT_ERROR_CODE structure provides a status code for the graphics processing unit (GPU) error reported via a page fault interrupt. |
| [_DXGK_MONITORLINKINFO_CAPABILITIES structure](ns-d3dkmdt-_dxgk_monitorlinkinfo_capabilities.md) | Flags which describe the capabilities for driving the monitor. |
| [_DXGK_MONITORLINKINFO_USAGEHINTS structure](ns-d3dkmdt-_dxgk_monitorlinkinfo_usagehints.md) | Hints to the driver on the intended usage of the display device. |
| [_DXGK_TARGETMODE_DETAIL_TIMING structure](ns-d3dkmdt-_dxgk_targetmode_detail_timing.md) | The DXGK_TARGETMODE_DETAIL_TIMING structure describes a video present target's additional timing modes that are compatible with the display device. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [DXGK_BACKLIGHT_OPTIMIZATION_LEVEL enumeration](ne-d3dkmdt-dxgk_backlight_optimization_level.md) | Indicates the optimization level of brightness control. Used by Windows Display Driver Model (WDDM) 1.2 and later display miniport drivers that support adaptive brightness control. |
| [DXGK_ENGINE_TYPE enumeration](ne-d3dkmdt-dxgk_engine_type.md) | Indicates the type of engine on a GPU node. Note the selection rules discussed in Remarks. |
| [_D3DKMDT_COLOR_BASIS enumeration](ne-d3dkmdt-_d3dkmdt_color_basis.md) | The D3DKMDT_COLOR_BASIS enumeration contains constants that indicate the color basis used to encode the content of a video present source or the signal on a video present target. |
| [_D3DKMDT_COMPUTE_PREEMPTION_GRANULARITY enumeration](ne-d3dkmdt-_d3dkmdt_compute_preemption_granularity.md) | Specifies the capabilities for the preemption of graphic processing unit (GPU) compute shader operations that the display miniport driver supports. |
| [_D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE enumeration](ne-d3dkmdt-_d3dkmdt_enumcofuncmodality_pivot_type.md) | The D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE enumeration indicates the pivot type in a call to DxgkDdiEnumVidPnCofuncModality. |
| [_D3DKMDT_GDISURFACETYPE enumeration](ne-d3dkmdt-_d3dkmdt_gdisurfacetype.md) | The D3DKMDT_GDISURFACETYPE enumeration indicates the type of lockable surface that is used by the Desktop Window Manager (DWM) for redirection. |
| [_D3DKMDT_GRAPHICS_PREEMPTION_GRANULARITY enumeration](ne-d3dkmdt-_d3dkmdt_graphics_preemption_granularity.md) | Specifies the capabilities for the preemption of graphic processing unit (GPU) graphics operations that the display miniport driver supports. |
| [_D3DKMDT_GTFCOMPLIANCE enumeration](ne-d3dkmdt-_d3dkmdt_gtfcompliance.md) | The D3DKMDT_GTFCOMPLIANCE enumeration is reserved for system use. Do not use it in your driver. |
| [_D3DKMDT_MODE_PREFERENCE enumeration](ne-d3dkmdt-_d3dkmdt_mode_preference.md) | The D3DKMDT_MODE_PREFERENCE enumeration is used to indicate whether a particular mode is one of the modes preferred by the monitor connected to a given video present target. |
| [_D3DKMDT_MONITOR_CAPABILITIES_ORIGIN enumeration](ne-d3dkmdt-_d3dkmdt_monitor_capabilities_origin.md) | The D3DKMDT_MONITOR_CAPABILITIES_ORIGIN enumeration is used to indicate where a monitor's capability information was obtained. |
| [_D3DKMDT_MONITOR_CONNECTIVITY_CHECKS enumeration](ne-d3dkmdt-_d3dkmdt_monitor_connectivity_checks.md) | The D3DKMDT_MONITOR_CONNECTIVITY_CHECKS enumerated type indicates whether the DxgkDdiCommitVidPn function should verify that certain video outputs have connected monitors. |
| [_D3DKMDT_MONITOR_DESCRIPTOR_TYPE enumeration](ne-d3dkmdt-_d3dkmdt_monitor_descriptor_type.md) | The D3DKMDT_MONITOR_DESCRIPTOR_TYPE enumeration is used to indicate a particular type of monitor descriptor. |
| [_D3DKMDT_MONITOR_FREQUENCY_RANGE_CONSTRAINT enumeration](ne-d3dkmdt-_d3dkmdt_monitor_frequency_range_constraint.md) | The D3DKMDT_MONITOR_FREQUENCY_RANGE_CONSTRAINT enumeration is used to indicate the type of constraint under which a monitor frequency range is supported. |
| [_D3DKMDT_MONITOR_ORIENTATION enumeration](ne-d3dkmdt-_d3dkmdt_monitor_orientation.md) | The D3DKMDT_MONITOR_ORIENTATION enumeration is used to describe the orientation (rotation angle) of a connected external display device. |
| [_D3DKMDT_MONITOR_ORIENTATION_AWARENESS enumeration](ne-d3dkmdt-_d3dkmdt_monitor_orientation_awareness.md) | The D3DKMDT_MONITOR_ORIENTATION_AWARENESS enumeration is used to describe the ability of a video output device (on the display adapter) to detect changes in the orientation (rotation angle) of a connected external display device. |
| [_D3DKMDT_MONITOR_TIMING_TYPE enumeration](ne-d3dkmdt-_d3dkmdt_monitor_timing_type.md) | The D3DKMDT_MONITOR_TIMING_TYPE enumeration is reserved for system use. Do not use it in your driver. |
| [_D3DKMDT_PIXEL_VALUE_ACCESS_MODE enumeration](ne-d3dkmdt-_d3dkmdt_pixel_value_access_mode.md) | The D3DKMDT_PIXEL_VALUE_ACCESS_MODE enumeration is used to indicate the way color values or palette indices are stored in the primary surface of a video present source. |
| [_D3DKMDT_STANDARDALLOCATION_TYPE enumeration](ne-d3dkmdt-_d3dkmdt_standardallocation_type.md) | The D3DKMDT_STANDARDALLOCATION_TYPE enumeration type contains values that identify particular types of surfaces. |
| [_D3DKMDT_TEXT_RENDERING_FORMAT enumeration](ne-d3dkmdt-_d3dkmdt_text_rendering_format.md) | The D3DKMDT_TEXT_RENDERING_FORMAT enumeration is currently not used. |
| [_D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY enumeration](ne-d3dkmdt-_d3dkmdt_video_output_technology.md) | The D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY enumerated type indicates the type of connector a video output device (on the display adapter) uses to connect to an external display device. |
| [_D3DKMDT_VIDEO_SIGNAL_STANDARD enumeration](ne-d3dkmdt-_d3dkmdt_video_signal_standard.md) | The D3DKMDT_VIDEO_SIGNAL_STANDARD enumeration contains constants that represent video signal standards. |
| [_D3DKMDT_VIDPN_PRESENT_PATH_CONTENT enumeration](ne-d3dkmdt-_d3dkmdt_vidpn_present_path_content.md) | The D3DKMDT_VIDPN_PRESENT_PATH_CONTENT enumeration is used to indicate the type of content that is displayed on a VidPN present path. |
| [_D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_TYPE enumeration](ne-d3dkmdt-_d3dkmdt_vidpn_present_path_copyprotection_type.md) | The D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_TYPE enumeration is used to indicate the type of copy protection that is supported by a VidPN present path. |
| [_D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE enumeration](ne-d3dkmdt-_d3dkmdt_vidpn_present_path_importance.md) | The D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE enumeration indicates the importance of a video present path. |
| [_D3DKMDT_VIDPN_PRESENT_PATH_ROTATION enumeration](ne-d3dkmdt-_d3dkmdt_vidpn_present_path_rotation.md) | The D3DKMDT_VIDPN_PRESENT_PATH_ROTATION enumeration is used to indicate the rotation angle applied to content displayed on a VidPN present path. |
| [_D3DKMDT_VIDPN_PRESENT_PATH_SCALING enumeration](ne-d3dkmdt-_d3dkmdt_vidpn_present_path_scaling.md) | The D3DKMDT_VIDPN_PRESENT_PATH_SCALING enumeration is used to indicate the scaling transformation applied to content displayed on a VidPN present path. |
| [_D3DKMDT_VIDPN_SOURCE_MODE_TYPE enumeration](ne-d3dkmdt-_d3dkmdt_vidpn_source_mode_type.md) | The D3DKMDT_VIDPN_SOURCE_MODE_TYPE enumeration is used to indicate whether a video present network (VidPN) source mode is a graphics mode, a text mode, or a stereo mode. |
| [_DISPLAYID_DETAILED_TIMING_TYPE_I_ASPECT_RATIO enumeration](ne-d3dkmdt-_displayid_detailed_timing_type_i_aspect_ratio.md) | The DISPLAYID_DETAILED_TIMING_TYPE_I_ASPECT_RATIO enumeration indicates the display device's aspect ratio, defined as width by height (width x height). |
| [_DISPLAYID_DETAILED_TIMING_TYPE_I_SCANNING_MODE enumeration](ne-d3dkmdt-_displayid_detailed_timing_type_i_scanning_mode.md) | The DISPLAYID_DETAILED_TIMING_TYPE_I_SCANNING_MODE enumeration indicates the display device's frame scanning mode. |
| [_DISPLAYID_DETAILED_TIMING_TYPE_I_STEREO_MODE enumeration](ne-d3dkmdt-_displayid_detailed_timing_type_i_stereo_mode.md) | The DISPLAYID_DETAILED_TIMING_TYPE_I_STEREO_MODE enumeration indicates the display device's stereo vision mode. |
| [_DISPLAYID_DETAILED_TIMING_TYPE_I_SYNC_POLARITY enumeration](ne-d3dkmdt-_displayid_detailed_timing_type_i_sync_polarity.md) | The DISPLAYID_DETAILED_TIMING_TYPE_I_SYNC_POLARITY enumeration indicates the display device's sync polarity (whether the sync signal is positive or negative). |
| [_DXGKDT_OPM_DVI_CHARACTERISTICS enumeration](ne-d3dkmdt-_dxgkdt_opm_dvi_characteristics.md) | The DXGKDT_OPM_DVI_CHARACTERISTICS enumeration indicates the Digital Video Interface (DVI) electrical characteristics of a connector. |
| [_DXGKMDT_CERTIFICATE_TYPE enumeration](ne-d3dkmdt-_dxgkmdt_certificate_type.md) | The DXGKMDT_CERTIFICATE_TYPE enumeration identifies the type of certificate that callers of the DxgkDdiOPMGetCertificateSize and DxgkDdiOPMGetCertificate functions require. |
| [_DXGKMDT_DPCP_PROTECTION_LEVEL enumeration](ne-d3dkmdt-_dxgkmdt_dpcp_protection_level.md) | The DXGKMDT_OPM_DPCP_PROTECTION_LEVEL enumeration indicates the protection levels for a protected output that supports DisplayPort Content Protection (DPCP). |
| [_DXGKMDT_OPM_ACP_PROTECTION_LEVEL enumeration](ne-d3dkmdt-_dxgkmdt_opm_acp_protection_level.md) | The DXGKMDT_OPM_ACP_PROTECTION_LEVEL enumeration indicates the protection levels for a protected output that supports Analog Copy Protection (ACP). |
| [_DXGKMDT_OPM_BUS_TYPE_AND_IMPLEMENTATION enumeration](ne-d3dkmdt-_dxgkmdt_opm_bus_type_and_implementation.md) | The DXGKMDT_OPM_BUS_TYPE_AND_IMPLEMENTATION enumeration contains values that indicate the type and implementation of the bus that connects a graphics adapter to a motherboard chipset's north bridge. |
| [_DXGKMDT_OPM_CGMSA enumeration](ne-d3dkmdt-_dxgkmdt_opm_cgmsa.md) | The DXGKMDT_OPM_CGMSA enumeration indicates the protection levels for a protected output that supports Content Generation Management System Analog (CGMS-A). |
| [_DXGKMDT_OPM_HDCP_FLAG enumeration](ne-d3dkmdt-_dxgkmdt_opm_hdcp_flag.md) | The DXGKMDT_OPM_HDCP_FLAG enumeration identifies whether a protected output's physical connector is connected to a High-bandwidth Digital Content Protection (HDCP) repeater. |
| [_DXGKMDT_OPM_HDCP_PROTECTION_LEVEL enumeration](ne-d3dkmdt-_dxgkmdt_opm_hdcp_protection_level.md) | The DXGKMDT_OPM_HDCP_PROTECTION_LEVEL enumeration indicates the protection levels for a protected output that supports High-bandwidth Digital Content Protection (HDCP). |
| [_DXGKMDT_OPM_INTERLEAVE_FORMAT enumeration](ne-d3dkmdt-_dxgkmdt_opm_interleave_format.md) | The DXGKMDT_OPM_INTERLEAVE_FORMAT enumeration indicates the scan line ordering of a video frame from a protected output's signal. |
| [_DXGKMDT_OPM_PROTECTION_STANDARD enumeration](ne-d3dkmdt-_dxgkmdt_opm_protection_standard.md) | The DXGKMDT_OPM_PROTECTION_STANDARD enumeration indicates the type of television signal for which a video output supports protection. |
| [_DXGKMDT_OPM_PROTECTION_TYPE enumeration](ne-d3dkmdt-_dxgkmdt_opm_protection_type.md) | The DXGKMDT_OPM_PROTECTION_TYPE enumeration indicates the type of protections that a video output supports. |
| [_DXGKMDT_OPM_STATUS enumeration](ne-d3dkmdt-_dxgkmdt_opm_status.md) | The DXGKMDT_OPM_STATUS enumeration identifies the status of a protected output. |
| [_DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS enumeration](ne-d3dkmdt-_dxgkmdt_opm_video_output_semantics.md) | The DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS enumeration identifies the semantics of a protected output that is created in a call to the DxgkDdiOPMCreateProtectedOutput function. |
| [_DXGK_CHILD_DEVICE_HPD_AWARENESS enumeration](ne-d3dkmdt-_dxgk_child_device_hpd_awareness.md) | The DXGK_CHILD_DEVICE_HPD_AWARENESS enumeration is used to describe the hot plug capabilities of a child device of a display adapter. |
| [_DXGK_DISPLAY_DESCRIPTOR_TYPE enumeration](ne-d3dkmdt-_dxgk_display_descriptor_type.md) | Enum used to express the display descriptor type. |
| [_DXGK_DISPLAY_TECHNOLOGY enumeration](ne-d3dkmdt-_dxgk_display_technology.md) | Enum used to specify the display technology being used. |
| [_DXGK_DISPLAY_USAGE enumeration](ne-d3dkmdt-_dxgk_display_usage.md) | Enum used to specify the display type being used. |
| [_DXGK_GENERAL_ERROR_CODE enumeration](ne-d3dkmdt-_dxgk_general_error_code.md) | The DXGK_GENERAL_ERROR_CODE enumeration specifies a set of predefined graphics processing unit (GPU) errors reported via a page fault interrupt. |
| [_DXGK_PAGE_FAULT_FLAGS enumeration](ne-d3dkmdt-_dxgk_page_fault_flags.md) | DXGK_PAGE_FAULT_FLAGS enumeration describes the nature of the page fault that has occurred and the prescribed OS recovery action. |
| [_DXGK_RENDER_PIPELINE_STAGE enumeration](ne-d3dkmdt-_dxgk_render_pipeline_stage.md) | The DXGK_RENDER_PIPELINE_STAGE enumeration describes the render pipeline stage during which the GPU error has occurred. |
