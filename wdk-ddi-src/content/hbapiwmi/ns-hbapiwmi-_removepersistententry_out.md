---
UID: NS:hbapiwmi._RemovePersistentEntry_OUT
title: "_RemovePersistentEntry_OUT"
author: windows-driver-content
description: The RemovePersistentEntry_OUT structure is used to report the output parameter data of the RemovePersistentEntry WMI method to the WMI client.
old-location: storage\removepersistententry_out.htm
old-project: storage
ms.assetid: 2fa578f7-5892-4ec1-a01f-49c828bd6913
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PRemovePersistentEntry_OUT, PRemovePersistentEntry_OUT, PRemovePersistentEntry_OUT structure pointer [Storage Devices], RemovePersistentEntry_OUT, RemovePersistentEntry_OUT structure [Storage Devices], _RemovePersistentEntry_OUT, hbapiwmi/PRemovePersistentEntry_OUT, hbapiwmi/RemovePersistentEntry_OUT, storage.removepersistententry_out, structs-Fibre_8a84bc15-be90-4a74-a551-c3cf43d4f5ef.xml"
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
-	RemovePersistentEntry_OUT
product:
- Windows
targetos: Windows
req.typenames: RemovePersistentEntry_OUT, *PRemovePersistentEntry_OUT
---

# _RemovePersistentEntry_OUT structure


## -description


The RemovePersistentEntry_OUT structure is used to report the output parameter data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563988">RemovePersistentEntry</a> WMI method to the WMI client.


## -struct-fields




### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>. 


## -remarks



The WMI tool suite generates a declaration of the RemovePersistentEntry_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562509">MSFC_HBAFCPInfo WMI Class</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563988">RemovePersistentEntry</a>
 

 

