---
UID: NS:iscsimgt._ISCSI_PortalInfo
title: _ISCSI_PortalInfo (iscsimgt.h)
description: The ISCSI_PortalInfo structure contains information about an iSCSI portal.
old-location: storage\iscsi_portalinfo.htm
tech.root: storage
ms.assetid: 0ecfed3e-477a-4014-8491-1a8997ac5b90
ms.date: 03/29/2018
ms.keywords: "*PISCSI_PortalInfo, ISCSI_PortalInfo, ISCSI_PortalInfo structure [Storage Devices], PISCSI_PortalInfo, PISCSI_PortalInfo structure pointer [Storage Devices], _ISCSI_PortalInfo, iscsimgt/ISCSI_PortalInfo, iscsimgt/PISCSI_PortalInfo, storage.iscsi_portalinfo, structs-iSCSI_40fc24e8-364d-4698-911c-4128f471cdcd.xml"
ms.topic: struct
f1_keywords:
 - "iscsimgt/ISCSI_PortalInfo"
req.header: iscsimgt.h
req.include-header: Iscsimgt.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- iscsimgt.h
api_name:
- ISCSI_PortalInfo
product:
- Windows
targetos: Windows
req.typenames: ISCSI_PortalInfo, *PISCSI_PortalInfo
---

# _ISCSI_PortalInfo structure


## -description


The ISCSI_PortalInfo structure contains information about an iSCSI portal. 


## -struct-fields




### -field Index

The unique port number associated with this portal.


### -field PortalType

The type of portal. This member can have the following symbolic constant values, which are defined in <i>Iscsimgt.h</i>.

<table>
<tr>
<th>Portal Type</th>
<th>Meaning</th>
</tr>
<tr>
<td>
InitiatorPortals

</td>
<td>
The portal that the initiator uses to access the network. In an initiator, a portal is identified by its IP address. 

</td>
</tr>
<tr>
<td>
TargetPortals

</td>
<td>
The portal that the target uses to access the network. In a target, a portal is identified by its IP address and its listening TCP port.

</td>
</tr>
</table>
 


### -field Protocol

The portal's transport protocol. Currently, this member must hold the value that is associated with the symbolic constant, TCP. TCP is defined in <i>Iscsimgt.h</i>.


### -field Reserved1

Reserved for Microsoft use only.


### -field Reserved2

Reserved for Microsoft use only.


### -field IPAddr

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsidef/ns-iscsidef-_iscsi_ip_address">ISCSI_IP_Address</a> structure that indicates the portal's network IP address.


### -field Port

The socket number for the portal.


### -field PortalTag

The portal group tag to which the portal belongs.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsidef/ns-iscsidef-_iscsi_ip_address">ISCSI_IP_Address</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/iscsi-portalinfo-wmi-class">ISCSI_PortalInfo WMI Class</a>
 

 

