---
UID: NS:ntddsd._SDBUS_REQUEST_PACKET
tech.root: sd
title: SDBUS_REQUEST_PACKET
ms.date: 11/02/2022
targetos: Windows
description: Learn more about the SDBUS_REQUEST_PACKET structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntddsd.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: SDBUS_REQUEST_PACKET, *PSDBUS_REQUEST_PACKET
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddsd.h
api_name:
 - _SDBUS_REQUEST_PACKET
 - PSDBUS_REQUEST_PACKET
 - SDBUS_REQUEST_PACKET
f1_keywords:
 - _SDBUS_REQUEST_PACKET
 - ntddsd/_SDBUS_REQUEST_PACKET
 - PSDBUS_REQUEST_PACKET
 - ntddsd/PSDBUS_REQUEST_PACKET
 - SDBUS_REQUEST_PACKET
 - ntddsd/SDBUS_REQUEST_PACKET
dev_langs:
 - c++
helpviewer_keywords:
 - _SDBUS_REQUEST_PACKET
---

## -description

The SDBUS\_REQUEST\_PACKET structure specifies the parameters for the individual requests and commands that the [**SdBusSubmitRequest**](nf-ntddsd-sdbussubmitrequest.md) routine sends to the bus driver.

## -struct-fields

### -field RequestFunction

Contains an enumeration value of type [**SD\_REQUEST\_FUNCTION**](ne-ntddsd-sd_request_function.md) that specifies the parameters for the operation and how they are interpreted.

### -field UserContext[3]

Contains a buffer area for optional use by the caller. The bus driver does not use this member.

### -field Information

Contains the status of the request on output.

### -field ResponseData

### -field ResponseData.AsUCHAR[16]

Contains a maximum of 16 bytes of response data on output. For more information about the response data, see the *Secure Digital (SD)* specification.

### -field ResponseData.AsULONG[4]

Contains a maximum of 16 bytes of response data on output. For more information about the response data, see the *Secure Digital (SD)* specification.

### -field ResponseData.Type3

### -field ResponseLength

Indicates the length, in bytes, of the response data.

### -field Reserved

### -field Flags

### -field Parameters

### -field Parameters.GetSetProperty

### -field Parameters.GetSetProperty.Property

Contains an enumeration value of type [**SDBUS\_PROPERTY**](ne-ntddsd-sdbus_property.md) that specifies the property to read or change.

### -field Parameters.GetSetProperty.Buffer

Contains the property data to write in operations that set a property. Contains the data read from the property in operations that retrieve the data associated with a property.

### -field Parameters.GetSetProperty.Length

Indicates the length, in bytes, of the response data.

### -field Parameters.DeviceCommand

### -field Parameters.DeviceCommand.CmdDesc

Contains a structure of type [**SDCMD\_DESCRIPTOR**](../sddef/ns-sddef-_sdcmd_descriptor.md) that defines an SD card command.

### -field Parameters.DeviceCommand.Argument

Contains 4 bytes of argument information that accompanies the command.

### -field Parameters.DeviceCommand.Mdl

Pointer to an MDL that holds the command data.

### -field Parameters.DeviceCommand.Length

Indicates the length, in bytes, of the response data.

### -field Parameters.EraseCommand

### -field Parameters.EraseCommand.EraseType

### -field Parameters.EraseCommand.StartBlock

### -field Parameters.EraseCommand.EndBlock

### -field Parameters.MmcSoftReset

### -field Parameters.MmcSoftReset.Frequency

### -field Parameters.MmcHpi

### -field Parameters.MmcHpi.IrpToHpi

## -remarks

If the request reads or sets a property on an SD device, a device driver must complete the following steps:

1. Set the **RequestFunction** member of SDBUS\_REQUEST\_PACKET to an [**SD\_REQUEST\_FUNCTION**](ne-ntddsd-sd_request_function.md) enumeration value of either SDRF\_GET\_PROPERTY or SDRF\_SET\_PROPERTY.

1. Set the **Property** member of SDBUS\_REQUEST\_PACKET to the SDBUS\_PROPERTY enumeration value that specifies the property to read or change.

1. Send the request to the bus driver by passing the initialized SDBUS\_REQUEST\_PACKET structure to either [**SdBusSubmitRequest**](nf-ntddsd-sdbussubmitrequest.md) or [**SdBusSubmitRequestAsync**](nf-ntddsd-sdbussubmitrequestasync.md).

If the request sends a command to an SD device, a device driver must complete the following steps:

1. Set the **RequestFunction** member of SDBUS\_REQUEST\_PACKET to an [**SD\_REQUEST\_FUNCTION**](ne-ntddsd-sd_request_function.md) enumeration value of SDRF\_DEVICE\_COMMAND.

1. Initialize the **CmdDesc** member of SDBUS\_REQUEST\_PACKET to define the command.

1. Send the request to the bus driver by passing the initialized SDBUS\_REQUEST\_PACKET structure to either [**SdBusSubmitRequest**](nf-ntddsd-sdbussubmitrequest.md) or [**SdBusSubmitRequestAsync**](nf-ntddsd-sdbussubmitrequestasync.md).

To do property operations, the driver must initialize the **GetSetProperty.Property**, **GetSetProperty.Buffer**, and **GetSetProperty.Length** members of the SDBUS\_REQUEST\_PACKET structure before submitting the request.

To send a command, the driver must initialize the **DeviceCommand.CmdDesc**, **DeviceCommand.Argument**, **DeviceCommand.Mdl**, and **DeviceCommand.Length** members of the SDBUS\_REQUEST\_PACKET structure before submitting the request.

## -see-also

[**SD\_REQUEST\_FUNCTION**](ne-ntddsd-sd_request_function.md)

[**SDBUS\_PROPERTY**](ne-ntddsd-sdbus_property.md)

[**SdBusSubmitRequest**](nf-ntddsd-sdbussubmitrequest.md)

[**SdBusSubmitRequestAsync**](nf-ntddsd-sdbussubmitrequestasync.md)

[**SDCMD\_DESCRIPTOR**](../sddef/ns-sddef-_sdcmd_descriptor.md)
