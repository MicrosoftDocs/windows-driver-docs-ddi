---
UID: NS:hbaapi.HBA_MgmtInfo
title: HBA_MgmtInfo
author: windows-driver-content
description: The HBA_MgmtInfo structure is used in conjunction with the HBA_SetRNIDMgmtInfo routine to program the HBA to return the indicated request node identification information data (RNID).
old-location: storage\hba_mgmtinfo.htm
old-project: storage
ms.assetid: a4ccb122-ae90-4b06-a40d-21f131add99b
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: HBA_MgmtInfo structure [Storage Devices], PHBA_MGMTINFO, PHBA_MGMTINFO structure pointer [Storage Devices], HBA_MgmtInfo, HBA_MGMTINFO structure [Storage Devices], *PHBA_MGMTINFO, hbaapi/PHBA_MGMTINFO, HBA_MGMTINFO, structs-Fibre_d7bcdc56-a999-4d0b-b7f0-88fe53b349b1.xml, hbaapi/HBA_MgmtInfo, storage.hba_mgmtinfo
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
-	HBA_MGMTINFO
product: Windows
targetos: Windows
req.typenames: HBA_MGMTINFO, *PHBA_MGMTINFO
---

# HBA_MgmtInfo structure


## -description


The HBA_MgmtInfo structure is used in conjunction with the <a href="..\hbaapi\nf-hbaapi-hba_setrnidmgmtinfo.md">HBA_SetRNIDMgmtInfo</a> routine to program the HBA to return the indicated request node identification information data (RNID). 


## -syntax


````
typedef struct HBA_MgmtInfo {
  HBA_WWN    wwn;
  HBA_UINT32 unittype;
  HBA_UINT32 PortId;
  HBA_UINT32 NumberOfAttachedNodes;
  HBA_UINT16 IPVersion;
  HBA_UINT16 UDPPort;
  HBA_UINT8  IPAddress[16];
  HBA_UINT16 reserved;
  HBA_UINT16 TopologyDiscoveryFlags;
} HBA_MGMTINFO, *PHBA_MGMTINFO;
````


## -struct-fields




### -field wwn

Contains a 64 bit world-wide name (WWN) that uniquely identifies the primary fibre channel node (host system) to which the HBA is attached. This information is returned in an RNID Accept payload in response to an RNID request. For more information about the meaning of this member, see the description of the RNID Accept payload in the <i>Fibre Channel Framing and Signaling (FC-FS) </i>specification, published by the T11 committee. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification. 


### -field unittype

Contains a value that indicates the unit type. Unit types include such things as gateways, switches, hubs, storage subsystems, etc. For a list of values that can be assigned to this field and their corresponding units, see the <i>Fibre Channel Framing and Signaling (FC-FS) </i>specification, published by the T11 committee.


### -field PortId

Contains a vendor-specific value that identifies the physical port on the HBA that has a Fibre-Channel link attached. For more information about the meaning of this member, see the <i>Fibre Channel Framing and Signaling (FC-FS) </i>specification, published by the T11 committee. 


### -field NumberOfAttachedNodes

Indicates the number of nodes to which the HBA is attached. For more information about the meaning of this member, see the description of the RNID Accept payload in the <i>Fibre Channel Framing and Signaling (FC-FS) </i>specification, published by the T11 committee. 


### -field IPVersion

Indicates the version of the IP protocol used by the HBA. For more information about the meaning of this member, see the <i>Fibre Channel Framing and Signaling (FC-FS) </i>specification, published by the T11 committee. 


### -field UDPPort

Indicates the UDP/TCP port number used by the HBA. For more information about the meaning of this member, see the <i>Fibre Channel Framing and Signaling (FC-FS) </i>specification, published by the T11 committee. 


### -field IPAddress

Contains the IP address f the HBA. 


### -field reserved

Reserved. 


### -field TopologyDiscoveryFlags

Contains the topology discovery flags. For an explanation of this member, see the <i>Fibre Channel Framing and Signaling (FC-FS) </i>specification, published by the T11 committee. 


## -see-also

<a href="..\hbaapi\nf-hbaapi-hba_getrnidmgmtinfo.md">HBA_GetRNIDMgmtInfo</a>

<a href="..\hbaapi\nf-hbaapi-hba_setrnidmgmtinfo.md">HBA_SetRNIDMgmtInfo</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_MgmtInfo structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

