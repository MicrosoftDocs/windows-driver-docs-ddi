---
UID: NS:hbapiwmi._HBAFCPID
title: _HBAFCPID (hbapiwmi.h)
description: The HBAFCPID structure contains information that uniquely identifies a logical unit on a fibre channel network.
old-location: storage\hbafcpid.htm
tech.root: storage
ms.assetid: a4fa3093-a328-4d90-bc51-0e7a6db1ed58
ms.date: 03/29/2018
keywords: ["HBAFCPID structure"]
ms.keywords: "*PHBAFCPID, HBAFCPID, HBAFCPID structure [Storage Devices], PHBAFCPID, PHBAFCPID structure pointer [Storage Devices], _HBAFCPID, hbapiwmi/HBAFCPID, hbapiwmi/PHBAFCPID, storage.hbafcpid, structs-Fibre_d993c5b6-2b58-4fae-981a-8096cd9c9bd0.xml"
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
targetos: Windows
req.typenames: HBAFCPID, *PHBAFCPID
f1_keywords:
 - _HBAFCPID
 - hbapiwmi/_HBAFCPID
 - PHBAFCPID
 - hbapiwmi/PHBAFCPID
 - HBAFCPID
 - hbapiwmi/HBAFCPID
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - HBAFCPID
---

# _HBAFCPID structure


## -description

The HBAFCPID structure contains information that uniquely identifies a logical unit on a fibre channel network.

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

The WMI tool suite generates a declaration for this structure in <i>hbapiwm.h</i> after compiling the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/hbafcpid-wmi-class">HBAFCPID WMI Class</a>.

For more information about the fibre channel protocol (FCP), see the T11 committee's <i>dpANS Fibre Channel Protocol for SCSI</i> and <i>Fibre Channel HBA API</i> specifications.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hbapiwmi/ns-hbapiwmi-_hbafcpbindingentry">HBAFCPBindingEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556062">HBA_FcpId</a>

