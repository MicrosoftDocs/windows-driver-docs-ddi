---
UID: NC:usbcamdi.PCOMMAND_COMPLETE_FUNCTION
title: PCOMMAND_COMPLETE_FUNCTION
author: windows-driver-content
description: A camera minidriver's CommandCompleteFunction callback function allows the camera minidriver to perform any additional tasks necessary to complete certain USBCAMD services
old-location: stream\commandcompletefunction.htm
old-project: stream
ms.assetid: f3bce52a-3420-42b6-8026-6731ce541b83
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: CommandCompleteFunction, CommandCompleteFunction routine [Streaming Media Devices], PCOMMAND_COMPLETE_FUNCTION, stream.commandcompletefunction, usbcamdi/CommandCompleteFunction, usbcmdpr_7ac7f300-71eb-463c-8471-df736a32105e.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	usbcamdi.h
api_name:
-	CommandCompleteFunction
product: Windows
targetos: Windows
req.typenames: USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3
req.product: Windows 10 or later.
---

# PCOMMAND_COMPLETE_FUNCTION callback


## -description


A camera minidriver's <i>CommandCompleteFunction</i> callback function allows the camera minidriver to perform any additional tasks necessary to complete certain USBCAMD services


## -parameters




### -param DeviceContext

Specifies the user-supplied value or structure relevant to the stream.


### -param CommandContext

Specifies the context passed to <i>CommandCompleteFunction</i> by certain USBCAMD services.


### -param NtStatus

Specifies the completion status of the called function.


## -returns



<i>CommandCompleteFunction</i> does not return a value.




## -remarks



The following USBCAMD services allow for the camera minidriver to perform any additional tasks:

USBCAMD_BulkReadWrite

USBCAMD_ControlVendorCommand

USBCAMD_WaitOnDeviceEvent.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568577">USBCAMD_BulkReadWrite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568581">USBCAMD_ControlVendorCommand</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568638">USBCAMD_WaitOnDeviceEvent</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PCOMMAND_COMPLETE_FUNCTION routine%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

