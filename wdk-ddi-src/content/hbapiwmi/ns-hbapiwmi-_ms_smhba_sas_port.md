---
UID: NS:hbapiwmi._MS_SMHBA_SAS_Port
title: _MS_SMHBA_SAS_Port (hbapiwmi.h)
description: The MS_SMHBA_SAS_Port structure is used to report the SAS port information.
old-location: storage\ms_smhba_sas_port.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["MS_SMHBA_SAS_Port structure"]
ms.keywords: "*PMS_SMHBA_SAS_Port, MS_SMHBA_SAS_Port, MS_SMHBA_SAS_Port structure [Storage Devices], PMS_SMHBA_SAS_Port, PMS_SMHBA_SAS_Port structure pointer [Storage Devices], _MS_SMHBA_SAS_Port, hbapiwmi/MS_SMHBA_SAS_Port, hbapiwmi/PMS_SMHBA_SAS_Port, storage.ms_smhba_sas_port, structs-Fibre_c7678d06-756a-4733-bdff-35571ff2c571.xml"
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
req.typenames: MS_SMHBA_SAS_Port, *PMS_SMHBA_SAS_Port
f1_keywords:
 - _MS_SMHBA_SAS_Port
 - hbapiwmi/_MS_SMHBA_SAS_Port
 - PMS_SMHBA_SAS_Port
 - hbapiwmi/PMS_SMHBA_SAS_Port
 - MS_SMHBA_SAS_Port
 - hbapiwmi/MS_SMHBA_SAS_Port
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - MS_SMHBA_SAS_Port
---

# _MS_SMHBA_SAS_Port structure


## -description

The MS_SMHBA_SAS_Port structure is used to report the SAS port information.

## -struct-fields

### -field PortProtocol

The protocols that are supported by this SAS port.

### -field LocalSASAddress

The Port_Identifier of this SAS port

### -field AttachedSASAddress

The SAS address of the entity that is at the opposite end of the SAS link from this local SAS port.

### -field NumberofDiscoveredPorts

The number of end ports that are visible to the local SAS port. The discovered ports might also include SMP ports that are contained within SAS expander devices.

### -field NumberofPhys

The number of physical ports that are associated with this SAS port. If the value is more than one, this SAS port is considered to be a wide port.

