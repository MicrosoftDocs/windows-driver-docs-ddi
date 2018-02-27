---
UID: NS:61883._GET_UNIT_CAPABILITIES
title: "_GET_UNIT_CAPABILITIES"
author: windows-driver-content
description: The GET_UNIT_CAPABILITIES structure is used in conjunction with the Av61883_GetUnitInfo request to retrieve unit information about a device's capabilities.
old-location: ieee\get_unit_capabilities.htm
old-project: IEEE
ms.assetid: 7fe180c2-cf0b-4658-86e3-fed5e270db8c
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PGET_UNIT_CAPABILITIES, 61883/GET_UNIT_CAPABILITIES, 61883/PGET_UNIT_CAPABILITIES, 61883_structures_d0aac9e5-5600-4552-b06a-7526e6c87336.xml, GET_UNIT_CAPABILITIES, GET_UNIT_CAPABILITIES structure [Buses], IEEE.get_unit_capabilities, PGET_UNIT_CAPABILITIES, PGET_UNIT_CAPABILITIES structure pointer [Buses], _GET_UNIT_CAPABILITIES"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 61883.h
req.include-header: 61883.h
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
-	61883.h
apiname:
-	GET_UNIT_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: GET_UNIT_CAPABILITIES, *PGET_UNIT_CAPABILITIES
---

# _GET_UNIT_CAPABILITIES structure


## -description


The GET_UNIT_CAPABILITIES structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536983">Av61883_GetUnitInfo</a> request to retrieve unit information about a device's capabilities. 


## -syntax


````
typedef struct _GET_UNIT_CAPABILITIES {
  ULONG NumOutputPlugs;
  ULONG NumInputPlugs;
  ULONG MaxDataRate;
  ULONG CTSFlags;
  ULONG HardwareFlags;
} GET_UNIT_CAPABILITIES, *PGET_UNIT_CAPABILITIES;
````


## -struct-fields




### -field NumOutputPlugs

The number of output plugs supported by the device.


### -field NumInputPlugs

The number of input plugs supported by the device.


### -field MaxDataRate

The maximum data rate of the device. Can be one of the following:

CMP_SPEED_S100

CMP_SPEED_S200

CMP_SPEED_S400


### -field CTSFlags

A bitmask that identifies the command and transaction sets supported by the device. For example, if <b>CTSFlags</b> is 0001, the device supports Audio Video Control (AV/C). If <b>CTSFlags</b> is 4000, the device supports a vendor-unique CTS. Most devices that support multiple command and transaction sets report each CTS value in a separate Configuration ROM unit directory entry, so typically only one bit is set at a time.


### -field HardwareFlags

If the AV_HOST_DMA_DOUBLE_BUFFERING_ENABLED flag is set, and the request level is SET_UNIT_INFO_ISOCH_PARAMS, then a size limit is imposed on members <b>RX_NumPackets</b> and <b>TX_NumPackets</b> of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff538921">UNIT_ISOCH_PARAMS</a> structure. These members, when multiplied by the packet size, must be less than or equal to 64 KB. For example, <b>Rx_NumPackets * PacketSize </b>must be less than or equal to 64 KB. 


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536983">Av61883_GetUnitInfo</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20GET_UNIT_CAPABILITIES structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

