---
UID: NS:usbcamdi._USBCAMD_DEVICE_DATA
title: _USBCAMD_DEVICE_DATA (usbcamdi.h)
description: This structure is obsolete and is provided to maintain backward compatibility with the original USBCAMD.
old-location: stream\usbcamd_device_data.htm
tech.root: stream
ms.assetid: 1841be02-e30f-4685-82ea-2d9c02ce7277
ms.date: 04/23/2018
ms.keywords: "*PUSBCAMD_DEVICE_DATA, PUSBCAMD_DEVICE_DATA, PUSBCAMD_DEVICE_DATA structure pointer [Streaming Media Devices], USBCAMD_DEVICE_DATA, USBCAMD_DEVICE_DATA structure [Streaming Media Devices], _USBCAMD_DEVICE_DATA, stream.usbcamd_device_data, usbcamdi/PUSBCAMD_DEVICE_DATA, usbcamdi/USBCAMD_DEVICE_DATA, usbcmdpr_1e4ea0e1-71e0-4c0e-a2bd-668f8fac9b02.xml"
ms.topic: struct
req.header: usbcamdi.h
req.include-header: Usbcamdi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- usbcamdi.h
api_name:
- USBCAMD_DEVICE_DATA
product:
- Windows
targetos: Windows
req.typenames: USBCAMD_DEVICE_DATA, *PUSBCAMD_DEVICE_DATA
---

# _USBCAMD_DEVICE_DATA structure


## -description


This structure is <b>obsolete</b> and is provided to maintain backward compatibility with the original USBCAMD. New camera minidrivers should use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbcamdi/ns-usbcamdi-_usbcamd_device_data2">USBCAMD_DEVICE_DATA2</a> structure.

The USBCAMD_DEVICE_DATA structure specifies the entry points for a camera minidriver's functions that the original USBCAMD calls.


## -struct-fields




### -field Sig

Reserved. Do not use.


### -field CamInitialize

Pointer to the camera minidriver defined <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbcamdi/nc-usbcamdi-pcam_initialize_routine">CamInitialize</a> callback function. This entry point is required.


### -field CamUnInitialize

Pointer to the camera minidriver defined <a href="https://docs.microsoft.com/previous-versions/ff557646(v=vs.85)">CamUnInitialize</a> callback function. This entry point is required.


### -field CamProcessUSBPacket

Pointer to the camera minidriver defined <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbcamdi/nc-usbcamdi-pcam_process_packet_routine">CamProcessUSBPacket</a> callback function. This is an optional entry point. If the minidriver does not implement this function, it must point to an empty function.


### -field CamNewVideoFrame

Pointer to the camera minidriver defined <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbcamdi/nc-usbcamdi-pcam_new_frame_routine">CamNewVideoFrame</a> callback function. This is an optional entry point. If the minidriver does not implement this function, it must point to an empty function.


### -field CamProcessRawVideoFrame

Pointer to the camera minidriver defined <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbcamdi/nc-usbcamdi-pcam_process_raw_frame_routine">CamProcessRawVideoFrame</a> callback function. This is an optional entry point. If the minidriver does not implement this function, it must point to an empty function.


### -field CamStartCapture

Pointer to the camera minidriver defined <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbcamdi/nc-usbcamdi-pcam_start_capture_routine">CamStartCapture</a> callback function. This entry point is required.


### -field CamStopCapture

Pointer to the camera minidriver defined <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbcamdi/nc-usbcamdi-pcam_stop_capture_routine">CamStopCapture</a> callback function. This entry point is required.


### -field CamConfigure

Pointer to the camera minidriver defined <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbcamdi/nc-usbcamdi-pcam_configure_routine">CamConfigure</a> callback function. This entry point is required.


### -field CamSaveState

Pointer to the camera minidriver defined <a href="https://docs.microsoft.com/previous-versions/ff557635(v=vs.85)">CamSaveState</a> callback function. This is an optional entry point. If the minidriver does not implement this function, it must point to an empty function.


### -field CamRestoreState

Pointer to the camera minidriver defined <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbcamdi/nc-usbcamdi-pcam_state_routine">CamRestoreState</a> callback function. This is an optional entry point. If the minidriver does not implement this function, it must point to an empty function.


### -field CamAllocateBandwidth

Pointer to the camera minidriver defined <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbcamdi/nc-usbcamdi-pcam_allocate_bw_routine">CamAllocateBandwidth</a> callback function. This entry point is required.


### -field CamFreeBandwidth

Pointer to the camera minidriver defined <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbcamdi/nc-usbcamdi-pcam_free_bw_routine">CamFreeBandwidth</a> callback function. This entry point is required.


## -remarks



A camera minidriver passes a USBCAMD_DEVICE_DATA structure to USBCAMD as a parameter to the USBCAMD library routine <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbcamdi/nf-usbcamdi-usbcamd_adapterreceivepacket">USBCAMD_AdapterReceivePacket</a> in the original USBCAMD.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbcamdi/ns-usbcamdi-_usbcamd_device_data2">USBCAMD_DEVICE_DATA2</a>
 

 

