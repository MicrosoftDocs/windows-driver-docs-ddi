---
UID: NS:hbapiwmi._HBAFCPID
title: "_HBAFCPID"
author: windows-driver-content
description: The HBAFCPID structure contains information that uniquely identifies a logical unit on a fibre channel network.
old-location: storage\hbafcpid.htm
old-project: storage
ms.assetid: a4fa3093-a328-4d90-bc51-0e7a6db1ed58
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PHBAFCPID, HBAFCPID, HBAFCPID structure [Storage Devices], PHBAFCPID, PHBAFCPID structure pointer [Storage Devices], _HBAFCPID, hbapiwmi/HBAFCPID, hbapiwmi/PHBAFCPID, storage.hbafcpid, structs-Fibre_d993c5b6-2b58-4fae-981a-8096cd9c9bd0.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	hbapiwmi.h
api_name:
-	HBAFCPID
product: Windows
targetos: Windows
req.typenames: HBAFCPID, *PHBAFCPID
---

# _HBAFCPID structure


## -description


The HBAFCPID structure contains information that uniquely identifies a logical unit on a fibre channel network.


## -syntax


````
typedef struct _HBAFCPID {
  ULONG     Fcid;
  UCHAR     NodeWWN[8];
  UCHAR     PortWWN[8];
  ULONGLONG FcpLun;
} HBAFCPID, *PHBAFCPID;
````


## -struct-fields




### -field Fcid

Contains the identifier that indicates which port is to be queried for information about the logical unit. For a discussion of the values that this member have, see the T11 committee's <i>Fibre Channel HBA API</i> specification.


### -field NodeWWN

Contains the 64 bit world-wide name (WWN) of the node (machine) to which the logical unit is connected. If an HBA has multiple ports and is associated with more than one node, this member will contain a name chosen from among the names of the associated nodes. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification.


### -field PortWWN

Contains the 64 bit world-wide name of the port to be queried for information about the logical unit. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification.


### -field FcpLun

Contains a 64-bit fibre channel protocol (FCP) number for the logical unit. 


## -remarks



The WMI tool suite generates a declaration for this structure in <i>hbapiwm.h</i> after compiling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556039">HBAFCPID WMI Class</a>.

For more information about the fibre channel protocol (FCP), see the T11 committee's <i>dpANS Fibre Channel Protocol for SCSI</i> and <i>Fibre Channel HBA API</i> specifications.




## -see-also

<a href="..\hbapiwmi\ns-hbapiwmi-_hbafcpbindingentry.md">HBAFCPBindingEntry</a>



<a href="..\hbaapi\ns-hbaapi-hba_fcpid.md">HBA_FcpId</a>



 

 


