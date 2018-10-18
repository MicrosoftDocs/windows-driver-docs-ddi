---
UID: NS:hbaapi.HBA_FCPBinding2
title: HBA_FCPBinding2
author: windows-driver-content
description: The HBA_FCPBinding2 structure contains an array of bindings between operating system identifiers, SCSI logical unit ID descriptors (LUIDs) and fibre channel protocol (FCP) identifiers for a set of logical units.
old-location: storage\hba_fcpbinding2.htm
tech.root: storage
ms.assetid: f715d45c-30e1-414f-907c-9ad1203ca604
ms.date: 03/29/2018
ms.keywords: "*PHBA_FCPBINDING2, HBA_FCPBINDING2, HBA_FCPBINDING2 structure [Storage Devices], HBA_FCPBinding2, HBA_FCPBinding2 structure [Storage Devices], PHBA_FCPBINDING2, PHBA_FCPBINDING2 structure pointer [Storage Devices], hbaapi/HBA_FCPBinding2, hbaapi/PHBA_FCPBINDING2, storage.hba_fcpbinding2, structs-Fibre_b19a2c46-204e-4500-a4ed-9e3949941093.xml"
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
-	HBA_FCPBINDING2
product:
- Windows
targetos: Windows
req.typenames: HBA_FCPBINDING2, *PHBA_FCPBINDING2
---

# HBA_FCPBinding2 structure


## -description


The HBA_FCPBinding2 structure contains an array of bindings between operating system identifiers, SCSI logical unit ID descriptors (LUIDs) and fibre channel protocol (FCP) identifiers for a set of logical units. 


## -struct-fields




### -field NumberOfEntries

Indicates, on input, the number of bindings that can fit in the array at <b>entry</b>. On output, this member holds the number of entries actually returned, which will be equal to the number specified on input or the full set of available bindings, whichever is smaller. The value in <b>NumberOfEntries</b> will contain the number of persistent bindings returned even when an error occurred because of insufficient buffer space. 


### -field entry

Variable length array of elements of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff556060">HBA_FCPBindingEntry2</a>, each of which holds a persistent binding between operating system identifiers, a SCSI logical unit ID descriptor (LUID) and a fibre channel protocol (FCP) identifier for a logical unit. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556102">HBA_GetPersistentBindingV2</a>
 

 

