---
UID: NS:hbaapi.HBA_FCPBindingEntry2
title: HBA_FCPBindingEntry2
author: windows-driver-content
description: The HBA_FCPBindingEntry2 structure defines a binding between the information that uniquely identifies a logical unit for the operating system and the fibre channel protocol (FCP) identifier for the logical unit.
old-location: storage\hba_fcpbindingentry2.htm
old-project: storage
ms.assetid: e2e7353d-2c83-4704-bec4-9485ab3c7706
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: structs-Fibre_168ea26c-34d1-4843-8464-528dc53e3953.xml, HBA_FCPBindingEntry2 structure [Storage Devices], hbaapi/HBA_FCPBindingEntry2, HBA_FCPBINDINGENTRY2, PHBA_FCPBINDINGENTRY2 structure pointer [Storage Devices], *PHBA_FCPBINDINGENTRY2, HBA_FCPBINDINGENTRY2 structure [Storage Devices], hbaapi/PHBA_FCPBINDINGENTRY2, HBA_FCPBindingEntry2, PHBA_FCPBINDINGENTRY2, storage.hba_fcpbindingentry2
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	hbaapi.h
apiname:
-	HBA_FCPBINDINGENTRY2
product: Windows
targetos: Windows
req.typenames: HBA_FCPBINDINGENTRY2, *PHBA_FCPBINDINGENTRY2
---

# HBA_FCPBindingEntry2 structure


## -description


The HBA_FCPBindingEntry2 structure defines a binding between the information that uniquely identifies a logical unit for the operating system and the fibre channel protocol (FCP) identifier for the logical unit.


## -syntax


````
typedef struct HBA_FCPBindingEntry2 {
  HBA_BIND_TYPE type;
  HBA_SCSIID    ScsiId;
  HBA_FCPID     FcpId;
  HBA_LUID      LUID;
  HBA_STATUS    Status;
} HBA_FCPBINDINGENTRY2, *PHBA_FCPBINDINGENTRY2;
````


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
Indicates that the target is identified by its fibre channel protocol (FCP) ID. The <b>Fcid</b> member of the <a href="..\hbaapi\ns-hbaapi-hba_fcpid.md">HBA_FcpId</a> structure contains this value.

</td>
</tr>
<tr>
<td>
HBA_BIND_TO_WWPN

</td>
<td>
Indicates that the target is identified by its worldwide port name. The <b>PortWWN</b> member of the <a href="..\hbaapi\ns-hbaapi-hba_fcpid.md">HBA_FcpId</a> structure contains this value.

</td>
</tr>
<tr>
<td>
HBA_BIND_TO_WWNN

</td>
<td>
Indicates that the fibre channel target device is identified by its worldwide node name. The <b>NodeWWN</b> member of the <a href="..\hbaapi\ns-hbaapi-hba_fcpid.md">HBA_FcpId</a> structure contains this value.

</td>
</tr>
<tr>
<td>
HBA_BIND_TO_LUID

</td>
<td>
Indicates that the target is identified by its fibre channel logical unit ID. The <b>FcpLun</b> member of the <a href="..\hbaapi\ns-hbaapi-hba_fcpid.md">HBA_FcpId</a> structure contains this value.

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

Contains a structure of type <a href="..\hbaapi\ns-hbaapi-hba_scsiid.md">HBA_ScsiId</a> that contains the information that uniquely identifies a logical unit for the operating system.


### -field FcpId

Contains a structure of type <a href="..\hbaapi\ns-hbaapi-hba_fcpid.md">HBA_FcpId</a> that contains the FCP identifier for the logical unit and information about the port to be queried for information about the device.


### -field LUID

Contains a structure of type <a href="..\hbaapi\ns-hbaapi-hba_luid.md">HBA_LUID</a> that holds a logical unit descriptor for the device that the operating system derives from SCSI inquiry data. 


### -field Status

Contains, on return, a status value that indicates the condition of the HBA. The status values that can be returned in this member correspond to the values associated with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> WMI property qualifier. 


## -remarks



This structure is very similar to the <a href="..\hbapiwmi\ns-hbapiwmi-_hbafcpbindingentry2.md">HBAFCPBindingEntry2</a> structure. The only difference is that HBA_FCPBindingEntry2 returns HBA status. 




## -see-also

<a href="..\hbaapi\ns-hbaapi-hba_luid.md">HBA_LUID</a>



<a href="..\hbaapi\ns-hbaapi-hba_scsiid.md">HBA_ScsiId</a>



<a href="..\hbaapi\ns-hbaapi-hba_fcpid.md">HBA_FcpId</a>



<a href="..\hbapiwmi\ns-hbapiwmi-_hbafcpbindingentry2.md">HBAFCPBindingEntry2</a>



<a href="..\hbaapi\ns-hbaapi-hba_fcpbindingentry.md">HBA_FCPBindingEntry</a>



<a href="..\hbapiwmi\ns-hbapiwmi-_hbafcpbindingentry.md">HBAFCPBindingEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556046">HBA_BIND_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_FCPBindingEntry2 structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

