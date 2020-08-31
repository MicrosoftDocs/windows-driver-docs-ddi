---
UID: NS:hidclass._HID_XFER_PACKET
title: _HID_XFER_PACKET (hidclass.h)
description: The HID_XFER_PACKET structure contains information about a HID report that the HID class driver uses with I/O requests to get or set a report.
old-location: hid\hid_xfer_packet.htm
tech.root: hid
ms.assetid: b256e6fd-d44f-482a-836d-a812634b4b3a
ms.date: 04/30/2018
keywords: ["HID_XFER_PACKET structure"]
ms.keywords: "*PHID_XFER_PACKET, HID_XFER_PACKET, HID_XFER_PACKET structure [Human Input Devices], PHID_XFER_PACKET, PHID_XFER_PACKET structure pointer [Human Input Devices], _HID_XFER_PACKET, hid.hid_xfer_packet, hidclass/HID_XFER_PACKET, hidclass/PHID_XFER_PACKET, hidstrct_55f22385-a5ed-46b5-9f97-9d47ee731145.xml"
req.header: hidclass.h
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
targetos: Windows
req.typenames: HID_XFER_PACKET, *PHID_XFER_PACKET
f1_keywords:
 - _HID_XFER_PACKET
 - hidclass/_HID_XFER_PACKET
 - PHID_XFER_PACKET
 - hidclass/PHID_XFER_PACKET
 - HID_XFER_PACKET
 - hidclass/HID_XFER_PACKET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hidclass.h
api_name:
 - HID_XFER_PACKET
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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_feature">IOCTL_HID_GET_FEATURE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_input_report">IOCTL_HID_GET_INPUT_REPORT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_set_feature">IOCTL_HID_SET_FEATURE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_set_output_report">IOCTL_HID_SET_OUTPUT_REPORT</a>

