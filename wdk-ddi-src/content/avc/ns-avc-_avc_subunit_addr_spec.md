---
UID: NS:avc._AVC_SUBUNIT_ADDR_SPEC
title: "_AVC_SUBUNIT_ADDR_SPEC"
author: windows-driver-content
description: The AVC_SUBUNIT_ADDR_SPEC structure is used with virtual instances of avc.sys to describe virtual subunit addresses.
old-location: stream\avc_subunit_addr_spec.htm
tech.root: stream
ms.assetid: fa9fedc5-cacc-409a-99f5-7103b5424b3c
ms.date: 04/23/2018
ms.keywords: "*PAVC_SUBUNIT_ADDR_SPEC, AVC_SUBUNIT_ADDR_SPEC, AVC_SUBUNIT_ADDR_SPEC structure [Streaming Media Devices], PAVC_SUBUNIT_ADDR_SPEC, PAVC_SUBUNIT_ADDR_SPEC structure pointer [Streaming Media Devices], _AVC_SUBUNIT_ADDR_SPEC, avc/AVC_SUBUNIT_ADDR_SPEC, avc/PAVC_SUBUNIT_ADDR_SPEC, avcref_56141f06-dd51-40cb-874a-ec136ec7683f.xml, stream.avc_subunit_addr_spec"
ms.topic: struct
req.header: avc.h
req.include-header: Avc.h
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
-	avc.h
api_name:
-	AVC_SUBUNIT_ADDR_SPEC
product:
- Windows
targetos: Windows
req.typenames: AVC_SUBUNIT_ADDR_SPEC, *PAVC_SUBUNIT_ADDR_SPEC
---

# _AVC_SUBUNIT_ADDR_SPEC structure


## -description


The AVC_SUBUNIT_ADDR_SPEC structure is used with virtual instances of <i>avc.sys</i> to describe virtual subunit addresses.


## -struct-fields




### -field Flags

The flags extend the operation in the following ways:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
AVC_SUBUNIT_ADDR_PERSISTENT

</td>
<td>
Makes the change persistent (in the registry) so on reboot the virtual device instances are automatically enumerated.

</td>
</tr>
<tr>
<td>
AVC_SUBUNIT_ADDR_TRIGGERBUSRESET

</td>
<td>
Informs Device Manager that the PDO list has changed. This causes a 1394 bus reset, which notifies devices on the 1394 bus that the topology has changed. This flag is normally set, unless there are several different subunit types to enable at the same time. The IOCTL_AVC_BUS_RESET control code performs the equivalent bus reset operation.

</td>
</tr>
</table>
 


### -field SubunitAddress

A Subunit Address encoded according to Section 5.3.3 of the AV/C Digital Interface Command Set General Specification, Rev 3.0. This specification can be found at the <a href="https://go.microsoft.com/fwlink/p/?linkid=8728">1394 Trade Association</a> website. The ID part (<b>SubunitAddress</b>[0] &amp; 0x7) represents the max ID (not the count of subunits), so to enumerate a single tuner subunit, you would specify 0x28 (0x5 &lt;&lt; 3). This struct supports extended subunit addresses (just allocate a bigger struct and pass the actual length with the IOCTL).


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560783">IOCTL_AVC_BUS_RESET</a>
 

 


