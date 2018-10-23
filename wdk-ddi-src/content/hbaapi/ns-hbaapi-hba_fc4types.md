---
UID: NS:hbaapi.HBA_fc4types
title: HBA_fc4types
author: windows-driver-content
description: The HBA_fc4types structure contains a set of up to 32 values indicating the FC-4 types that the HBA supports.
old-location: storage\hba_fc4types.htm
tech.root: storage
ms.assetid: ef043a97-3ef4-4fd3-93a6-ac1621503713
ms.date: 03/29/2018
ms.keywords: "*PHBA_FC4TYPES, HBA_FC4TYPES, HBA_FC4TYPES structure [Storage Devices], HBA_fc4types, HBA_fc4types structure [Storage Devices], PHBA_FC4TYPES, PHBA_FC4TYPES structure pointer [Storage Devices], hbaapi/HBA_fc4types, hbaapi/PHBA_FC4TYPES, storage.hba_fc4types, structs-Fibre_603d3c1f-1d3c-44e5-86f0-803dda272723.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	hbaapi.h
api_name:
-	HBA_FC4TYPES
product:
- Windows
targetos: Windows
req.typenames: HBA_FC4TYPES, *PHBA_FC4TYPES
---

# HBA_fc4types structure


## -description


The HBA_fc4types structure contains a set of up to 32 values indicating the FC-4 types that the HBA supports. 


## -struct-fields




### -field bits

Contains 32 bytes of FC4 type information. Each byte indicates a support FC-4 type. For a complete list of the values that can be assigned to this member, see .the T11 committee's <i>Fibre Channel Generic Services -4 (FC-GS-4) </i>specification.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557107">HBA_PortAttributes</a>
 

 

