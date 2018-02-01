---
UID: NS:hbaapi.HBA_FCPBinding
title: HBA_FCPBinding
author: windows-driver-content
description: The HBA_FCPBinding structure contains an array of bindings between operating system and fibre channel protocol (FCP) identifiers for a set of logical units.
old-location: storage\hba_fcpbinding.htm
old-project: storage
ms.assetid: e06b82f7-2b48-47e8-b6fa-c86b790e8019
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: HBA_FCPBINDING, HBA_FCPBINDING structure [Storage Devices], PHBA_FCPBINDING, structs-Fibre_c02a809a-3b65-4e19-93e0-c72a0aead81c.xml, *PHBA_FCPBINDING, HBA_FCPBinding, hbaapi/PHBA_FCPBINDING, PHBA_FCPBINDING structure pointer [Storage Devices], HBA_FCPBinding structure [Storage Devices], storage.hba_fcpbinding, hbaapi/HBA_FCPBinding
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	hbaapi.h
apiname:
-	HBA_FCPBINDING
product: Windows
targetos: Windows
req.typenames: "*PHBA_FCPBINDING, HBA_FCPBINDING"
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

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_FCPBinding structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

