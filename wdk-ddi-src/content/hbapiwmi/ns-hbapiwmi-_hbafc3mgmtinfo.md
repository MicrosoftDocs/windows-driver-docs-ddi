---
UID: NS:hbapiwmi._HBAFC3MgmtInfo
title: "_HBAFC3MgmtInfo"
author: windows-driver-content
description: The HBAFC3MgmtInfo structure is used to report FC3 management information associated with a fibre channel adapter.
old-location: storage\hbafc3mgmtinfo.htm
old-project: storage
ms.assetid: 96236605-36b0-48f5-85d6-512160692b5f
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PHBAFC3MgmtInfo structure pointer [Storage Devices], structs-Fibre_b128f553-eb08-4077-9dcb-7a7238ec220f.xml, _HBAFC3MgmtInfo, *PHBAFC3MgmtInfo, HBAFC3MgmtInfo structure [Storage Devices], storage.hbafc3mgmtinfo, HBAFC3MgmtInfo, hbapiwmi/HBAFC3MgmtInfo, PHBAFC3MgmtInfo, hbapiwmi/PHBAFC3MgmtInfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	hbapiwmi.h
apiname:
-	HBAFC3MgmtInfo
product: Windows
targetos: Windows
req.typenames: "*PHBAFC3MgmtInfo, HBAFC3MgmtInfo"
---

# _HBAFC3MgmtInfo structure


## -description


The HBAFC3MgmtInfo structure is used to report FC3 management information associated with a fibre channel adapter. 


## -syntax


````
typedef struct _HBAFC3MgmtInfo {
  ULONGLONG UniqueAdapterId;
  UCHAR     wwn[8];
  ULONG     unittype;
  ULONG     PortId;
  ULONG     NumberOfAttachedNodes;
  USHORT    IPVersion;
  USHORT    UDPPort;
  UCHAR     IPAddress[16];
  USHORT    reserved;
  USHORT    TopologyDiscoveryFlags;
  ULONG     reserved1;
} HBAFC3MgmtInfo, *PHBAFC3MgmtInfo;
````


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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553939">GetFC3MgmtInfo</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBAFC3MgmtInfo structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

