---
UID: NS:ntddpcm._PCMCIA_SOCKET_INFORMATION
title: _PCMCIA_SOCKET_INFORMATION (ntddpcm.h)
description: The PCMCIA_SOCKET_INFORMATION structure is used in conjunction with the IOCTL_SOCKET_INFORMATION request to retrieve socket configuration and state data.
old-location: pcmcia\pcmcia_socket_information.htm
tech.root: PCMCIA
ms.assetid: 53881aca-e49c-43e9-b68e-b91a1868e3f5
ms.date: 02/15/2018
keywords: ["_PCMCIA_SOCKET_INFORMATION structure"]
ms.keywords: "*PPCMCIA_SOCKET_INFORMATION, PCMCIA.pcmcia_socket_information, PCMCIA_SOCKET_INFORMATION, PCMCIA_SOCKET_INFORMATION structure [Buses], PPCMCIA_SOCKET_INFORMATION, PPCMCIA_SOCKET_INFORMATION structure pointer [Buses], _PCMCIA_SOCKET_INFORMATION, memcdref_b118ae5c-5dc5-4919-809d-5cfe5b25598f.xml, ntddpcm/PCMCIA_SOCKET_INFORMATION, ntddpcm/PPCMCIA_SOCKET_INFORMATION"
f1_keywords:
 - "ntddpcm/PCMCIA_SOCKET_INFORMATION"
 - "PCMCIA_SOCKET_INFORMATION"
req.header: ntddpcm.h
req.include-header: Ntddpcm.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddpcm.h
api_name:
- PCMCIA_SOCKET_INFORMATION
targetos: Windows
req.typenames: PCMCIA_SOCKET_INFORMATION, *PPCMCIA_SOCKET_INFORMATION
---

# _PCMCIA_SOCKET_INFORMATION structure


## -description


The PCMCIA_SOCKET_INFORMATION structure is used in conjunction with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddpcm/ni-ntddpcm-ioctl_socket_information">IOCTL_SOCKET_INFORMATION</a> request to retrieve socket configuration and state data. 


## -struct-fields




### -field Socket

Indicates the socket number. 


### -field TupleCrc

Contains a 16-bit CRC that is concatenated with the PCMCIA prefix, the manufacturer-name string, the product-name string, and the instance value for the card to produce the device ID for a PC Card or CardBus card. For more information about PCMCIA device IDs, see <a href="https://docs.microsoft.com/windows-hardware/drivers/install/identifiers-for-pcmcia-devices">Identifiers for PCMCIA Devices</a>. 


### -field Manufacturer

Indicates the manufacturer of the PC Card or CardBus card. 


### -field Identifier

Contains the device ID of the PC Card or CardBus card. 


### -field DriverName

Contains the name of the PC Card or CardBus card device driver. 


### -field DeviceFunctionId

Indicates the type of PC Card or CardBus card. This value can be one of the following.

<table>
<tr>
<th>PC Card Type</th>
<th>Meaning</th>
</tr>
<tr>
<td>
PCCARD_TYPE_MULTIFUNCTION

</td>
<td>
Multifunction card.

</td>
</tr>
<tr>
<td>
PCCARD_TYPE_MEMORY

</td>
<td>
Memory card.

</td>
</tr>
<tr>
<td>
PCCARD_TYPE_SERIAL

</td>
<td>
Serial port card.

</td>
</tr>
<tr>
<td>
PCCARD_TYPE_PARALLEL

</td>
<td>
Parallel port card.

</td>
</tr>
<tr>
<td>
PCCARD_TYPE_ATA

</td>
<td>
Disk controller card. 

</td>
</tr>
<tr>
<td>
PCCARD_TYPE_VIDEO

</td>
<td>
Video controller card. 

</td>
</tr>
<tr>
<td>
PCCARD_TYPE_NETWORK

</td>
<td>
Network controller card. 

</td>
</tr>
<tr>
<td>
PCCARD_TYPE_AIMS

</td>
<td>
Auto-increment mass storage card. 

</td>
</tr>
<tr>
<td>
PCCARD_TYPE_SCSI_BRIDGE

</td>
<td>
SCSI bridge card. 

</td>
</tr>
<tr>
<td>
PCCARD_TYPE_SECURITY

</td>
<td>
Security card. 

</td>
</tr>
<tr>
<td>
PCCARD_TYPE_MULTIFUNCTION3

</td>
<td>
Multifunction 3.0 PC Card. 

</td>
</tr>
<tr>
<td>
PCCARD_TYPE_FLASH_MEMORY

</td>
<td>
Flash memory card. 

</td>
</tr>
<tr>
<td>
PCCARD_TYPE_MODEM

</td>
<td>
Modem card. 

</td>
</tr>
</table>
 


### -field Reserved

Reserved. 


### -field CardInSocket

Indicates that there is a card present in the socket. 


### -field CardEnabled

Indicates that the card is enabled. 


### -field ControllerType

Indicates the controller type. Some common controller types are defined in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddpcm/ne-ntddpcm-_pcmcia_controller_class">PCMCIA_CONTROLLER_CLASS</a> enumeration. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddpcm/ni-ntddpcm-ioctl_socket_information">IOCTL_SOCKET_INFORMATION</a>
 

 

