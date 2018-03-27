---
UID: NC:dispmprt.DXGKDDI_DISPATCH_IO_REQUEST
title: DXGKDDI_DISPATCH_IO_REQUEST
author: windows-driver-content
description: The DxgkDdiDispatchIoRequest function handles I/O control (IOCTL) requests.
old-location: display\dxgkddidispatchiorequest.htm
old-project: display
ms.assetid: e1973aca-cbc2-4780-a3b5-7601e1cc6c90
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKDDI_DISPATCH_IO_REQUEST, DmFunctions_17ebc963-6659-4f1b-bd5a-f804c04be8b5.xml, DxgkDdiDispatchIoRequest, DxgkDdiDispatchIoRequest callback function [Display Devices], display.dxgkddidispatchiorequest, dispmprt/DxgkDdiDispatchIoRequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	dispmprt.h
api_name:
-	DxgkDdiDispatchIoRequest
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---

# DXGKDDI_DISPATCH_IO_REQUEST callback


## -description


The <i>DxgkDdiDispatchIoRequest</i> function handles I/O control (IOCTL) requests.


## -parameters




### -param MiniportDeviceContext [in]

A handle to a context block associated with a display adapter. The display miniport driver's <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


### -param VidPnSourceId [in]

An integer that identifies the video present source associated with the I/O request.


### -param VideoRequestPacket [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff570547">VIDEO_REQUEST_PACKET</a> structure that describes the I/O request.


## -returns



<i>DxgkDdiDispatchIoRequest</i> returns STATUS_SUCCESS if it succeeds; otherwise it returns one of the error codes defined in <i>Ntstatus.h</i>.




## -remarks



The <i>DxgkDdiDispatchIoRequest</i> function should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570547">VIDEO_REQUEST_PACKET</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_DISPATCH_IO_REQUEST callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

