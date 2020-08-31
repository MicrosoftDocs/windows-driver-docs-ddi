---
UID: NC:dispmprt.DXGKDDI_DISPATCH_IO_REQUEST
title: DXGKDDI_DISPATCH_IO_REQUEST (dispmprt.h)
description: The DxgkDdiDispatchIoRequest function handles I/O control (IOCTL) requests.
old-location: display\dxgkddidispatchiorequest.htm
tech.root: display
ms.assetid: e1973aca-cbc2-4780-a3b5-7601e1cc6c90
ms.date: 05/10/2018
keywords: ["DXGKDDI_DISPATCH_IO_REQUEST callback function"]
ms.keywords: DXGKDDI_DISPATCH_IO_REQUEST, DXGKDDI_DISPATCH_IO_REQUEST callback, DmFunctions_17ebc963-6659-4f1b-bd5a-f804c04be8b5.xml, DxgkDdiDispatchIoRequest, DxgkDdiDispatchIoRequest callback function [Display Devices], display.dxgkddidispatchiorequest, dispmprt/DxgkDdiDispatchIoRequest
req.header: dispmprt.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - DXGKDDI_DISPATCH_IO_REQUEST
 - dispmprt/DXGKDDI_DISPATCH_IO_REQUEST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DxgkDdiDispatchIoRequest
---

# DXGKDDI_DISPATCH_IO_REQUEST callback function


## -description

The <i>DxgkDdiDispatchIoRequest</i> function handles I/O control (IOCTL) requests.

## -parameters

### -param MiniportDeviceContext 

[in]
A handle to a context block associated with a display adapter. The display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.

### -param VidPnSourceId 

[in]
An integer that identifies the video present source associated with the I/O request.

### -param VideoRequestPacket 

[in]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_request_packet">VIDEO_REQUEST_PACKET</a> structure that describes the I/O request.

## -returns

<i>DxgkDdiDispatchIoRequest</i> returns STATUS_SUCCESS if it succeeds; otherwise it returns one of the error codes defined in <i>Ntstatus.h</i>.

## -remarks

The <i>DxgkDdiDispatchIoRequest</i> function should be made pageable.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_request_packet">VIDEO_REQUEST_PACKET</a>

