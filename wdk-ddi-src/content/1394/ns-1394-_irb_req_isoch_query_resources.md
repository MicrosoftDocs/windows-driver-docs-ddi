---
UID: NS:1394._IRB_REQ_ISOCH_QUERY_RESOURCES
title: "_IRB_REQ_ISOCH_QUERY_RESOURCES"
author: windows-driver-content
description: This structure contains the fields necessary to carry out a IsochQueryResources request.
old-location: ieee\irb_req_isoch_query_resources.htm
old-project: IEEE
ms.assetid: B9CDFB62-32CF-497A-BF0F-1E4FBCA36E82
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: 1394/IRB_REQ_ISOCH_QUERY_RESOURCES, IEEE.irb_req_isoch_query_resources, IRB_REQ_ISOCH_QUERY_RESOURCES, IRB_REQ_ISOCH_QUERY_RESOURCES structure [Buses], _IRB_REQ_ISOCH_QUERY_RESOURCES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 1394.h
req.include-header: 
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	1394.h
api_name:
-	IRB_REQ_ISOCH_QUERY_RESOURCES
product:
- Windows
targetos: Windows
req.typenames: IRB_REQ_ISOCH_QUERY_RESOURCES
---

# _IRB_REQ_ISOCH_QUERY_RESOURCES structure


## -description


This structure contains the fields necessary to carry out a IsochQueryResources request.


## -struct-fields




### -field fulSpeed

Specifies the speed flag to use in allocating bandwidth. The possible speed values are SPEED_FLAGS_xxx, where xxx is the approximate transfer rate in megabits per second. Existing hardware supports transfer rates of 100, 200, and 400 MBps.

<table>
<tr>
<th>Transfer Rate</th>
<th>Description</th>
</tr>
<tr>
<td>
SPEED_FLAGS_100

</td>
<td>
100 Mb/s

</td>
</tr>
<tr>
<td>
SPEED_FLAGS_200

</td>
<td>
200 Mb/s

</td>
</tr>
<tr>
<td>
SPEED_FLAGS_400

</td>
<td>
400 Mb/s

</td>
</tr>
</table>
 


### -field BytesPerFrameAvailable

On success, specifies the returned available bandwidth as expressed in bytes per isochronous frame. 


### -field ChannelsAvailable

On success, points to a bitmap of available channels.

 The highest order bit (bit 63) specifies channel 0, the next bit (bit 62) specifies channel 1, and so on.

