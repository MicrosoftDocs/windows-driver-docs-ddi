---
UID: NS:hbapiwmi._HBAFCPBindingEntry2
title: _HBAFCPBindingEntry2
author: windows-driver-content
description: The HBAFCPBindingEntry2 structure defines a binding between the information that uniquely identifies a logical unit for the operating system and the fibre channel protocol (FCP) identifier for the logical unit.
old-location: storage\hbafcpbindingentry2.htm
old-project: storage
ms.assetid: 75de51b1-063b-49b2-a390-2bafd44e04b0
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _HBAFCPBindingEntry2, HBAFCPBindingEntry2, *PHBAFCPBindingEntry2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h, Hbaapi.h, Hbaapi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HBAFCPBindingEntry2
req.alt-loc: Hbapiwmi.h
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
req.typenames: HBAFCPBindingEntry2, *PHBAFCPBindingEntry2
---

# _HBAFCPBindingEntry2 structure



## -description
The HBAFCPBindingEntry2 structure defines a binding between the information that uniquely identifies a logical unit for the operating system and the fibre channel protocol (FCP) identifier for the logical unit.



## -syntax

````
typedef struct _HBAFCPBindingEntry2 {
  ULONG     Type;
  HBAFCPID  FCPId;
  UCHAR     Luid[256];
  HBAScsiID ScsiId;
} HBAFCPBindingEntry2, *PHBAFCPBindingEntry2;
````


## -struct-fields

### -field Type

Indicates the binding type. For a description of the values that this member can have, see the T11 committee's <i>Fibre Channel HBA API</i> specification. 

<table>
<tr>
<th>Type Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
HBA_BIND_TO_D_ID

</td>
<td>
Indicates that the target is identified by its fibre channel protocol (FCP) ID. The <b>Fcid</b> member of the <a href="..\hbapiwmi\ns-hbapiwmi-_hbafcpid.md">HBAFCPID</a> structure contains this value.

</td>
</tr>
<tr>
<td>
HBA_BIND_TO_WWPN

</td>
<td>
Indicates that the target is identified by its worldwide port name. The <b>PortWWN</b> member of the <a href="..\hbapiwmi\ns-hbapiwmi-_hbafcpid.md">HBAFCPID</a> structure contains this value.

</td>
</tr>
<tr>
<td>
HBA_BIND_TO_WWNN

</td>
<td>
Indicates that the fibre channel target device is identified by its worldwide node name. The <b>NodeWWN</b> member of the <a href="..\hbapiwmi\ns-hbapiwmi-_hbafcpid.md">HBAFCPID</a> structure contains this value.

</td>
</tr>
<tr>
<td>
HBA_BIND_TO_LUID

</td>
<td>
Indicates that the target is identified by its fibre channel logical unit ID. The <b>FcpLun</b> member of the <a href="..\hbapiwmi\ns-hbapiwmi-_hbafcpid.md">HBAFCPID</a> structure contains this value.

</td>
</tr>
<tr>
<td>
HBA_BIND_TARGETS

</td>
<td>
Indicates that the system should automatically generate target mappings from logical unit numbers to fibre channel protocol identifiers. 

</td>
</tr>
</table>
 

For information about what needs to be included to use the symbols that represent the binding types, see the Headers section.


### -field FCPId

Contains a structure of type <a href="..\hbapiwmi\ns-hbapiwmi-_hbafcpid.md">HBAFCPID</a> that contains the FCP identifier for the logical unit and information about the port to be queried for information about the device.


### -field Luid[256]

Contains the logical unit descriptor for the device that the operating system derives from SCSI inquiry data. 


### -field ScsiId

Contains a structure of type <a href="..\hbapiwmi\ns-hbapiwmi-_hbascsiid.md">HBAScsiID</a> that contains the information that uniquely identifies a logical unit for the operating system.


## -remarks
This structure is very similar to the <a href="..\hbapiwmi\ns-hbapiwmi-_hbafcpbindingentry.md">HBAFCPBindingEntry</a> structure. The only difference is that HBAFCPBindingEntry2 includes the number that the operating system generates for the logical unit. 

The WMI tool suite generates a declaration of HBAFCPBindingEntry2 automatically when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556037">HBAFCPBindingEntry WMI Class</a> that is defined in <i>hbaapi.mof</i>. 

For an explanation of the fibre channel protocol (FCP), see the T11 committee's <i>dpANS Fibre Channel Protocol for SCSI</i> specification. 


## -see-also
<dl>
<dt>
<a href="..\hbapiwmi\ns-hbapiwmi-_hbafcpbindingentry.md">HBAFCPBindingEntry</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556036">HBAFCPBindingEntry2 WMI Class</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBAFCPBindingEntry2 structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

