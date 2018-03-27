---
UID: NS:hbaapi.HBA_fc4types
title: HBA_fc4types
author: windows-driver-content
description: The HBA_fc4types structure contains a set of up to 32 values indicating the FC-4 types that the HBA supports.
old-location: storage\hba_fc4types.htm
old-project: storage
ms.assetid: ef043a97-3ef4-4fd3-93a6-ac1621503713
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PHBA_FC4TYPES, HBA_FC4TYPES, HBA_FC4TYPES structure [Storage Devices], HBA_fc4types, HBA_fc4types structure [Storage Devices], PHBA_FC4TYPES, PHBA_FC4TYPES structure pointer [Storage Devices], hbaapi/HBA_fc4types, hbaapi/PHBA_FC4TYPES, storage.hba_fc4types, structs-Fibre_603d3c1f-1d3c-44e5-86f0-803dda272723.xml"
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
-	HBA_FC4TYPES
product: Windows
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
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_fc4types structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

