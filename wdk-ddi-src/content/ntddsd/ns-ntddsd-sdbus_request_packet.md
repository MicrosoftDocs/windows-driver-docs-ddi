---
UID: NS:ntddsd._SDBUS_REQUEST_PACKET
tech.root: sd
title: SDBUS_REQUEST_PACKET
ms.date: 11/08/2022
targetos: Windows
description: The SDBUS_REQUEST_PACKET structure specifies the parameters for the individual requests and commands that the SdBusSubmitRequest routine sends to the bus driver.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntddsd.h
req.include-header: Ntddsd.h
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

The **SDBUS_REQUEST_PACKET** structure specifies the parameters for the individual requests and commands that the [**SdBusSubmitRequest**](nf-ntddsd-sdbussubmitrequest.md) routine sends to the bus driver.

## -struct-fields

### -field RequestFunction

Contains an enumeration value of type [**SD_REQUEST_FUNCTION**](ne-ntddsd-sd_request_function.md) that specifies the parameters for the operation and how they are interpreted.

### -field UserContext[3]

Contains a buffer area for optional use by the caller. The bus driver does not use this member.

### -field Information

Contains the status of the request on output.

### -field ResponseData

Defines the **ResponseData** union.

### -field ResponseData.AsUCHAR[16]

Contains a maximum of 16 bytes of response data on output. For more information about the response data, see the *Secure Digital (SD)* specification.

### -field ResponseData.AsULONG[4]

Contains a maximum of 16 bytes of response data on output. For more information about the response data, see the *Secure Digital (SD)* specification.

### -field ResponseData.Type3

Defines the **SDRESP_TYPE3** member **Type3**.

### -field ResponseLength

Indicates the length, in bytes, of the response data.

### -field Reserved

Reserved, set to 0.

### -field Flags

Flags field for the SDRP.

### -field Parameters

Parameters to the individual functions.

### -field Parameters.GetSetProperty

The property functions allow the caller to control aspects of bus driver operation.

### -field Parameters.GetSetProperty.Property

Contains an enumeration value of type [**SDBUS_PROPERTY**](ne-ntddsd-sdbus_property.md) that specifies the property to read or change.

### -field Parameters.GetSetProperty.Buffer

Contains the property data to write in operations that set a property. Contains the data read from the property in operations that retrieve the data associated with a property.

### -field Parameters.GetSetProperty.Length

Indicates the length, in bytes, of the response data.

### -field Parameters.DeviceCommand

**DeviceCommand** is the 'pipe' that allows SD device codes and arguments to be executed. These codes are either defined in the *Secure Digital (SD)* specification, can be based per device class, or can also be proprietary.

### -field Parameters.DeviceCommand.CmdDesc

Contains a structure of type [**SDCMD_DESCRIPTOR**](../sddef/ns-sddef-_sdcmd_descriptor.md) that defines an SD card command.

### -field Parameters.DeviceCommand.Argument

Contains 4 bytes of argument information that accompanies the command.

### -field Parameters.DeviceCommand.Mdl

Pointer to an MDL that holds the command data.

### -field Parameters.DeviceCommand.Length

Indicates the length, in bytes, of the response data.

### -field Parameters.EraseCommand

**EraseCommand** allows MMC devices to send Erase commands to the given device in an atomic sequence, as three device commands need to be sent to Erase a given LBA range or group.

### -field Parameters.EraseCommand.EraseType

Defines the **SDBUS_ERASE_TYPE** member **EraseType**.

### -field Parameters.EraseCommand.StartBlock

Defines the **ULONG** member **StartBlock**.

### -field Parameters.EraseCommand.EndBlock

Defines the **ULONG** member **EndBlock**.

### -field Parameters.MmcSoftReset

**MmcSoftReset** allows eMMC devices to be soft reset for a SanDisk proprietary firmware update that resets the device to its manufactured state.

### -field Parameters.MmcSoftReset.Frequency

Defines the **ULONG** member **Frequency**.

### -field Parameters.MmcHpi

**MmcHpi** allows an HPI to be sent to the eMMC device which will cause sdbus to stop the currently executing SDRP with STATUS_SDBUS_IO_INTERRUPTED. The information field of the stopped SDRP will be filled out with the progress of the halted operation, so it may be resumed later at the correct offset.

### -field Parameters.MmcHpi.IrpToHpi

This is the IRP to HPI. This is checked by SDBUS to ensure it is going to HPI the right IRP.

## -remarks

If the request reads or sets a property on an SD device, a device driver must complete the following steps:

1. Set the **RequestFunction** member of **SDBUS_REQUEST_PACKET** to an [**SD_REQUEST_FUNCTION**](ne-ntddsd-sd_request_function.md) enumeration value of either SDRF_GET_PROPERTY or SDRF_SET_PROPERTY.

1. Set the **Property** member of **SDBUS_REQUEST_PACKET** to the **SDBUS_PROPERTY** enumeration value that specifies the property to read or change.

1. Send the request to the bus driver by passing the initialized **SDBUS_REQUEST_PACKET** structure to either [**SdBusSubmitRequest**](nf-ntddsd-sdbussubmitrequest.md) or [**SdBusSubmitRequestAsync**](nf-ntddsd-sdbussubmitrequestasync.md).

If the request sends a command to an SD device, a device driver must complete the following steps:

1. Set the **RequestFunction** member of **SDBUS_REQUEST_PACKET** to an [**SD_REQUEST_FUNCTION**](ne-ntddsd-sd_request_function.md) enumeration value of SDRF_DEVICE_COMMAND.

1. Initialize the **CmdDesc** member of **SDBUS_REQUEST_PACKET** to define the command.

1. Send the request to the bus driver by passing the initialized **SDBUS_REQUEST_PACKET** structure to either [**SdBusSubmitRequest**](nf-ntddsd-sdbussubmitrequest.md) or [**SdBusSubmitRequestAsync**](nf-ntddsd-sdbussubmitrequestasync.md).

To do property operations, the driver must initialize the **GetSetProperty.Property**, **GetSetProperty.Buffer**, and **GetSetProperty.Length** members of the **SDBUS_REQUEST_PACKET** structure before submitting the request.

To send a command, the driver must initialize the **DeviceCommand.CmdDesc**, **DeviceCommand.Argument**, **DeviceCommand.Mdl**, and **DeviceCommand.Length** members of the **SDBUS_REQUEST_PACKET** structure before submitting the request.

## -see-also

[**SD_REQUEST_FUNCTION**](ne-ntddsd-sd_request_function.md)

[**SDBUS_PROPERTY**](ne-ntddsd-sdbus_property.md)

[**SdBusSubmitRequest**](nf-ntddsd-sdbussubmitrequest.md)

[**SdBusSubmitRequestAsync**](nf-ntddsd-sdbussubmitrequestasync.md)

[**SDCMD_DESCRIPTOR**](../sddef/ns-sddef-_sdcmd_descriptor.md)
