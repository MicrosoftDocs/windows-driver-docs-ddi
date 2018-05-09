---
UID: NS:vhf._HID_XFER_PACKET
title: "_HID_XFER_PACKET"
author: windows-driver-content
description: The HID_XFER_PACKET structure contains information about a HID report that the HID class driver uses with I/O requests to get or set a report.
old-location: hid\hid_xfer_packet.htm
old-project: hid
ms.assetid: b256e6fd-d44f-482a-836d-a812634b4b3a
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: "*PHID_XFER_PACKET, HID_XFER_PACKET, HID_XFER_PACKET structure [Human Input Devices], PHID_XFER_PACKET, PHID_XFER_PACKET structure pointer [Human Input Devices], _HID_XFER_PACKET, hid.hid_xfer_packet, hidclass/HID_XFER_PACKET, hidclass/PHID_XFER_PACKET, hidstrct_55f22385-a5ed-46b5-9f97-9d47ee731145.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: vhf.h
req.include-header: Hidport.h, Vhf.h
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
-	hidclass.h
api_name:
-	HID_XFER_PACKET
product:
- Windows
targetos: Windows
req.typenames: HID_XFER_PACKET, *PHID_XFER_PACKET
---

# _HID_XFER_PACKET structure


## -description


The HID_XFER_PACKET structure contains information about a HID report that the HID class driver uses with I/O requests to get or set a report.


## -struct-fields




### -field reportBuffer

Pointer to a report buffer.


### -field reportBufferLen

Specifies the length of the report at <b>reportBuffer</b>.


### -field reportId

Specifies the report ID of the report contained at <b>reportBuffer</b>. This parameter is optional, and, if not specified, should be set to zero.


## -remarks



The HID class driver uses this structure to specify information about a HID report when it uses an I/O request to get or set a report.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541100">IOCTL_HID_GET_FEATURE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541126">IOCTL_HID_GET_INPUT_REPORT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541176">IOCTL_HID_SET_FEATURE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541196">IOCTL_HID_SET_OUTPUT_REPORT</a>
 

 

