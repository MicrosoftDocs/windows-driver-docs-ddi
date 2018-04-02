---
UID: NS:1394._BUS_RESET_DATA
title: "_BUS_RESET_DATA"
author: windows-driver-content
description: The BUS_RESET_DATA structure specifies the context for the extended bus reset notification routine.
old-location: ieee\bus_reset_data.htm
old-project: IEEE
ms.assetid: 82A01880-AC8D-4285-A780-EE195F186B71
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PBUS_RESET_DATA, 1394/BUS_RESET_DATA, 1394/PBUS_RESET_DATA, BUS_RESET_DATA, BUS_RESET_DATA structure [Buses], IEEE.bus_reset_data, PBUS_RESET_DATA, PBUS_RESET_DATA structure pointer [Buses], _BUS_RESET_DATA"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 1394.h
req.include-header: 1394.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions.
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
-	HeaderDef
api_location:
-	1394.h
api_name:
-	BUS_RESET_DATA
product: Windows
targetos: Windows
req.typenames: BUS_RESET_DATA, *PBUS_RESET_DATA
---

# _BUS_RESET_DATA structure


## -description


The <b>BUS_RESET_DATA</b> structure specifies the context for the extended bus reset notification routine. 


## -struct-fields




### -field ResetContext

Pointer to a client driver-defined context when a bus reset occurs. The argument that is specified in the <b>u.BusResetNotification.ResetContext</b> parameter when the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537638">REQUEST_BUS_RESET_NOTIFICATION</a> request is sent.


### -field GenerationCount

The current generation of the 1394 bus.


### -field DeviceNodeId

The 1394 address for the device.


### -field LocalNodeId

The 1394 address for the local host.


### -field SpeedToNode

The negotiated speed to the device. The possible values are as follows:

<table>
<tr>
<th>Flag</th>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>SPEED_FLAGS_800</td>
<td>0x08</td>
<td>    800 Mb/s</td>
</tr>
<tr>
<td>SPEED_FLAGS_1600</td>
<td>0x10</td>
<td>160 Mb/s</td>
</tr>
<tr>
<td>SPEED_FLAGS_3200</td>
<td>0x20</td>
<td>3200 Mb/s</td>
</tr>
</table>
 


## -see-also




<a href="https://msdn.microsoft.com/5473C6AC-284C-41B1-AA67-75696BE96C24">Device Driver Interface (DDI) Changes in Windows 7</a>
 

 

