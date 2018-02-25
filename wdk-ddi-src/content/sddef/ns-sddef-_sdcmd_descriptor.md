---
UID: NS:sddef._SDCMD_DESCRIPTOR
title: "_SDCMD_DESCRIPTOR"
author: windows-driver-content
description: The SDCMD_DESCRIPTOR structure defines a Secure Digital (SD) card command.
old-location: sd\sdcmd_descriptor.htm
old-project: SD
ms.assetid: 7c49c394-d0b3-4594-a623-0a13825bdcec
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: ",  , *, *PSDCMD_DESCRIPTOR, ,, C, D, E, I, M, O, P, PSDCMD_DESCRIPTOR, PSDCMD_DESCRIPTOR structure pointer [Buses], R, S, SD.sdcmd_descriptor, SDCMD_DESCRIPTOR, SDCMD_DESCRIPTOR structure [Buses], T, _, _SDCMD_DESCRIPTOR, sd-structs_20a7faa8-4e91-49cc-94eb-13bd584a25a3.xml, sddef/PSDCMD_DESCRIPTOR, sddef/SDCMD_DESCRIPTOR"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	sddef.h
apiname:
-	SDCMD_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: SDCMD_DESCRIPTOR, *PSDCMD_DESCRIPTOR
req.product: Windows 10 or later.
---

# _SDCMD_DESCRIPTOR structure


## -description


The SDCMD_DESCRIPTOR structure defines a Secure Digital (SD) card command.


## -syntax


````
typedef struct _SDCMD_DESCRIPTOR {
  SD_COMMAND_CODE       Cmd;
  SD_COMMAND_CLASS      CmdClass;
  SD_TRANSFER_DIRECTION TransferDirection;
  SD_TRANSFER_TYPE      TransferType;
  SD_RESPONSE_TYPE      ResponseType;
} SDCMD_DESCRIPTOR, *PSDCMD_DESCRIPTOR;
````


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

Contains an enumeration value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff538003">SD_COMMAND_CLASS</a>


that specifies the class of the SD command.


### -field TransferDirection

Contains an enumeration value of type <a href="https://msdn.microsoft.com/1e821ca5-ff65-48a1-be5c-6d776c61f166">SD_TRANSFER_DIRECTION</a> that indicates the direction of the data transfer.


### -field TransferType

Contains an enumeration value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff538045">SD_TRANSFER_TYPE</a> that indicates the type of the data transfer.


### -field ResponseType

Contains an enumeration value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff538025">SD_RESPONSE_TYPE</a> that indicates the type of response that the card sends in response to the command indicated in the <b>Cmd</b> member.


## -remarks



To send a command to an SD device, a device driver must complete the following steps:

<ol>
<li>
Set the <b>RequestFunction</b> member of SDBUS_REQUEST_PACKET to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff538012">SD_REQUEST_FUNCTION</a> enumeration value of SDRF_DEVICE_COMMAND.

</li>
<li>
Initialize the <b>CmdDesc</b> member of SDBUS_REQUEST_PACKET to define the command.

</li>
<li>
Send the request to the bus driver by passing the initialized SDBUS_REQUEST_PACKET structure to either <a href="https://msdn.microsoft.com/library/windows/hardware/ff537909">SdBusSubmitRequest</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff537914">SdBusSubmitRequestAsync</a>.

</li>
</ol>
If a driver submits a command request without properly initializing the <b>TransferDirection</b>, <b>TransferType</b>, and <b>ResponseType</b> members of the command descriptor, the request will fail. These members cannot be 0.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537914">SdBusSubmitRequestAsync</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538003">SD_COMMAND_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537909">SdBusSubmitRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538012">SD_REQUEST_FUNCTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538045">SD_TRANSFER_TYPE</a>



<a href="https://msdn.microsoft.com/1e821ca5-ff65-48a1-be5c-6d776c61f166">SD_TRANSFER_DIRECTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538025">SD_RESPONSE_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538008">SD_COMMAND_CODE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SD\buses]:%20SDCMD_DESCRIPTOR structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

