---
UID: NS:hbapiwmi._HBAFCPBindingEntry
title: "_HBAFCPBindingEntry"
author: windows-driver-content
description: The HBAFCPBindingEntry structure defines a binding between the information that uniquely identifies a logical unit for the operating system and the fibre channel protocol (FCP) identifier for the logical unit.
old-location: storage\hbafcpbindingentry.htm
old-project: storage
ms.assetid: fa0f20e1-7d63-48e8-8270-8dab566f5947
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PHBAFCPBindingEntry, ,, A, B, C, E, F, H, HBAFCPBindingEntry, HBAFCPBindingEntry structure [Storage Devices], P, PHBAFCPBindingEntry, PHBAFCPBindingEntry structure pointer [Storage Devices], _, _HBAFCPBindingEntry, d, g, hbapiwmi/HBAFCPBindingEntry, hbapiwmi/PHBAFCPBindingEntry, i, n, r, storage.hbafcpbindingentry, structs-Fibre_1b8c019a-3cec-4aa3-b43c-8f52168c7a03.xml, t, y"
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
-	Hbapiwmi.h
apiname:
-	HBAFCPBindingEntry
product: Windows
targetos: Windows
req.typenames: HBAFCPBindingEntry, *PHBAFCPBindingEntry
---

# _HBAFCPBindingEntry structure


## -description


The HBAFCPBindingEntry structure defines a binding between the information that uniquely identifies a logical unit for the operating system and the fibre channel protocol (FCP) identifier for the logical unit. 


## -syntax


````
typedef struct _HBAFCPBindingEntry {
  ULONG     Type;
  HBAFCPID  FCPId;
  HBAScsiID ScsiId;
} HBAFCPBindingEntry, *PHBAFCPBindingEntry;
````


## -struct-fields




### -field Type

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
 

You must include file <i>hbaapi.h </i>to use the symbolic constants in this table (See the <b>Headers</b> section).

For a comparable set of values that define how an HBA specifies targets and logical units in the persistent bindings that it maintains, see the WMI property qualifier <a href="https://msdn.microsoft.com/library/windows/hardware/ff556046">HBA_BIND_TYPE</a>. 

For a more detailed description of the values that this member can have, see the T11 committee's <i>Fibre Channel HBA API</i> specification. 


### -field FCPId

Contains a structure of type <a href="..\hbapiwmi\ns-hbapiwmi-_hbafcpid.md">HBAFCPID</a> that contains the FCP identifier for the logical unit and information about the port to be queried for information about the device.


### -field ScsiId

Contains a structure of type <a href="..\hbapiwmi\ns-hbapiwmi-_hbascsiid.md">HBAScsiID</a> that contains the information that uniquely identifies a logical unit for the operating system. 


## -remarks



The WMI tool suite generates a declaration of this structure automatically when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556037">HBAFCPBindingEntry WMI Class</a> in <i>hbaapi.mof</i>. 

For an explanation of the fibre channel protocol (FCP), see the T11 committee's <i>Fibre Channel Protocol for SCSI</i> specification. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556037">HBAFCPBindingEntry WMI Class</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBAFCPBindingEntry structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

