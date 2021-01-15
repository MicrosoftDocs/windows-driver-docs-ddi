---
UID: NS:usbcamdi._USBCAMD_DEVICE_DATA2
title: _USBCAMD_DEVICE_DATA2 (usbcamdi.h)
description: The USBCAMD_DEVICE_DATA2 structure specifies the entry points for a camera minidriver's functions that USBCAMD calls.
old-location: stream\usbcamd_device_data2.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["USBCAMD_DEVICE_DATA2 structure"]
ms.keywords: "*PUSBCAMD_DEVICE_DATA2, PUSBCAMD_DEVICE_DATA2, PUSBCAMD_DEVICE_DATA2 structure pointer [Streaming Media Devices], USBCAMD_DEVICE_DATA2, USBCAMD_DEVICE_DATA2 structure [Streaming Media Devices], _USBCAMD_DEVICE_DATA2, stream.usbcamd_device_data2, usbcamdi/PUSBCAMD_DEVICE_DATA2, usbcamdi/USBCAMD_DEVICE_DATA2, usbcmdpr_01305731-bde1-4718-8ff9-d0f102d6cc34.xml"
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
targetos: Windows
req.typenames: USBCAMD_DEVICE_DATA2, *PUSBCAMD_DEVICE_DATA2
f1_keywords:
 - _USBCAMD_DEVICE_DATA2
 - usbcamdi/_USBCAMD_DEVICE_DATA2
 - PUSBCAMD_DEVICE_DATA2
 - usbcamdi/PUSBCAMD_DEVICE_DATA2
 - USBCAMD_DEVICE_DATA2
 - usbcamdi/USBCAMD_DEVICE_DATA2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbcamdi.h
api_name:
 - _USBCAMD_DEVICE_DATA2
 - PUSBCAMD_DEVICE_DATA2
 - USBCAMD_DEVICE_DATA2
---

# _USBCAMD_DEVICE_DATA2 structure


## -description

The USBCAMD_DEVICE_DATA2 structure specifies the entry points for a camera minidriver's functions that USBCAMD calls.

## -struct-fields

### -field Sig

Reserved. Do not use.

### -field CamInitialize

Pointer to the camera minidriver defined <a href="/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_initialize_routine">CamInitialize</a> callback function. This entry point is required.

### -field CamUnInitialize

Pointer to the camera minidriver defined <a href="/previous-versions/ff557646(v=vs.85)">CamUnInitialize</a> callback function. This entry point is required.

### -field CamProcessUSBPacketEx

Pointer to the camera minidriver defined <a href="/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_process_packet_routine_ex">CamProcessUSBPacketEx</a> callback function. This is an optional entry point. If the minidriver does not implement this function, it must point to an empty function.

### -field CamNewVideoFrameEx

Pointer to the camera minidriver defined <a href="/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_new_frame_routine_ex">CamNewVideoFrameEx</a> callback function. This is an optional entry point. If the minidriver does not implement this function, it must point to an empty function.

### -field CamProcessRawVideoFrameEx

Pointer to the camera minidriver defined <a href="/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_process_raw_frame_routine_ex">CamProcessRawVideoFrameEx</a> callback function. This is an optional entry point. If the minidriver does not implement this function, it must point to an empty function.

### -field CamStartCaptureEx

Pointer to the camera minidriver defined <a href="/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_start_capture_routine_ex">CamStartCaptureEx</a> callback function. This entry point is required.

### -field CamStopCaptureEx

Pointer to the camera minidriver defined <a href="/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_stop_capture_routine_ex">CamStopCaptureEx</a> callback function. This entry point is required.

### -field CamConfigureEx

Pointer to the camera minidriver defined <a href="/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_configure_routine_ex">CamConfigureEx</a> callback function. This entry point is required.

### -field CamSaveState

Pointer to the camera minidriver defined <a href="/previous-versions/ff557635(v=vs.85)">CamSaveState</a> callback function. This is an optional entry point. If the minidriver does not implement this function, it must point to an empty function.

### -field CamRestoreState

Pointer to the camera minidriver defined <a href="/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_state_routine">CamRestoreState</a> callback function. This is an optional entry point. If the minidriver does not implement this function, it must point to an empty function.

### -field CamAllocateBandwidthEx

Pointer to the camera minidriver defined <a href="/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_allocate_bw_routine_ex">CamAllocateBandwidthEx</a> callback function. This entry point is required.

### -field CamFreeBandwidthEx

Pointer to the camera minidriver defined <a href="/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_free_bw_routine_ex">CamFreeBandwidthEx</a> callback function. This entry point is required.

## -remarks

A camera minidriver passes a USBCAMD_DEVICE_DATA2 structure to USBCAMD as a parameter to USBCAMD service <a href="/windows-hardware/drivers/ddi/usbcamdi/nf-usbcamdi-usbcamd_initializenewinterface">USBCAMD_InitializeNewInterface</a>.

Camera minidrivers that must be backward compatible with the original USBCAMD library must use the <a href="/windows-hardware/drivers/ddi/usbcamdi/ns-usbcamdi-_usbcamd_device_data">USBCAMD_DEVICE_DATA</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_allocate_bw_routine_ex">CamAllocateBandwidthEx</a>



<a href="/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_configure_routine_ex">CamConfigureEx</a>



<a href="/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_free_bw_routine_ex">CamFreeBandwidthEx</a>



<a href="/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_initialize_routine">CamInitialize</a>



<a href="/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_new_frame_routine_ex">CamNewVideoFrameEx</a>



<a href="/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_process_raw_frame_routine_ex">CamProcessRawVideoFrameEx</a>



<a href="/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_process_packet_routine_ex">CamProcessUSBPacketEx</a>



<a href="/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_state_routine">CamRestoreState</a>



<a href="/previous-versions/ff557635(v=vs.85)">CamSaveState</a>



<a href="/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_start_capture_routine_ex">CamStartCaptureEx</a>



<a href="/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_stop_capture_routine_ex">CamStopCaptureEx</a>



<a href="/previous-versions/ff557646(v=vs.85)">CamUnInitialize</a>



<a href="/windows-hardware/drivers/ddi/usbcamdi/nf-usbcamdi-usbcamd_initializenewinterface">USBCAMD_InitializeNewInterface</a>

