---
UID: NC:usbcamdi.PFNUSBCAMD_WaitOnDeviceEvent
title: PFNUSBCAMD_WaitOnDeviceEvent (usbcamdi.h)
description: The USBCAMD_WaitOnDeviceEvent service is used to perform a read from the interrupt pipe if the camera has an interrupt pipe for external event notifications.
tech.root: stream
ms.date: 03/08/2023
keywords: ["PFNUSBCAMD_WaitOnDeviceEvent callback function"]
ms.keywords: PFNUSBCAMD_WaitOnDeviceEvent, USBCAMD_WaitOnDeviceEvent, USBCAMD_WaitOnDeviceEvent routine [Streaming Media Devices], stream.usbcamd_waitondeviceevent, usbcamdi/USBCAMD_WaitOnDeviceEvent, usbcmdpr_854c2d35-c023-4d7a-8c2e-3e56d3150e41.xml
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
 - PFNUSBCAMD_WaitOnDeviceEvent
 - usbcamdi/PFNUSBCAMD_WaitOnDeviceEvent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - usbcamdi.h
api_name:
 - PFNUSBCAMD_WaitOnDeviceEvent
---

## -description

The **USBCAMD_WaitOnDeviceEvent** service is used to perform a read from the interrupt pipe if the camera has an interrupt pipe for external event notifications.

## -parameters

### -param DeviceContext [in]

A pointer to device-specific context.

### -param PipeIndex [in]

Specifies the index of the interrupt pipe.

### -param Buffer [in]

A pointer to the read buffer.

### -param BufferLength [in]

Length of the read buffer, in bytes.

### -param EventComplete [in]

Pointer to a camera minidriver defined [CommandCompleteFunction](/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcommand_complete_function), which is called when the interrupt read is completed This value can be **NULL**.

### -param EventContext [in]

Pointer to a block of memory, that is passed as an argument to the camera minidriver defined [CommandCompleteFunction](/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcommand_complete_function).

### -param LoopBack [in]

Specifies if USBCAMD is to resubmit another read request to the interrupt pipe every time an interrupt read is completed. Set to **TRUE**

## -returns

**USBCAMD_WaitOnDeviceEvent** returns STATUS_SUCCESS if the call was successful. Other possible error codes include:

| Return code | Description |
|---|---|
| **STATUS_FILE_CLOSED** | The device has been removed. |
| **STATUS_INVALID_PARAMETER** | USBCAMD may return STATUS_INVALID_PARAMETER for a number of reasons, including: The value passed in the *PipeIndex* argument is invalid, the type of the pipe specified by the *PipeIndex* argument represents an invalid type of pipe, a bulk read/write request already exists, or the *Buffer* argument is **NULL**. The length specified in the BufferLength argument is smaller than the maximum packet size. |
| **STATUS_PENDING** | The event work item is deferred. |
| **STATUS_INSUFFICIENT_RESOURCES** | There are insufficient resources to allocate a work item to read from the pipe. |

## -remarks

The typical usage scenario for this function is a camera with a snapshot button and an interrupt pipe associated with the button. When a user presses the snapshot button, the read request on the interrupt pipe is satisfied and the camera minidriver is called back. If the camera minidriver sets USBCAMD_CamControlFlag_EnableDeviceEvents in the *CamControlFlag* argument during the [USBCAMD_InitializeNewInterface](/windows-hardware/drivers/ddi/usbcamdi/nf-usbcamdi-usbcamd_initializenewinterface) call, the STI monitor also is notified of the snapshot event.

**USBCAMD_WaitOnDeviceEvent** is not available in USBCAMD version 1.0.

## -see-also

[CommandCompleteFunction](/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcommand_complete_function)

[USBCAMD_INTERFACE](/windows-hardware/drivers/ddi/usbcamdi/ns-usbcamdi-usbcamd_interface)

[USBCAMD_InitializeNewInterface](/windows-hardware/drivers/ddi/usbcamdi/nf-usbcamdi-usbcamd_initializenewinterface)
