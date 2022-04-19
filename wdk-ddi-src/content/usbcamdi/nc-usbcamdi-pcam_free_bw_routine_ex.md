---
UID: NC:usbcamdi.PCAM_FREE_BW_ROUTINE_EX
title: PCAM_FREE_BW_ROUTINE_EX (usbcamdi.h)
description: A camera minidriver's CamFreeBandwidthEx callback function selects an alternate setting within the USB video streaming interface that uses no bandwidth.
tech.root: stream
ms.date: 04/19/2022
keywords: ["PCAM_FREE_BW_ROUTINE_EX callback function"]
ms.keywords: CamFreeBandwidthEx, CamFreeBandwidthEx routine [Streaming Media Devices], PCAM_FREE_BW_ROUTINE_EX, stream.camfreebandwidthex, usbcamdi/CamFreeBandwidthEx, usbcmdpr_bf3efd8f-3320-469c-a358-85cf2d896caf.xml
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - PCAM_FREE_BW_ROUTINE_EX
 - usbcamdi/PCAM_FREE_BW_ROUTINE_EX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - usbcamdi.h
api_name:
 - PCAM_FREE_BW_ROUTINE_EX
---

## -description

A camera minidriver's **CamFreeBandwidthEx** callback function selects an alternate setting within the USB video streaming interface that uses no bandwidth.

## -parameters

### -param BusDeviceObject

Pointer to the camera minidriver's device object created by the USB hub.

### -param DeviceContext

Pointer to the camera minidriver's device context.

### -param STreamNumber

Indicates stream number.

## -returns

**CamFreeBandwidthEx** returns STATUS_SUCCESS or an appropriate error code.

## -remarks

USBCAMD calls the camera minidriver's **CamFreeBandwidthEx** callback function after the isochronous video stream has stopped.

Typically, this function calls the **USBCAMD_SelectAlternateInterface** service to select the correct alternate interface and prepare for streaming video.

The original USBCAMD does not call **CamFreeBandwidthEx**.

This function is required.

## -see-also

[USBCAMD_DEVICE_DATA2](/windows-hardware/drivers/ddi/usbcamdi/ns-usbcamdi-_usbcamd_device_data2)

[USBCAMD_SelectAlternateInterface](/windows-hardware/drivers/ddi/usbcamdi/nf-usbcamdi-usbcamd_selectalternateinterface)
