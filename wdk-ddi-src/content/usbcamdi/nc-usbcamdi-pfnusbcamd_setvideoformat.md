---
UID: NC:usbcamdi.PFNUSBCAMD_SetVideoFormat
title: PFNUSBCAMD_SetVideoFormat (usbcamdi.h)
description: The USBCAMD_SetVideoFormat service is used to notify USBCAMD that the video format has changed.
tech.root: stream
ms.date: 03/08/2023
keywords: ["PFNUSBCAMD_SetVideoFormat callback function"]
ms.keywords: PFNUSBCAMD_SetVideoFormat, USBCAMD_SetVideoFormat, USBCAMD_SetVideoFormat routine [Streaming Media Devices], stream.usbcamd_setvideoformat, usbcamdi/USBCAMD_SetVideoFormat, usbcmdpr_c4209df8-d0e2-4727-b9f8-4b9b734be34c.xml
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
 - PFNUSBCAMD_SetVideoFormat
 - usbcamdi/PFNUSBCAMD_SetVideoFormat
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - usbcamdi.h
api_name:
 - PFNUSBCAMD_SetVideoFormat
---

## -description

The **USBCAMD_SetVideoFormat** service is used to notify USBCAMD that the video format has changed.

## -parameters

### -param DeviceContext [in]

Pointer to device-specific context.

### -param pSrb [in]

Pointer to a stream request block (SRB).

## -returns

**USBCAMD_SetVideoFormat** returns **TRUE** if the call was successful, otherwise it returns **FALSE** and sets *pSrb->Status* to one of the following error codes:

| Return code | Description |
|---|---|
| **STATUS_INVALID_PARAMETER** | USBCAMD may return STATUS_INVALID_PARAMETER for a number of reasons, including: Unknown video format Arithmetic overflow when calculating the video info header size or format size. |
| **STATUS_INSUFFICIENT_RESOURCES** | There are insufficient resources to allocate the video info header. |

## -remarks

Note that this function returns **TRUE** to indicate success and not STATUS_SUCCESS.

Camera minidrivers must handle all SRBs related to video format. Camera minidrivers should use **USBCAMD_SetVideoFormat** to inform USBCAMD of a video format change. Typically, the camera minidriver calls **USBCAMD_SetVideoFormat** from within its SRB_SET_DATA_FORMAT handler.

**USBCAMD_SetVideoFormat** is not available in USBCAMD version 1.0.

## -see-also

[SRB_SET_DATA_FORMAT](/windows-hardware/drivers/stream/srb-set-data-format)

[**USBCAMD_INTERFACE**](/windows-hardware/drivers/ddi/usbcamdi/ns-usbcamdi-usbcamd_interface)
