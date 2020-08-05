---
UID: NS:hbapiwmi._HBAFC3MgmtInfo
title: _HBAFC3MgmtInfo (hbapiwmi.h)
description: The HBAFC3MgmtInfo structure is used to report FC3 management information associated with a fibre channel adapter.
old-location: storage\hbafc3mgmtinfo.htm
tech.root: storage
ms.assetid: 96236605-36b0-48f5-85d6-512160692b5f
ms.date: 03/29/2018
keywords: ["HBAFC3MgmtInfo structure"]
ms.keywords: "*PHBAFC3MgmtInfo, HBAFC3MgmtInfo, HBAFC3MgmtInfo structure [Storage Devices], PHBAFC3MgmtInfo, PHBAFC3MgmtInfo structure pointer [Storage Devices], _HBAFC3MgmtInfo, hbapiwmi/HBAFC3MgmtInfo, hbapiwmi/PHBAFC3MgmtInfo, storage.hbafc3mgmtinfo, structs-Fibre_b128f553-eb08-4077-9dcb-7a7238ec220f.xml"
f1_keywords:
 - "hbapiwmi/HBAFC3MgmtInfo"
 - "HBAFC3MgmtInfo"
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
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
- hbapiwmi.h
api_name:
- HBAFC3MgmtInfo
targetos: Windows
req.typenames: HBAFC3MgmtInfo, *PHBAFC3MgmtInfo
---

# _HBAFC3MgmtInfo structure


## -description


The HBAFC3MgmtInfo structure is used to report FC3 management information associated with a fibre channel adapter. 


## -struct-fields




### -field UniqueAdapterId

Contains a unique identifier for the adapter. 


### -field wwn

Contains a worldwide name for the adapter, as described in the T11 committee's <i>Fibre Channel HBA API </i>specification. 


### -field unittype

Describes the type of HBA, as described in the T11 committee's <i>Fibre Channel HBA API </i>specification.


### -field PortId

Contains a value corresponding to the physical port number field of the specific identification data as described in the T11 committee's <i>Fibre Channel HBA API </i>specification.


### -field NumberOfAttachedNodes

Contains the number of nodes attached to the topology as described in the T11 committee's <i>Fibre Channel HBA API </i>specification.


### -field IPVersion

Contains the concatenated node management and IP version fields of the specific identification data as described in the T11 committee's <i>Fibre Channel HBA API </i>specification.


### -field UDPPort

Indicates the value of the UDP/TCP port number field of the specific identification data as described in the T11 committee's <i>Fibre Channel HBA API </i>specification.


### -field IPAddress

Indicates the value of the IP address field of the specific identification data as described in the T11 committee's <i>Fibre Channel HBA API </i>specification.


### -field reserved

Reserved.


### -field TopologyDiscoveryFlags

Indicates the value of the vendor specific field in word 12 of the specific identification data as described in the T11 committee's <i>Fibre Channel HBA API </i>specification.


### -field reserved1

Reserved.


## -remarks



FC-3 refers to the common services layer of the fibre channel protocol. It defines a set of services which are common across multiple ports of a node. For an explanation of the common services layer, see the T11 committee's <i>Fibre Channel HBA API</i> specification.

The WMI tool suite generates a declaration of this structure automatically when it compiles the <b>HBAFC3MgmtInfo</b> WMI Class in <i>hbaapi.mof</i>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/getfc3mgmtinfo">GetFC3MgmtInfo</a>
 

 

