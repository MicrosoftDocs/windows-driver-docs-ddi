---
UID: NS:hbapiwmi._HBAFCPBindingEntry2
title: _HBAFCPBindingEntry2 (hbapiwmi.h)
description: The HBAFCPBindingEntry2 structure defines a binding between the information that uniquely identifies a logical unit for the operating system and the fibre channel protocol (FCP) identifier for the logical unit.
old-location: storage\hbafcpbindingentry2.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["HBAFCPBindingEntry2 structure"]
ms.keywords: "*PHBAFCPBindingEntry2, HBAFCPBindingEntry2, HBAFCPBindingEntry2 structure [Storage Devices], PHBAFCPBindingEntry2, PHBAFCPBindingEntry2 structure pointer [Storage Devices], _HBAFCPBindingEntry2, hbapiwmi/HBAFCPBindingEntry2, hbapiwmi/PHBAFCPBindingEntry2, storage.hbafcpbindingentry2, structs-Fibre_b15c2291-b1fc-4f4f-9890-ddf50e3dee9e.xml"
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h, Hbaapi.h, Hbaapi.h
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
req.typenames: HBAFCPBindingEntry2, *PHBAFCPBindingEntry2
f1_keywords:
 - _HBAFCPBindingEntry2
 - hbapiwmi/_HBAFCPBindingEntry2
 - PHBAFCPBindingEntry2
 - hbapiwmi/PHBAFCPBindingEntry2
 - HBAFCPBindingEntry2
 - hbapiwmi/HBAFCPBindingEntry2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Hbapiwmi.h
api_name:
 - HBAFCPBindingEntry2
---

# _HBAFCPBindingEntry2 structure


## -description

The HBAFCPBindingEntry2 structure defines a binding between the information that uniquely identifies a logical unit for the operating system and the fibre channel protocol (FCP) identifier for the logical unit.

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
Indicates that the target is identified by its fibre channel protocol (FCP) ID. The <b>Fcid</b> member of the <a href="/windows-hardware/drivers/ddi/hbapiwmi/ns-hbapiwmi-_hbafcpid">HBAFCPID</a> structure contains this value.

</td>
</tr>
<tr>
<td>
HBA_BIND_TO_WWPN

</td>
<td>
Indicates that the target is identified by its worldwide port name. The <b>PortWWN</b> member of the <a href="/windows-hardware/drivers/ddi/hbapiwmi/ns-hbapiwmi-_hbafcpid">HBAFCPID</a> structure contains this value.

</td>
</tr>
<tr>
<td>
HBA_BIND_TO_WWNN

</td>
<td>
Indicates that the fibre channel target device is identified by its worldwide node name. The <b>NodeWWN</b> member of the <a href="/windows-hardware/drivers/ddi/hbapiwmi/ns-hbapiwmi-_hbafcpid">HBAFCPID</a> structure contains this value.

</td>
</tr>
<tr>
<td>
HBA_BIND_TO_LUID

</td>
<td>
Indicates that the target is identified by its fibre channel logical unit ID. The <b>FcpLun</b> member of the <a href="/windows-hardware/drivers/ddi/hbapiwmi/ns-hbapiwmi-_hbafcpid">HBAFCPID</a> structure contains this value.

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

Contains a structure of type <a href="/windows-hardware/drivers/ddi/hbapiwmi/ns-hbapiwmi-_hbafcpid">HBAFCPID</a> that contains the FCP identifier for the logical unit and information about the port to be queried for information about the device.

### -field Luid

### -field ScsiId

Contains a structure of type <a href="/windows-hardware/drivers/ddi/hbapiwmi/ns-hbapiwmi-_hbascsiid">HBAScsiID</a> that contains the information that uniquely identifies a logical unit for the operating system.


#### - Luid[256]

Contains the logical unit descriptor for the device that the operating system derives from SCSI inquiry data.

## -remarks

This structure is very similar to the <a href="/windows-hardware/drivers/ddi/hbapiwmi/ns-hbapiwmi-_hbafcpbindingentry">HBAFCPBindingEntry</a> structure. The only difference is that HBAFCPBindingEntry2 includes the number that the operating system generates for the logical unit. 

The WMI tool suite generates a declaration of HBAFCPBindingEntry2 automatically when it compiles the <a href="/windows-hardware/drivers/storage/hbafcpbindingentry-wmi-class">HBAFCPBindingEntry WMI Class</a> that is defined in <i>hbaapi.mof</i>. 

For an explanation of the fibre channel protocol (FCP), see the T11 committee's <i>dpANS Fibre Channel Protocol for SCSI</i> specification.

## -see-also

<a href="/windows-hardware/drivers/ddi/hbapiwmi/ns-hbapiwmi-_hbafcpbindingentry">HBAFCPBindingEntry</a>



<a href="/windows-hardware/drivers/storage/hbafcpbindingentry2-wmi-class">HBAFCPBindingEntry2 WMI Class</a>
