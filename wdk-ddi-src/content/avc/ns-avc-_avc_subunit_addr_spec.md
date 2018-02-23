---
UID: NS:avc._AVC_SUBUNIT_ADDR_SPEC
title: "_AVC_SUBUNIT_ADDR_SPEC"
author: windows-driver-content
description: The AVC_SUBUNIT_ADDR_SPEC structure is used with virtual instances of avc.sys to describe virtual subunit addresses.
old-location: stream\avc_subunit_addr_spec.htm
old-project: stream
ms.assetid: fa9fedc5-cacc-409a-99f5-7103b5424b3c
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: "*PAVC_SUBUNIT_ADDR_SPEC, AVC_SUBUNIT_ADDR_SPEC structure [Streaming Media Devices], avc/PAVC_SUBUNIT_ADDR_SPEC, _AVC_SUBUNIT_ADDR_SPEC, AVC_SUBUNIT_ADDR_SPEC, avcref_56141f06-dd51-40cb-874a-ec136ec7683f.xml, stream.avc_subunit_addr_spec, PAVC_SUBUNIT_ADDR_SPEC structure pointer [Streaming Media Devices], PAVC_SUBUNIT_ADDR_SPEC, avc/AVC_SUBUNIT_ADDR_SPEC"
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	avc.h
apiname:
-	AVC_SUBUNIT_ADDR_SPEC
product: Windows
targetos: Windows
req.typenames: AVC_SUBUNIT_ADDR_SPEC, *PAVC_SUBUNIT_ADDR_SPEC
---

# _AVC_SUBUNIT_ADDR_SPEC structure


## -description


The AVC_SUBUNIT_ADDR_SPEC structure is used with virtual instances of <i>avc.sys</i> to describe virtual subunit addresses.


## -syntax


````
typedef struct _AVC_SUBUNIT_ADDR_SPEC {
  ULONG Flags;
  UCHAR SubunitAddress[1];
} AVC_SUBUNIT_ADDR_SPEC, *PAVC_SUBUNIT_ADDR_SPEC;
````


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

A Subunit Address encoded according to Section 5.3.3 of the AV/C Digital Interface Command Set General Specification, Rev 3.0. This specification can be found at the <a href="http://go.microsoft.com/fwlink/p/?linkid=8728">1394 Trade Association</a> website. The ID part (<b>SubunitAddress</b>[0] &amp; 0x7) represents the max ID (not the count of subunits), so to enumerate a single tuner subunit, you would specify 0x28 (0x5 &lt;&lt; 3). This struct supports extended subunit addresses (just allocate a bigger struct and pass the actual length with the IOCTL).


## -see-also

<a href="..\avc\ni-avc-ioctl_avc_bus_reset.md">IOCTL_AVC_BUS_RESET</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20AVC_SUBUNIT_ADDR_SPEC structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

