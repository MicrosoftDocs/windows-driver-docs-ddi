---
UID: NA:usbcamdi
ms.assetid: 7f3b551e-5a01-3632-882a-60b6c21fdc36
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Usbcamdi.h header



This header is used by Streaming media devices. For more information, see
- [Streaming media devices](../_stream/index.md)

Usbcamdi.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [USBCAMD_AdapterReceivePacket function](nf-usbcamdi-usbcamd_adapterreceivepacket.md) | The USBCAMD_AdapterReceivePacket function allows USBCAMD to process an adapter-based stream request block (SRB). |
| [USBCAMD_ControlVendorCommand function](nf-usbcamdi-usbcamd_controlvendorcommand.md) | The USBCAMD_ControlVendorCommand function sends vendor-specific commands to the control pipe. |
| [USBCAMD_Debug_LogEntry function](nf-usbcamdi-usbcamd_debug_logentry.md) | The USBCAMD_Debug_LogEntry function is called by the camera minidriver to log debugging information to a file. |
| [USBCAMD_DriverEntry function](nf-usbcamdi-usbcamd_driverentry.md) | The USBCAMD_DriverEntry function registers the minidriver with USBCAMD, effectively binding USBCAMD and the minidriver together. |
| [USBCAMD_GetRegistryKeyValue function](nf-usbcamdi-usbcamd_getregistrykeyvalue.md) | The USBCAMD_GetRegistryKeyValue function retrieves the device-instance-specific registry key value. |
| [USBCAMD_InitializeNewInterface function](nf-usbcamdi-usbcamd_initializenewinterface.md) | The USBCAMD_InitializeNewInterface function provides USBCAMD with all the necessary information to configure the camera minidriver to work correctly with the stream class driver and the USB bus driver. |
| [USBCAMD_SelectAlternateInterface function](nf-usbcamdi-usbcamd_selectalternateinterface.md) | The USBCAMD_SelectAlternateInterface function selects an alternate setting within the USB video streaming interface. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [PADAPTER_RECEIVE_PACKET_ROUTINE callback](nc-usbcamdi-padapter_receive_packet_routine.md) | A camera minidriver's AdapterReceivePacket callback function processes adapter-based stream request blocks (SRBs) passed to it by the stream class driver. |
| [PCAM_ALLOCATE_BW_ROUTINE callback](nc-usbcamdi-pcam_allocate_bw_routine.md) | A camera minidriver's CamAllocateBandwidth callback function selects the appropriate alternate setting within the USB video streaming interface and prepares the device to stream. |
| [PCAM_ALLOCATE_BW_ROUTINE_EX callback](nc-usbcamdi-pcam_allocate_bw_routine_ex.md) | A camera minidriver's CamAllocateBandwidthEx callback function selects the appropriate alternate setting within the USB video streaming interface and prepares the device to stream. |
| [PCAM_CONFIGURE_ROUTINE callback](nc-usbcamdi-pcam_configure_routine.md) | A camera minidriver's CamConfigure callback function configures the isochronous streaming interface. |
| [PCAM_CONFIGURE_ROUTINE_EX callback](nc-usbcamdi-pcam_configure_routine_ex.md) | A camera minidriver's CamConfigureEx callback function configures the isochronous streaming interface. |
| [PCAM_FREE_BW_ROUTINE callback](nc-usbcamdi-pcam_free_bw_routine.md) | A camera minidriver's CamFreeBandwidth callback function selects an alternate setting within the USB video streaming interface that uses no bandwidth. |
| [PCAM_FREE_BW_ROUTINE_EX callback](nc-usbcamdi-pcam_free_bw_routine_ex.md) | A camera minidriver's CamFreeBandwidthEx callback function selects an alternate setting within the USB video streaming interface that uses no bandwidth. |
| [PCAM_INITIALIZE_ROUTINE callback](nc-usbcamdi-pcam_initialize_routine.md) | A camera minidriver's callback function initializes the device or performs any minidriver-specific clean-up that is required. |
| [PCAM_NEW_FRAME_ROUTINE callback](nc-usbcamdi-pcam_new_frame_routine.md) | A camera minidriver's CamNewVideoFrame callback function initializes a new video frame context structure. |
| [PCAM_NEW_FRAME_ROUTINE_EX callback](nc-usbcamdi-pcam_new_frame_routine_ex.md) | A camera minidriver's CamNewVideoFrameEx callback function initializes a new video frame context structure. |
| [PCAM_PROCESS_PACKET_ROUTINE callback](nc-usbcamdi-pcam_process_packet_routine.md) | A camera minidriver's CamProcessUSBPacket callback function processes a USB packet. |
| [PCAM_PROCESS_PACKET_ROUTINE_EX callback](nc-usbcamdi-pcam_process_packet_routine_ex.md) | A camera minidriver's CamProcessUSBPacketEx callback function processes a USB packet. |
| [PCAM_PROCESS_RAW_FRAME_ROUTINE callback](nc-usbcamdi-pcam_process_raw_frame_routine.md) | A camera minidriver's CamProcessRawVideoFrame callback function decodes a raw video frame. |
| [PCAM_PROCESS_RAW_FRAME_ROUTINE_EX callback](nc-usbcamdi-pcam_process_raw_frame_routine_ex.md) | A camera minidriver's CamProcessRawVideoFrameEx callback function decodes a raw video frame. |
| [PCAM_START_CAPTURE_ROUTINE callback](nc-usbcamdi-pcam_start_capture_routine.md) | A camera minidriver's CamStartCapture callback function selects the appropriate alternate setting within the USB video streaming interface and prepares the device to stream. |
| [PCAM_START_CAPTURE_ROUTINE_EX callback](nc-usbcamdi-pcam_start_capture_routine_ex.md) | A camera minidriver's CamStartCaptureEx callback function selects the appropriate alternate setting within the USB video streaming interface and prepares the device to stream. |
| [PCAM_STATE_ROUTINE callback](nc-usbcamdi-pcam_state_routine.md) | A camera minidriver's state callback function restores a previously saved device context state or saves the current device context state. |
| [PCAM_STOP_CAPTURE_ROUTINE callback](nc-usbcamdi-pcam_stop_capture_routine.md) | A camera minidriver's CamStopCapture callback function performs any processing after the stream is stopped. |
| [PCAM_STOP_CAPTURE_ROUTINE_EX callback](nc-usbcamdi-pcam_stop_capture_routine_ex.md) | A camera minidriver's CamStopCaptureEx callback function performs any processing after the stream is stopped. |
| [PCOMMAND_COMPLETE_FUNCTION callback](nc-usbcamdi-pcommand_complete_function.md) | A camera minidriver's CommandCompleteFunction callback function allows the camera minidriver to perform any additional tasks necessary to complete certain USBCAMD services |
| [PFNUSBCAMD_BulkReadWrite callback](nc-usbcamdi-pfnusbcamd_bulkreadwrite.md) | The USBCAMD_BulkReadWrite service performs a read or write operation on the specified bulk pipe. |
| [PFNUSBCAMD_CancelBulkReadWrite callback](nc-usbcamdi-pfnusbcamd_cancelbulkreadwrite.md) | The USBCAMD_CancelBulkReadWrite service cancels a pending bulk read or write request. |
| [PFNUSBCAMD_SetIsoPipeState callback](nc-usbcamdi-pfnusbcamd_setisopipestate.md) | The USBCAMD_SetIsoPipeState service permits the camera minidriver to control the streaming state on the isochronous pipe. |
| [PFNUSBCAMD_SetVideoFormat callback](nc-usbcamdi-pfnusbcamd_setvideoformat.md) | The USBCAMD_SetVideoFormat service is used to notify USBCAMD that the video format has changed. |
| [PFNUSBCAMD_WaitOnDeviceEvent callback](nc-usbcamdi-pfnusbcamd_waitondeviceevent.md) | The USBCAMD_WaitOnDeviceEvent service is used to perform a read from the interrupt pipe if the camera has an interrupt pipe for external event notifications. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [USBCAMD_INTERFACE structure](ns-usbcamdi-usbcamd_interface.md) | The USBCAMD_INTERFACE structure defines a set of services related to the USB bus interfaces. |
| [_USBCAMD_DEVICE_DATA structure](ns-usbcamdi-_usbcamd_device_data.md) | This structure is obsolete and is provided to maintain backward compatibility with the original USBCAMD. |
| [_USBCAMD_DEVICE_DATA2 structure](ns-usbcamdi-_usbcamd_device_data2.md) | The USBCAMD_DEVICE_DATA2 structure specifies the entry points for a camera minidriver's functions that USBCAMD calls. |
| [_pipe_config_descriptor structure](ns-usbcamdi-_pipe_config_descriptor.md) | The USBCAMD_Pipe_Config_Descriptor structure describes the association between pipes and streams. |
