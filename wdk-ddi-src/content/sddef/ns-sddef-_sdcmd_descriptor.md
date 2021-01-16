---
UID: NS:sddef._SDCMD_DESCRIPTOR
title: _SDCMD_DESCRIPTOR (sddef.h)
description: The SDCMD_DESCRIPTOR structure defines a Secure Digital (SD) card command.
old-location: sd\sdcmd_descriptor.htm
tech.root: SD
ms.date: 02/15/2018
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

# _SDCMD_DESCRIPTOR structure


## -description

The SDCMD_DESCRIPTOR structure defines a Secure Digital (SD) card command.

## -struct-fields

### -field Cmd

Contains a value of type SD_COMMAND_CODE that specifies the SD command.

<ul>
<li>SDCMD_IO_RW_DIRECTIndicates a read or write operation of a single byte.

</li>
<li>SDCMD_IO_RW_EXTENDEDIndicates a read or write operation on a buffer in memory.

</li>
</ul>

### -field CmdClass

Contains an enumeration value of type <a href="/windows-hardware/drivers/ddi/sddef/ne-sddef-sd_command_class">SD_COMMAND_CLASS</a>


that specifies the class of the SD command.

### -field TransferDirection

Contains an enumeration value of type <a href="/previous-versions/windows/hardware/drivers/ff538037(v=vs.85)">SD_TRANSFER_DIRECTION</a> that indicates the direction of the data transfer.

### -field TransferType

Contains an enumeration value of type <a href="/windows-hardware/drivers/ddi/sddef/ne-sddef-sd_transfer_type">SD_TRANSFER_TYPE</a> that indicates the type of the data transfer.

### -field ResponseType

Contains an enumeration value of type <a href="/windows-hardware/drivers/ddi/sddef/ne-sddef-sd_response_type">SD_RESPONSE_TYPE</a> that indicates the type of response that the card sends in response to the command indicated in the <b>Cmd</b> member.

## -remarks

To send a command to an SD device, a device driver must complete the following steps:

<ol>
<li>
Set the <b>RequestFunction</b> member of SDBUS_REQUEST_PACKET to an <a href="/windows-hardware/drivers/ddi/ntddsd/ne-ntddsd-sd_request_function">SD_REQUEST_FUNCTION</a> enumeration value of SDRF_DEVICE_COMMAND.

</li>
<li>
Initialize the <b>CmdDesc</b> member of SDBUS_REQUEST_PACKET to define the command.

</li>
<li>
Send the request to the bus driver by passing the initialized SDBUS_REQUEST_PACKET structure to either <a href="/windows-hardware/drivers/ddi/ntddsd/nf-ntddsd-sdbussubmitrequest">SdBusSubmitRequest</a> or <a href="/windows-hardware/drivers/ddi/ntddsd/nf-ntddsd-sdbussubmitrequestasync">SdBusSubmitRequestAsync</a>.

</li>
</ol>
If a driver submits a command request without properly initializing the <b>TransferDirection</b>, <b>TransferType</b>, and <b>ResponseType</b> members of the command descriptor, the request will fail. These members cannot be 0.

## -see-also

<a href="/windows-hardware/drivers/ddi/sddef/ne-sddef-sd_command_class">SD_COMMAND_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538008">SD_COMMAND_CODE</a>



<a href="/windows-hardware/drivers/ddi/ntddsd/ne-ntddsd-sd_request_function">SD_REQUEST_FUNCTION</a>



<a href="/windows-hardware/drivers/ddi/sddef/ne-sddef-sd_response_type">SD_RESPONSE_TYPE</a>



<a href="/previous-versions/windows/hardware/drivers/ff538037(v=vs.85)">SD_TRANSFER_DIRECTION</a>



<a href="/windows-hardware/drivers/ddi/sddef/ne-sddef-sd_transfer_type">SD_TRANSFER_TYPE</a>



<a href="/windows-hardware/drivers/ddi/ntddsd/nf-ntddsd-sdbussubmitrequest">SdBusSubmitRequest</a>



<a href="/windows-hardware/drivers/ddi/ntddsd/nf-ntddsd-sdbussubmitrequestasync">SdBusSubmitRequestAsync</a>

