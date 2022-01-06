---
UID: NS:sddef._SDCMD_DESCRIPTOR
title: SDCMD_DESCRIPTOR (sddef.h)
description: The SDCMD_DESCRIPTOR structure defines a Secure Digital (SD) card command.
old-location: sd\sdcmd_descriptor.htm
tech.root: SD
ms.date: 12/16/2021
keywords: ["SDCMD_DESCRIPTOR structure"]
ms.keywords: "*PSDCMD_DESCRIPTOR, PSDCMD_DESCRIPTOR, PSDCMD_DESCRIPTOR structure pointer [Buses], SD.sdcmd_descriptor, SDCMD_DESCRIPTOR, SDCMD_DESCRIPTOR structure [Buses], _SDCMD_DESCRIPTOR, sd-structs_20a7faa8-4e91-49cc-94eb-13bd584a25a3.xml, sddef/PSDCMD_DESCRIPTOR, sddef/SDCMD_DESCRIPTOR"
req.header: sddef.h
req.include-header: Sddef.h
req.target-type: Windows
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
req.typenames: SDCMD_DESCRIPTOR, *PSDCMD_DESCRIPTOR
f1_keywords:
 - _SDCMD_DESCRIPTOR
 - sddef/_SDCMD_DESCRIPTOR
 - PSDCMD_DESCRIPTOR
 - sddef/PSDCMD_DESCRIPTOR
 - SDCMD_DESCRIPTOR
 - sddef/SDCMD_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - sddef.h
api_name:
 - _SDCMD_DESCRIPTOR
 - PSDCMD_DESCRIPTOR
 - SDCMD_DESCRIPTOR
---

# SDCMD_DESCRIPTOR structure

## -description

The **SDCMD_DESCRIPTOR** structure defines a Secure Digital (SD) card command.

## -struct-fields

### -field Cmd

Contains a value of type SD_COMMAND_CODE that specifies the SD command. **Cmd** can be one of the following values.

| Value | Meaning |
| ----- | ------- |
| SDCMD_IO_RW_DIRECT   | Indicates a read or write operation of a single byte.      |
| SDCMD_IO_RW_EXTENDED | Indicates a read or write operation on a buffer in memory. |

### -field CmdClass

Contains an enumeration value of type [**SD_COMMAND_CLASS**](ne-sddef-sd_command_class.md) that specifies the class of the SD command.

### -field TransferDirection

Contains an enumeration value of type [**SD_TRANSFER_DIRECTION**](ne-sddef-sd_transfer_direction.md) that indicates the direction of the data transfer.

### -field TransferType

Contains an enumeration value of type [**SD_TRANSFER_TYPE**](ne-sddef-sd_transfer_type.md) that indicates the type of the data transfer.

### -field ResponseType

Contains an enumeration value of type [**SD_RESPONSE_TYPE**](ne-sddef-sd_response_type.md) that indicates the type of response that the card sends in response to the command indicated in the **Cmd** member.

## -remarks

To send a command to an SD device, a device driver must complete the following steps:

1. Set the **RequestFunction** member of SDBUS_REQUEST_PACKET to an [**SD_REQUEST_FUNCTION**](../ntddsd/ne-ntddsd-sd_request_function.md) enumeration value of SDRF_DEVICE_COMMAND.

2. Initialize the **CmdDesc** member of SDBUS_REQUEST_PACKET to define the command.

3. Send the request to the bus driver by passing the initialized SDBUS_REQUEST_PACKET structure to either [**SdBusSubmitRequest**](../ntddsd/nf-ntddsd-sdbussubmitrequest.md) or [**SdBusSubmitRequestAsync**](../ntddsd/nf-ntddsd-sdbussubmitrequestasync.md).

If a driver submits a command request without properly initializing the **TransferDirection**, **TransferType**, and **ResponseType** members of the command descriptor, the request will fail. These members cannot be 0.

## -see-also

[**SD_COMMAND_CLASS**](ne-sddef-sd_command_class.md)

[**SD_REQUEST_FUNCTION**](../ntddsd/ne-ntddsd-sd_request_function.md)

[**SD_RESPONSE_TYPE**](ne-sddef-sd_response_type.md)

[**SD_TRANSFER_DIRECTION**](ne-sddef-sd_transfer_direction.md)

[**SD_TRANSFER_TYPE**](ne-sddef-sd_transfer_type.md)

[**SdBusSubmitRequest**](../ntddsd/nf-ntddsd-sdbussubmitrequest.md)

[**SdBusSubmitRequestAsync**](../ntddsd/nf-ntddsd-sdbussubmitrequestasync.md)
