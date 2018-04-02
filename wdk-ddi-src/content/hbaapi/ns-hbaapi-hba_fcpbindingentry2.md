---
UID: NS:hbaapi.HBA_FCPBindingEntry2
title: HBA_FCPBindingEntry2
author: windows-driver-content
description: The HBA_FCPBindingEntry2 structure defines a binding between the information that uniquely identifies a logical unit for the operating system and the fibre channel protocol (FCP) identifier for the logical unit.
old-location: storage\hba_fcpbindingentry2.htm
old-project: storage
ms.assetid: e2e7353d-2c83-4704-bec4-9485ab3c7706
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PHBA_FCPBINDINGENTRY2, HBA_FCPBINDINGENTRY2, HBA_FCPBINDINGENTRY2 structure [Storage Devices], HBA_FCPBindingEntry2, HBA_FCPBindingEntry2 structure [Storage Devices], PHBA_FCPBINDINGENTRY2, PHBA_FCPBINDINGENTRY2 structure pointer [Storage Devices], hbaapi/HBA_FCPBindingEntry2, hbaapi/PHBA_FCPBINDINGENTRY2, storage.hba_fcpbindingentry2, structs-Fibre_168ea26c-34d1-4843-8464-528dc53e3953.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbaapi.h
req.include-header: Hbaapi.h
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
-	hbaapi.h
api_name:
-	HBA_FCPBINDINGENTRY2
product: Windows
targetos: Windows
req.typenames: HBA_FCPBINDINGENTRY2, *PHBA_FCPBINDINGENTRY2
---

# HBA_FCPBindingEntry2 structure


## -description


The HBA_FCPBindingEntry2 structure defines a binding between the information that uniquely identifies a logical unit for the operating system and the fibre channel protocol (FCP) identifier for the logical unit.


## -struct-fields




### -field type

Contains a binding type that indicates how the target is specified in the binding. This member can have any of the following values: 

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
Indicates that the target is identified by its fibre channel protocol (FCP) ID. The <b>Fcid</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556062">HBA_FcpId</a> structure contains this value.

</td>
</tr>
<tr>
<td>
HBA_BIND_TO_WWPN

</td>
<td>
Indicates that the target is identified by its worldwide port name. The <b>PortWWN</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556062">HBA_FcpId</a> structure contains this value.

</td>
</tr>
<tr>
<td>
HBA_BIND_TO_WWNN

</td>
<td>
Indicates that the fibre channel target device is identified by its worldwide node name. The <b>NodeWWN</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556062">HBA_FcpId</a> structure contains this value.

</td>
</tr>
<tr>
<td>
HBA_BIND_TO_LUID

</td>
<td>
Indicates that the target is identified by its fibre channel logical unit ID. The <b>FcpLun</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556062">HBA_FcpId</a> structure contains this value.

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
 

For a comparable set of values that define how an HBA specifies targets and logical units in the persistent bindings that it maintains, see the WMI property qualifier <a href="https://msdn.microsoft.com/library/windows/hardware/ff556046">HBA_BIND_TYPE</a>. 

For a more detailed description of the values that this member can have, see the T11 committee's <i>Fibre Channel HBA API</i> specification. 


### -field ScsiId

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557191">HBA_ScsiId</a> that contains the information that uniquely identifies a logical unit for the operating system.


### -field FcpId

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff556062">HBA_FcpId</a> that contains the FCP identifier for the logical unit and information about the port to be queried for information about the device.


### -field LUID

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557091">HBA_LUID</a> that holds a logical unit descriptor for the device that the operating system derives from SCSI inquiry data. 


### -field Status

Contains, on return, a status value that indicates the condition of the HBA. The status values that can be returned in this member correspond to the values associated with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> WMI property qualifier. 


## -remarks



This structure is very similar to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556035">HBAFCPBindingEntry2</a> structure. The only difference is that HBA_FCPBindingEntry2 returns HBA status. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556034">HBAFCPBindingEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556035">HBAFCPBindingEntry2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556046">HBA_BIND_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556058">HBA_FCPBindingEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556062">HBA_FcpId</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557091">HBA_LUID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557191">HBA_ScsiId</a>
 

 

