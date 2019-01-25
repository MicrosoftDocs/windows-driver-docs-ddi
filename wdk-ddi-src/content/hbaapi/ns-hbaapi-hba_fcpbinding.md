---
UID: NS:hbaapi.HBA_FCPBinding
title: HBA_FCPBinding (hbaapi.h)
description: The HBA_FCPBinding structure contains an array of bindings between operating system and fibre channel protocol (FCP) identifiers for a set of logical units.
old-location: storage\hba_fcpbinding.htm
tech.root: storage
ms.assetid: e06b82f7-2b48-47e8-b6fa-c86b790e8019
ms.date: 03/29/2018
ms.keywords: "*PHBA_FCPBINDING, HBA_FCPBINDING, HBA_FCPBINDING structure [Storage Devices], HBA_FCPBinding, HBA_FCPBinding structure [Storage Devices], PHBA_FCPBINDING, PHBA_FCPBINDING structure pointer [Storage Devices], hbaapi/HBA_FCPBinding, hbaapi/PHBA_FCPBINDING, storage.hba_fcpbinding, structs-Fibre_c02a809a-3b65-4e19-93e0-c72a0aead81c.xml"
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
-	HBA_FCPBINDING
product:
- Windows
targetos: Windows
req.typenames: HBA_FCPBINDING, *PHBA_FCPBINDING
---

# HBA_FCPBinding structure


## -description


The HBA_FCPBinding structure contains an array of bindings between operating system and fibre channel protocol (FCP) identifiers for a set of logical units. 


## -struct-fields




### -field NumberOfEntries

Indicates the number of bindings.


### -field entry

Contains a variable length array of structures of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff556058">HBA_FCPBindingEntry</a> each of which defines a binding between a pair of operating system and fibre channel protocol (FCP) identifiers for a logical unit. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556034">HBAFCPBindingEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556058">HBA_FCPBindingEntry</a>
 

 

