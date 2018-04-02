---
UID: NS:hbaapi.HBA_FCPTargetMapping
title: HBA_FCPTargetMapping
author: windows-driver-content
description: The HBA_FCPTargetMapping structure contains an array of bindings between operating system and fibre channel protocol (FCP) identifiers for a set of target devices.
old-location: storage\hba_fcptargetmapping.htm
old-project: storage
ms.assetid: 666f4aea-2fcb-46cf-8d25-d1322c0517c9
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PHBA_FCPTARGETMAPPING, HBA_FCPTARGETMAPPING, HBA_FCPTARGETMAPPING structure [Storage Devices], HBA_FCPTargetMapping, HBA_FCPTargetMapping structure [Storage Devices], PHBA_FCPTARGETMAPPING, PHBA_FCPTARGETMAPPING structure pointer [Storage Devices], hbaapi/HBA_FCPTargetMapping, hbaapi/PHBA_FCPTARGETMAPPING, storage.hba_fcptargetmapping, structs-Fibre_ac1d3ea4-8e4f-4164-833f-dde1c0eaa30a.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	hbaapi.h
api_name:
-	HBA_FCPTARGETMAPPING
product: Windows
targetos: Windows
req.typenames: HBA_FCPTARGETMAPPING, *PHBA_FCPTARGETMAPPING
---

# HBA_FCPTargetMapping structure


## -description


The HBA_FCPTargetMapping structure contains an array of bindings between operating system and fibre channel protocol (FCP) identifiers for a set of target devices. 


## -struct-fields




### -field NumberOfEntries

Indicates the number of bindings.


### -field entry

Contains a variable length array of structures of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff556064">HBA_FcpScsiEntry</a> each of which defines a mapping between an operating system identifier for a logical unit and the corresponding fibre channel protocol (FCP) identifier for the logical unit. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556064">HBA_FcpScsiEntry</a>
 

 

