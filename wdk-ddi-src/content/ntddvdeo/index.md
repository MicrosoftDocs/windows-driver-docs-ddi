---
UID: NA:ntddvdeo
ms.assetid: d139e37c-aaeb-32a4-a038-0fe5f25ee5e9
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Ntddvdeo.h header



This header is used by Display. For more information, see
- [Display](../_display/index.md)

Ntddvdeo.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [_DISPLAY_BRIGHTNESS structure](ns-ntddvdeo-_display_brightness.md) | The DISPLAY_BRIGHTNESS structure is reserved for system use. |
| [_DXGK_WIN32K_PARAM_DATA structure](ns-ntddvdeo-_dxgk_win32k_param_data.md) | The DXGK_WIN32K_PARAM_DATA structure is reserved for system use. |
| [_ENG_EVENT structure](ns-ntddvdeo-_eng_event.md) | The ENG_EVENT structure is reserved for system use. |
| [_VIDEO_MEMORY structure](ns-ntddvdeo-_video_memory.md) | The VIDEO_MEMORY structure holds the address of a requested block of kernel-mode video memory. |
| [_VIDEO_MEMORY_INFORMATION structure](ns-ntddvdeo-_video_memory_information.md) | The VIDEO_MEMORY_INFORMATION structure contains information about a mapping of video memory into system space or the private virtual address space of a user-mode process. |
| [_VIDEO_MODE structure](ns-ntddvdeo-_video_mode.md) | The VIDEO_MODE structure contains the requested VGA mode that an adapter should set. This structure is used in conjunction with IOCTL_VIDEO_SET_CURRENT_MODE. |
| [_VIDEO_MODE_INFORMATION structure](ns-ntddvdeo-_video_mode_information.md) | The VIDEO_MODE_INFORMATION structure contains all of the information about one mode of a video adapter. |
| [_VIDEO_NUM_MODES structure](ns-ntddvdeo-_video_num_modes.md) | The VIDEO_NUM_MODES structure contains the number of modes supported by a video adapter, and the size of the structure that describes each mode. |
| [_VIDEO_POINTER_ATTRIBUTES structure](ns-ntddvdeo-_video_pointer_attributes.md) | The VIDEO_POINTER_ATTRIBUTES structure contains attributes of the screen pointer. |
| [_VIDEO_POINTER_CAPABILITIES structure](ns-ntddvdeo-_video_pointer_capabilities.md) | Contains capabilities of the screen pointer. |
| [_VIDEO_POINTER_POSITION structure](ns-ntddvdeo-_video_pointer_position.md) | The VIDEO_POINTER_POSITION structure contains the location of the screen pointer relative to the top left corner of the screen. |
| [_VIDEO_POWER_MANAGEMENT structure](ns-ntddvdeo-_video_power_management.md) | The VIDEO_POWER_MANAGEMENT structure contains information required by the miniport driver to perform power management. |
| [_VIDEO_PUBLIC_ACCESS_RANGES structure](ns-ntddvdeo-_video_public_access_ranges.md) | The VIDEO_PUBLIC_ACCESS_RANGES structure contains information about video resources other than frame buffers and video RAM, such as memory-mapped I/O registers or ports. |
| [_VIDEO_SHARE_MEMORY structure](ns-ntddvdeo-_video_share_memory.md) | The VIDEO_SHARE_MEMORY structure is used in a request to the video miniport driver for a block of user-mode memory to be shared with the specified process. |
| [_VIDEO_SHARE_MEMORY_INFORMATION structure](ns-ntddvdeo-_video_share_memory_information.md) | The VIDEO_SHARE_MEMORY_INFORMATION structure is used to communicate to the display driver that a request for a block of user-mode memory has been fulfilled. |
| [_VIDEO_WIN32K_CALLBACKS structure](ns-ntddvdeo-_video_win32k_callbacks.md) | The VIDEO_WIN32K_CALLBACKS structure is reserved for system use. |
| [_VIDEO_WIN32K_CALLBACKS_PARAMS structure](ns-ntddvdeo-_video_win32k_callbacks_params.md) | The VIDEO_WIN32K_CALLBACKS_PARAMS structure and the VIDEO_WIN32K_CALLBACKS_PARAMS_TYPE enumeration are reserved for system use. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_VIDEO_DISABLE_CURSOR IOCTL](ni-ntddvdeo-ioctl_video_disable_cursor.md) | Makes the cursor invisible by disabling the cursor's visibility attribute. Miniport drivers for VGA-compatible adapters are required to support this modal request; optional for other miniport drivers. |
| [IOCTL_VIDEO_DISABLE_POINTER IOCTL](ni-ntddvdeo-ioctl_video_disable_pointer.md) | Makes the pointer invisible by disabling the pointer attributes. Support for this modal request is optional. |
| [IOCTL_VIDEO_ENABLE_CURSOR IOCTL](ni-ntddvdeo-ioctl_video_enable_cursor.md) | Makes the cursor visible by enabling the cursor's visibility attribute. Miniport drivers for VGA-compatible adapters are required to support this modal request; optional for other miniport drivers. |
| [IOCTL_VIDEO_ENABLE_POINTER IOCTL](ni-ntddvdeo-ioctl_video_enable_pointer.md) | Makes the pointer visible by enabling pointer attributes. Support for this modal request is optional; however, if a miniport driver supports this request, it must process an IOCTL_VIDEO_SET_POINTER_ATTR request before processing this request. |
| [IOCTL_VIDEO_ENABLE_VDM IOCTL](ni-ntddvdeo-ioctl_video_enable_vdm.md) | This IOCTL is not handled by video miniport drivers. It is handled entirely by the system-supplied video port driver. |
| [IOCTL_VIDEO_FREE_PUBLIC_ACCESS_RANGES IOCTL](ni-ntddvdeo-ioctl_video_free_public_access_ranges.md) | Releases the address range that was allocated by a preceding IOCTL_VIDEO_QUERY_PUBLIC_ACCESS_RANGES request. Support for this nonmodal request is optional. |
| [IOCTL_VIDEO_GET_BANK_SELECT_CODE IOCTL](ni-ntddvdeo-ioctl_video_get_bank_select_code.md) | Returns a block of x86-specific executable code to be used by a high-resolution SVGA display driver for bank switching. Miniport drivers for VGA-compatible adapters are required to support this modal request; optional for other miniport drivers. |
| [IOCTL_VIDEO_GET_CHILD_STATE IOCTL](ni-ntddvdeo-ioctl_video_get_child_state.md) | Determines whether a child device is currently enabled. |
| [IOCTL_VIDEO_GET_POWER_MANAGEMENT IOCTL](ni-ntddvdeo-ioctl_video_get_power_management.md) | This IOCTL is obsolete in Windows 2000 and later, and is no longer supported. |
| [IOCTL_VIDEO_HANDLE_VIDEOPARAMETERS IOCTL](ni-ntddvdeo-ioctl_video_handle_videoparameters.md) | Gets the capabilities of the device's television connector and/or copy protection hardware, or sets the desired functionality on the copy protection hardware. |
| [IOCTL_VIDEO_INIT_WIN32K_CALLBACKS IOCTL](ni-ntddvdeo-ioctl_video_init_win32k_callbacks.md) | This IOCTL is for internal use only. |
| [IOCTL_VIDEO_LOAD_AND_SET_FONT IOCTL](ni-ntddvdeo-ioctl_video_load_and_set_font.md) | Loads a user-defined font on the adapter. Miniport drivers for VGA-compatible adapters are required to support this modal request; optional for other miniport drivers. |
| [IOCTL_VIDEO_MAP_VIDEO_MEMORY IOCTL](ni-ntddvdeo-ioctl_video_map_video_memory.md) | Maps the video hardware frame buffer and video RAM into the virtual address space of the requester. |
| [IOCTL_VIDEO_PREPARE_FOR_EARECOVERY IOCTL](ni-ntddvdeo-ioctl_video_prepare_for_earecovery.md) | This IOCTL is for internal use only. |
| [IOCTL_VIDEO_QUERY_AVAIL_MODES IOCTL](ni-ntddvdeo-ioctl_video_query_avail_modes.md) | Returns information about each video mode supported by the adapter. Miniport drivers are required to support this nonmodal request. |
| [IOCTL_VIDEO_QUERY_COLOR_CAPABILITIES IOCTL](ni-ntddvdeo-ioctl_video_query_color_capabilities.md) | Returns the color-capabilities information found in the VDDP description file for the adapter. |
| [IOCTL_VIDEO_QUERY_CURRENT_MODE IOCTL](ni-ntddvdeo-ioctl_video_query_current_mode.md) | Returns information about the current adapter mode. Miniport drivers are required to support this modal request. |
| [IOCTL_VIDEO_QUERY_CURSOR_ATTR IOCTL](ni-ntddvdeo-ioctl_video_query_cursor_attr.md) | Returns the size, position, and visibility of the cursor. |
| [IOCTL_VIDEO_QUERY_CURSOR_POSITION IOCTL](ni-ntddvdeo-ioctl_video_query_cursor_position.md) | Returns the current cursor position (row and column). Miniport drivers for VGA-compatible adapters are required to support this modal request; optional for other miniport drivers. |
| [IOCTL_VIDEO_QUERY_DISPLAY_BRIGHTNESS IOCTL](ni-ntddvdeo-ioctl_video_query_display_brightness.md) | This IOCTL is not handled by video miniport drivers. It is handled entirely by the system-supplied video port driver. |
| [IOCTL_VIDEO_QUERY_NUM_AVAIL_MODES IOCTL](ni-ntddvdeo-ioctl_video_query_num_avail_modes.md) | Returns the number of video modes supported by the adapter and the size in bytes of the video mode information, which can be used to allocate a buffer for an IOCTL_VIDEO_QUERY_AVAIL_MODES request. |
| [IOCTL_VIDEO_QUERY_POINTER_ATTR IOCTL](ni-ntddvdeo-ioctl_video_query_pointer_attr.md) | Returns the attributes for the pointer, defined as a set of pixels used to paint the shape associated with the mouse. Support for this modal request is optional. |
| [IOCTL_VIDEO_QUERY_POINTER_CAPABILITIES IOCTL](ni-ntddvdeo-ioctl_video_query_pointer_capabilities.md) | Returns information about the adapter's &#0034;hardware cursor&#0034; features. Support for this modal request is optional. |
| [IOCTL_VIDEO_QUERY_POINTER_POSITION IOCTL](ni-ntddvdeo-ioctl_video_query_pointer_position.md) | Returns the current position of the pointer. Support for this modal request is optional. |
| [IOCTL_VIDEO_QUERY_PUBLIC_ACCESS_RANGES IOCTL](ni-ntddvdeo-ioctl_video_query_public_access_ranges.md) | Returns an array, possibly with one element, of address ranges used to program the adapter registers or ports directly. Support for this nonmodal request is optional. |
| [IOCTL_VIDEO_QUERY_SUPPORTED_BRIGHTNESS IOCTL](ni-ntddvdeo-ioctl_video_query_supported_brightness.md) | This IOCTL is not handled by video miniport drivers. It is handled entirely by the system-supplied video port driver. |
| [IOCTL_VIDEO_RESET_DEVICE IOCTL](ni-ntddvdeo-ioctl_video_reset_device.md) | Resets the video hardware to the default mode, to which it was initialized at system boot. Miniport drivers are required to support this nonmodal request. |
| [IOCTL_VIDEO_RESTORE_HARDWARE_STATE IOCTL](ni-ntddvdeo-ioctl_video_restore_hardware_state.md) | Restores all values used to set the hardware registers. Miniport drivers for VGA-compatible adapters are required to support this nonmodal request; optional for other miniport drivers. |
| [IOCTL_VIDEO_SAVE_HARDWARE_STATE IOCTL](ni-ntddvdeo-ioctl_video_save_hardware_state.md) | Saves the state of the video adapter in the VRP OutputBuffer. Miniport drivers for VGA-compatible adapters are required to support this nonmodal request; optional for other miniport drivers. |
| [IOCTL_VIDEO_SET_CHILD_STATE_CONFIGURATION IOCTL](ni-ntddvdeo-ioctl_video_set_child_state_configuration.md) | Performs a display device switch, a state change in which the video signal going to one display device is sent to another, possibly different type of display device. |
| [IOCTL_VIDEO_SET_COLOR_REGISTERS IOCTL](ni-ntddvdeo-ioctl_video_set_color_registers.md) | Sets the adapter's color registers to the specified RGB values. If the adapter has a color look up table (CLUT), sometimes called a palette, the miniport driver is required to support this modal request. |
| [IOCTL_VIDEO_SET_CURRENT_MODE IOCTL](ni-ntddvdeo-ioctl_video_set_current_mode.md) | Sets the adapter to the specified operating mode. |
| [IOCTL_VIDEO_SET_CURSOR_ATTR IOCTL](ni-ntddvdeo-ioctl_video_set_cursor_attr.md) | Sets the cursor size, position, and visibility. Miniport drivers for VGA-compatible adapters are required to support this request, which is modal. Support is optional for other miniport drivers. |
| [IOCTL_VIDEO_SET_CURSOR_POSITION IOCTL](ni-ntddvdeo-ioctl_video_set_cursor_position.md) | Sets the cursor position (row and column). Miniport drivers for VGA-compatible adapters are required to support this request, which is modal. It is optional for other miniport drivers. |
| [IOCTL_VIDEO_SET_DISPLAY_BRIGHTNESS IOCTL](ni-ntddvdeo-ioctl_video_set_display_brightness.md) | This IOCTL is not handled by video miniport drivers. It is handled entirely by the system-supplied video port driver. |
| [IOCTL_VIDEO_SET_PALETTE_REGISTERS IOCTL](ni-ntddvdeo-ioctl_video_set_palette_registers.md) | Loads a specified portion of the adapter palette registers with an array of colors. Miniport drivers for VGA-compatible adapters are required to support this request, which is modal. Support is optional for other miniport drivers. |
| [IOCTL_VIDEO_SET_POINTER_ATTR IOCTL](ni-ntddvdeo-ioctl_video_set_pointer_attr.md) | Sets the pointer attributes. |
| [IOCTL_VIDEO_SET_POINTER_POSITION IOCTL](ni-ntddvdeo-ioctl_video_set_pointer_position.md) | Sets the pointer position. Support for this modal request is optional. A supporting miniport driver should have already processed an enable-pointer request before processing this request. |
| [IOCTL_VIDEO_SET_POWER_MANAGEMENT IOCTL](ni-ntddvdeo-ioctl_video_set_power_management.md) | This IOCTL is obsolete in Windows 2000 and later, and is no longer supported. |
| [IOCTL_VIDEO_SHARE_VIDEO_MEMORY IOCTL](ni-ntddvdeo-ioctl_video_share_video_memory.md) | This IOCTL is called by a process that will share user-mode video memory as a linear frame buffer. |
| [IOCTL_VIDEO_SWITCH_DUALVIEW IOCTL](ni-ntddvdeo-ioctl_video_switch_dualview.md) | Notifies the video miniport that a secondary view is about to be enabled or disabled. |
| [IOCTL_VIDEO_UNMAP_VIDEO_MEMORY IOCTL](ni-ntddvdeo-ioctl_video_unmap_video_memory.md) | Releases a mapping between the virtual address space and the adapter's frame buffer and video RAM. Miniport drivers are required to support this nonmodal request. |
| [IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY IOCTL](ni-ntddvdeo-ioctl_video_unshare_video_memory.md) | Unmaps a video hardware frame buffer and video RAM from the virtual address space of the requester that was mapped by an IOCTL_VIDEO_SHARE_VIDEO_MEMORY request. |
| [IOCTL_VIDEO_VALIDATE_CHILD_STATE_CONFIGURATION IOCTL](ni-ntddvdeo-ioctl_video_validate_child_state_configuration.md) | Queries the miniport driver to determine whether it is ready for a display device switch. |
