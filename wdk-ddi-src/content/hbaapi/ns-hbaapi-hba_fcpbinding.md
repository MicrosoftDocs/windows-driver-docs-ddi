---
UID: NS:hbaapi.HBA_FCPBinding
title: HBA_FCPBinding
author: windows-driver-content
description: The HBA_FCPBinding structure contains an array of bindings between operating system and fibre channel protocol (FCP) identifiers for a set of logical units.
old-location: storage\hba_fcpbinding.htm
old-project: storage
ms.assetid: e06b82f7-2b48-47e8-b6fa-c86b790e8019
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PHBA_FCPBINDING, HBA_FCPBINDING, HBA_FCPBINDING structure [Storage Devices], HBA_FCPBinding, HBA_FCPBinding structure [Storage Devices], PHBA_FCPBINDING, PHBA_FCPBINDING structure pointer [Storage Devices], hbaapi/HBA_FCPBinding, hbaapi/PHBA_FCPBINDING, storage.hba_fcpbinding, structs-Fibre_c02a809a-3b65-4e19-93e0-c72a0aead81c.xml"
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
-	HBA_FCPBINDING
product: Windows
targetos: Windows
req.typenames: HBA_FCPBINDING, *PHBA_FCPBINDING
---

# HBA_FCPBinding structure


## -description


The HBA_FCPBinding structure contains an array of bindings between operating system and fibre channel protocol (FCP) identifiers for a set of logical units. 


## -syntax


````
typedef struct HBA_FCPBinding {
  HBA_UINT32          NumberOfEntries;
  HBA_FCPBINDINGENTRY entry[1];
} HBA_FCPBINDING, *PHBA_FCPBINDING;
````


## -struct-fields




### -field NumberOfEntries

Indicates the number of bindings.


### -field entry

Contains a variable length array of structures of type <a href="..\hbaapi\ns-hbaapi-hba_fcpbindingentry.md">HBA_FCPBindingEntry</a> each of which defines a binding between a pair of operating system and fibre channel protocol (FCP) identifiers for a logical unit. 


## -see-also

<a href="..\hbapiwmi\ns-hbapiwmi-_hbafcpbindingentry.md">HBAFCPBindingEntry</a>



<a href="..\hbaapi\ns-hbaapi-hba_fcpbindingentry.md">HBA_FCPBindingEntry</a>



 

 


