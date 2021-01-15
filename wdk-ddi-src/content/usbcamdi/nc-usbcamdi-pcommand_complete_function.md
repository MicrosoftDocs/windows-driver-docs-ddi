---
UID: NC:usbcamdi.PCOMMAND_COMPLETE_FUNCTION
title: PCOMMAND_COMPLETE_FUNCTION (usbcamdi.h)
description: A camera minidriver's CommandCompleteFunction callback function allows the camera minidriver to perform any additional tasks necessary to complete certain USBCAMD services
old-location: stream\commandcompletefunction.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["PCOMMAND_COMPLETE_FUNCTION callback function"]
ms.keywords: CommandCompleteFunction, CommandCompleteFunction routine [Streaming Media Devices], PCOMMAND_COMPLETE_FUNCTION, stream.commandcompletefunction, usbcamdi/CommandCompleteFunction, usbcmdpr_7ac7f300-71eb-463c-8471-df736a32105e.xml
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
 - PCOMMAND_COMPLETE_FUNCTION
 - usbcamdi/PCOMMAND_COMPLETE_FUNCTION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - usbcamdi.h
api_name:
 - PCOMMAND_COMPLETE_FUNCTION
---

# PCOMMAND_COMPLETE_FUNCTION callback function


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

<a href="/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pfnusbcamd_bulkreadwrite">USBCAMD_BulkReadWrite</a>



<a href="/windows-hardware/drivers/ddi/usbcamdi/nf-usbcamdi-usbcamd_controlvendorcommand">USBCAMD_ControlVendorCommand</a>



<a href="/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pfnusbcamd_waitondeviceevent">USBCAMD_WaitOnDeviceEvent</a>

