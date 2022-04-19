---
UID: NF:usbcamdi.USBCAMD_DriverEntry
title: USBCAMD_DriverEntry function (usbcamdi.h)
description: The USBCAMD_DriverEntry function registers the minidriver with USBCAMD, effectively binding USBCAMD and the minidriver together.
tech.root: stream
ms.date: 04/19/2022
keywords: ["USBCAMD_DriverEntry function"]
ms.keywords: USBCAMD_DriverEntry, USBCAMD_DriverEntry function [Streaming Media Devices], stream.usbcamd_driverentry, usbcamdi/USBCAMD_DriverEntry, usbcmdpr_3aeb66f4-1729-400c-af6d-6e1290c9fe3b.xml
req.header: usbcamdi.h
req.include-header: Usbcamdi.h
req.target-type: Desktop
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
req.lib: Usbcamd2.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - USBCAMD_DriverEntry
 - usbcamdi/USBCAMD_DriverEntry
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - usbcamd2.lib
 - usbcamd2.dll
api_name:
 - USBCAMD_DriverEntry
---

## -description

The **USBCAMD_DriverEntry** function registers the minidriver with USBCAMD, effectively binding USBCAMD and the minidriver together.

## -parameters

### -param Context1 [in]

Pointer to the first argument that is passed to the camera minidriver's DriverEntry function. This is effectively a pointer to the driver object that is created by the system and passed to DriverEntry.

### -param Context2 [in]

Pointer to the second argument that is passed to the camera minidriver's DriverEntry function. This is effectively a pointer to the registry path that describes the minidriver's registry key.

### -param DeviceContextSize [in]

Specifies the size, in bytes, required for the minidriver's device-specific context.

### -param FrameCOntextSize [in]

Specifies the size, in bytes, required for the minidriver's frame-specific context structure. Use **NULL** if not needed.

### -param ReceivePacket [in]

Pointer to the minidriver-defined [AdapterReceivePacket](/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-padapter_receive_packet_routine) function that handles adapter-based SRB requests.

## -returns

**USBCAMD_DriverEntry** returns the status of the registration attempt. If a value other than STATUS_SUCCESS is returned, the minidriver is unloaded.

## -remarks

A camera minidriver must call **USBCAMD_DriverEntry** from the minidriver's **DriverEntry** routine. For more information, see [DriverEntry for Stream Class Minidrivers](/previous-versions/ff558717(v=vs.85))

*FrameContextSize* is optional. A non-**NULL** value should be provided only with calls to [CamNewVideoFrame](/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_new_frame_routine) or [CamProcessRawVideoFrame](/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_process_raw_frame_routine).

## -see-also

[AdapterReceivePacket](/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-padapter_receive_packet_routine)

[CamNewVideoFrame](/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_new_frame_routine)

[CamProcessRawVideoFrame](/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_process_raw_frame_routine)
