---
UID: NC:usbcamdi.PFNUSBCAMD_SetIsoPipeState
title: PFNUSBCAMD_SetIsoPipeState (usbcamdi.h)
description: The USBCAMD_SetIsoPipeState service permits the camera minidriver to control the streaming state on the isochronous pipe.
tech.root: stream
ms.date: 03/08/2023
keywords: ["PFNUSBCAMD_SetIsoPipeState callback function"]
ms.keywords: PFNUSBCAMD_SetIsoPipeState, USBCAMD_SetIsoPipeState, USBCAMD_SetIsoPipeState routine [Streaming Media Devices], stream.usbcamd_setisopipestate, usbcamdi/USBCAMD_SetIsoPipeState, usbcmdpr_6643c631-6892-4955-8a1f-ae152fd155e4.xml
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
 - PFNUSBCAMD_SetIsoPipeState
 - usbcamdi/PFNUSBCAMD_SetIsoPipeState
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - usbcamdi.h
api_name:
 - PFNUSBCAMD_SetIsoPipeState
---

## -description

The **USBCAMD_SetIsoPipeState** service permits the camera minidriver to control the streaming state on the isochronous pipe.

## -parameters

### -param DeviceContext [in]

Pointer to device-specific context.

### -param PipeStateFlags [in]

Specifies the isochronous pipe state. This argument should be set to either of the following values:

| Flag | Meaning |
|---|---|
| USBCAMD_STOP_STREAM | This flags indicates to stop streaming. |
| USBCAMD_START_STREAM | This flags indicates to start streaming. |

## -returns

**USBCAMD_SetIsoPipeState** returns STATUS_SUCCESS if the call was successful. Other possible error codes include:

| Return code | Description |
|---|---|
| **STATUS_INVALID_PARAMETER** | The requested pipe state is the same as the current pipe state. |
| **STATUS_PENDING** | The pipe state change is deferred. |
| **STATUS_INSUFFICIENT_RESOURCES** | There are insufficient resources to allocate a work item to change the pipe state. |

## -remarks

Note that the streaming state on the isochronous pipe works differently from the streaming state in the stream class and in Microsoft DirectShow. It is possible to stop the isochronous pipe from streaming for a short period while the overall video capture graph is still in a Run state.

This function is used to enable dual-mode cameras. In a dual-mode camera, if there is a request to get still data while streaming is in progress, the stream must be stopped on the isochronous pipe. The still call is then serviced and then the isochronous stream must be restarted, all while the overall stream class/DirectShow graph is still in a **Run** state.

Using this function does not enable you to change the alternate setting within the USB video streaming interface or the channel bandwidth. The isochronous stream must be closed before the alternate setting is changed.

**USBCAMD_SetIsoPipeState** is not available in USBCAMD version 1.0.

## -see-also

[USBCAMD_INTERFACE](./ns-usbcamdi-usbcamd_interface.md)