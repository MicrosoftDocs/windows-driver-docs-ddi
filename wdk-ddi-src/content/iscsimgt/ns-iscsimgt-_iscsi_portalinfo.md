---
UID: NS:iscsimgt._ISCSI_PortalInfo
title: "_ISCSI_PortalInfo"
author: windows-driver-content
description: The ISCSI_PortalInfo structure contains information about an iSCSI portal.
old-location: storage\iscsi_portalinfo.htm
old-project: storage
ms.assetid: 0ecfed3e-477a-4014-8491-1a8997ac5b90
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: "*PISCSI_PortalInfo, iscsimgt/PISCSI_PortalInfo, PISCSI_PortalInfo, ISCSI_PortalInfo, storage.iscsi_portalinfo, _ISCSI_PortalInfo, iscsimgt/ISCSI_PortalInfo, PISCSI_PortalInfo structure pointer [Storage Devices], structs-iSCSI_40fc24e8-364d-4698-911c-4128f471cdcd.xml, ISCSI_PortalInfo structure [Storage Devices]"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	iscsimgt.h
apiname:
-	ISCSI_PortalInfo
product: Windows
targetos: Windows
req.typenames: "*PISCSI_PortalInfo, ISCSI_PortalInfo"
---

# _ISCSI_PortalInfo structure


## -description


The ISCSI_PortalInfo structure contains information about an iSCSI portal. 


## -syntax


````
typedef struct _ISCSI_PortalInfo {
  ULONG            Index;
  UCHAR            PortalType;
  UCHAR            Protocol;
  UCHAR            Reserved1;
  UCHAR            Reserved2;
  ISCSI_IP_Address IPAddr;
  ULONG            Port;
  USHORT           PortalTag;
} ISCSI_PortalInfo, *PISCSI_PortalInfo;
````


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

A <a href="..\iscsidef\ns-iscsidef-_iscsi_ip_address.md">ISCSI_IP_Address</a> structure that indicates the portal's network IP address.


### -field Port

The socket number for the portal.


### -field PortalTag

The portal group tag to which the portal belongs.


## -see-also

<a href="..\iscsidef\ns-iscsidef-_iscsi_ip_address.md">ISCSI_IP_Address</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561559">ISCSI_PortalInfo WMI Class</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ISCSI_PortalInfo structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

