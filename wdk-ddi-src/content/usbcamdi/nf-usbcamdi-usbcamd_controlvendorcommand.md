---
UID: NF:usbcamdi.USBCAMD_ControlVendorCommand
title: USBCAMD_ControlVendorCommand function (usbcamdi.h)
description: The USBCAMD_ControlVendorCommand function sends vendor-specific commands to the control pipe.
tech.root: stream
ms.date: 03/08/2023
keywords: ["USBCAMD_ControlVendorCommand function"]
ms.keywords: USBCAMD_ControlVendorCommand, USBCAMD_ControlVendorCommand function [Streaming Media Devices], stream.usbcamd_controlvendorcommand, usbcamdi/USBCAMD_ControlVendorCommand, usbcmdpr_71f3fad0-03ef-4328-90cf-d556de6736f5.xml
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
req.irql: Greater than or equal to PASSIVE_LEVEL (See Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - USBCAMD_ControlVendorCommand
 - usbcamdi/USBCAMD_ControlVendorCommand
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - usbcamd2.lib
 - usbcamd2.dll
api_name:
 - USBCAMD_ControlVendorCommand
---

## -description

The **USBCAMD_ControlVendorCommand** function sends vendor-specific commands to the control pipe.

## -parameters

### -param DeviceContext [in]

Pointer to device-specific context.

### -param Request [in]

Specifies the value of the **Request** field for the vendor command.

### -param Value [in]

Specifies the value of the **Value** field for the vendor command.

### -param Index [in]

Specifies the value of the **Index** field for the vendor command.

### -param Buffer [in, out, optional]

Pointer to a data buffer if the command has data. If the command does not have any data, this value is **NULL**.

### -param BufferLength [in, out]

Pointer to the buffer length value. Buffer length is expressed in bytes. If the value of *Buffer* is **NULL**, *BufferLength* may also be **NULL**.

### -param GetData [in]

*GetData* indicates data was sent from the device to the host.

### -param CommandComplete [in, optional]

Pointer to a camera minidriver defined [CommandCompleteFunction](./nc-usbcamdi-pcommand_complete_function.md), which is called when the bulk read or write is completed. This value can be **NULL**.

### -param CommandContext [in, optional]

Pointer to a block of memory, that is passed as an argument to the camera minidriver defined [CommandCompleteFunction](./nc-usbcamdi-pcommand_complete_function.md).

## -returns

**USBCAMD_ControlVendorCommand** returns the NTSTATUS code from vendor command.

Other possible error codes include:

| Return code | Description |
|---|---|
| **STATUS_PENDING** | The vendor command is deferred. |
| **STATUS_INSUFFICIENT_RESOURCES** | There are insufficient resources to allocate the vendor command. |

## -remarks

This function may be called at IRQL >= PASSIVE_LEVEL. If the function is called at IRQL > PASSIVE_LEVEL, the command is deferred. After completion, the camera minidriver defined [CommandCompleteFunction](./nc-usbcamdi-pcommand_complete_function.md) is called and passed the value in the *CommandContext* argument*.*

## -see-also

[CommandCompleteFunction](./nc-usbcamdi-pcommand_complete_function.md)