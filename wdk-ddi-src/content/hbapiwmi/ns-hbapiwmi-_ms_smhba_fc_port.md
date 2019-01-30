---
UID: NS:hbapiwmi._MS_SMHBA_FC_Port
title: "_MS_SMHBA_FC_Port" (hbapiwmi.h)
description: The MS_SMHBA_FC_Port structure is used to report the FC port information.
old-location: storage\ms_smhba_fc_port.htm
tech.root: storage
ms.assetid: e5d0d58c-f2dd-4c8a-9b15-967d0be89788
ms.date: 03/29/2018
ms.keywords: "*PMS_SMHBA_FC_Port, MS_SMHBA_FC_Port, MS_SMHBA_FC_Port structure [Storage Devices], PMS_SMHBA_FC_Port, PMS_SMHBA_FC_Port structure pointer [Storage Devices], _MS_SMHBA_FC_Port, hbapiwmi/MS_SMHBA_FC_Port, hbapiwmi/PMS_SMHBA_FC_Port, storage.ms_smhba_fc_port, structs-Fibre_74bec0b8-c7eb-4866-8fef-ab9a7c3d5950.xml"
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
-	MS_SMHBA_FC_Port
product:
- Windows
targetos: Windows
req.typenames: MS_SMHBA_FC_Port, *PMS_SMHBA_FC_Port
---

# _MS_SMHBA_FC_Port structure


## -description


The MS_SMHBA_FC_Port structure is used to report the FC port information.


## -struct-fields




### -field NodeWWN

A 64-bit world-wide name (WWN) that uniquely identifies the fibre channel node that is associated with PortWWN. For more information about worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification.


### -field PortWWN

A 64-bit world-wide name (WWN) that uniquely identifies the fibre channel port. For more information about worldwide names, see the T11 committee's <i>Fibre Channel HBA API </i>specification.


### -field FcId

The current fibre channel address of PortWWN. The high order byte of this member contains the first byte of the address. Successively lower order bytes of this member contain successively lower bytes of the address. The lowest order byte of this member must be zero.


### -field PortSupportedClassofService

The class of service that is supported by PortWWN. For a list of the different classes of service and the values that must be assigned to this member for each class, see the ANSI standard for Fibre Channel Generic Services 4th Generation (FC-GS-4).


### -field PortSupportedFc4Types

The FC-4 types that are supported by PortWWN. For more information about FC-4 types, see the ANSI standard for Fibre Channel Generic Services 4th Generation (FC-GS-4).


### -field PortActiveFc4Types

The FC-4 types that are currently available on PortWWN. For more information about FC-4 types, see the ANSI standard for Fibre Channel Generic Services 4th Generation (FC-GS-4).


### -field FabricName

The name identifier for the fabric to which PortWWN is attached.


### -field NumberofDiscoveredPorts

The number of ports that are visible to PortWWN. For more information about the types of ports that this number takes into consideration, see the T11 committee's specification for <i>Fibre Channel HBA API (FC-HBA).</i>


### -field NumberofPhys

The number of physical fibre channel ports.


### -field PortSymbolicName

An ASCII string that is less than or equal to 256 bytes in length and that indicates the symbolic name for the fibre channel node.

