---
UID: NC:dispmprt.DXGKCB_MIRACAST_SEND_MESSAGE_CALLBACK
title: DXGKCB_MIRACAST_SEND_MESSAGE_CALLBACK (dispmprt.h)
description: Called in kernel mode when the message that was sent to the user-mode driver with a call to the DxgkCbMiracastSendMessage function has completed or has been canceled.
old-location: display\dxgkcbmiracastsendmessage.htm
tech.root: display
ms.assetid: E8C3B9E3-854C-488D-809B-0F0893591352
ms.date: 05/10/2018
keywords: ["DXGKCB_MIRACAST_SEND_MESSAGE_CALLBACK callback function"]
ms.keywords: DXGKCB_MIRACAST_SEND_MESSAGE, DXGKCB_MIRACAST_SEND_MESSAGE callback, DxgkCbMiracastSendMessage, DxgkCbMiracastSendMessage callback function [Display Devices], display.dxgkcbmiracastsendmessage, dispmprt/DxgkCbMiracastSendMessage
f1_keywords:
 - "dispmprt/DxgkCbMiracastSendMessageCallback"
 - "DxgkCbMiracastSendMessageCallback"
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Dispmprt.h
api_name:
- DxgkCbMiracastSendMessageCallback
targetos: Windows
req.typenames: 
---

# DXGKCB_MIRACAST_SEND_MESSAGE_CALLBACK callback function


## -description


Called in kernel mode when the message that was sent to the user-mode driver with a call to the DxgkCbMiracastSendMessage function has completed or has been canceled.


## -parameters




### -param CallbackContext

A pointer to the driver-supplied callback context. The operating system passes this context to the driver-supplied callback routine after the operation has completed.


### -param pIoStatusBlock

A pointer to a driver-supplied buffer to hold the returned IO_STATUS_BLOCK structure for the completed or canceled user-mode message. This structure holds the status of the I/O call and the number of bytes that the user-mode driver wrote to the output buffer.




## -remarks

This function can be called simultaneously from multiple execution threads.

The operating system guarantees that this function follows the zero level synchronization mode as defined in Threading and Synchronization Zero Level.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_miracast_display_callbacks">DXGK_MIRACAST_DISPLAY_CALLBACKS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_miracast_send_message_callback">DxgkCbMiracastSendMessageCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_miracast_create_context">DxgkDdiMiracastCreateContext</a>
 

 

