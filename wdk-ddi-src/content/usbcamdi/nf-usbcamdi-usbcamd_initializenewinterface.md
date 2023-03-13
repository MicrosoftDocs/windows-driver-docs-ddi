---
UID: NF:usbcamdi.USBCAMD_InitializeNewInterface
title: USBCAMD_InitializeNewInterface function (usbcamdi.h)
description: The USBCAMD_InitializeNewInterface function provides USBCAMD with all the necessary information to configure the camera minidriver to work correctly with the stream class driver and the USB bus driver.
tech.root: stream
ms.date: 03/08/2023
keywords: ["USBCAMD_InitializeNewInterface function"]
ms.keywords: USBCAMD_InitializeNewInterface, USBCAMD_InitializeNewInterface function [Streaming Media Devices], stream.usbcamd_initializenewinterface, usbcamdi/USBCAMD_InitializeNewInterface, usbcmdpr_4b43d8ab-fd5f-4199-afbc-b21801c4fab3.xml
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
 - USBCAMD_InitializeNewInterface
 - usbcamdi/USBCAMD_InitializeNewInterface
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - usbcamd2.lib
 - usbcamd2.dll
api_name:
 - USBCAMD_InitializeNewInterface
---

## -description

The **USBCAMD_InitializeNewInterface** function provides USBCAMD with all the necessary information to configure the camera minidriver to work correctly with the stream class driver and the USB bus driver.

## -parameters

### -param DeviceContext [in]

Pointer to device-specific context.

### -param DeviceData [in]

Pointer to a [**USBCAMD_DEVICE_DATA2**](/windows-hardware/drivers/ddi/usbcamdi/ns-usbcamdi-_usbcamd_device_data2) structure.

### -param Version [in]

Specifies the version information. This value should be set to the value USBCAMD_VERSION_200 for use with USBCAMD version 2.0.

### -param CamControlFlag [in]

Specifies how USBCAMD and the camera minidriver should interact. The camera minidriver should set this value to one or more of the following:

| Flag | Meaning |
|---|---|
| USBCAMD_CamControlFlag_NoVideoRawProcessing | If the camera minidriver does not need to operate on video, it should set the USBCAMD_CamControlFlag_NoVideoRawProcessing. This eliminates one buffer copy. |
| USBCAMD_CamControlFlag_NoStillRawProcessing | If the camera minidriver does not need to operate on the still image raw frame, it should set the USBCAMD_CamControlFlag_NoStillRawProcessing bit to eliminate one buffer copy. |
| USBCAMD_CamControlFlag_AssociatedFormat | The USBCAMD_CamControlFlag_AssociatedFormat bit should be set if the camera minidriver uses the same format for video as it does on the virtual still pin. After this flag is set, USBCAMD does not permit the virtual still pin to be opened in a format different from the video pin. The USBCAMD_CamControlFlag_AssociatedFormat bit should be set only when the virtual still pin produces frames of the same format as the video frames. |
| USBCAMD_CamControlFlag_EnableDeviceEvents | Setting the USBCAMD_CamControlFlag_EnableDeviceEvents exposes a device event to the stream class driver and Microsoft DirectShow. This enables an STI monitor to launch a still image application if the still button is pressed on the camera. USBCAMD sends a [KSEVENT_VIDCAPTOSTI_EXT_TRIGGER](/windows-hardware/drivers/stream/ksevent-vidcaptosti-ext-trigger) event if this bit is set and the camera's still button is pressed. |

## -returns

**USBCAMD_InitializeNewInterface** returns the value USBCAMD_VERSION_200.

## -remarks

This function is only called by USBCAMD version 2.0.

The **USBCAMD_InitializeNewInterface** function must be called by the camera minidriver upon receiving an [SRB_INITIALIZE_DEVICE](/windows-hardware/drivers/stream/srb-initialize-device) request.

## -see-also

[SRB_INITIALIZE_DEVICE](/windows-hardware/drivers/stream/srb-initialize-device)

[**USBCAMD_DEVICE_DATA2**](/windows-hardware/drivers/ddi/usbcamdi/ns-usbcamdi-_usbcamd_device_data2)
