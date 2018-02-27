---
UID: NS:hbaapi.HBA_wwn
title: HBA_wwn
author: windows-driver-content
description: The HBA_wwn structure contains a 64 bit world-wide name (WWN) that uniquely identifies an HBA.
old-location: storage\hba_wwn.htm
old-project: storage
ms.assetid: 84441fde-1d66-4f76-86b7-dccd792afd0f
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PHBA_WWN, HBA_WWN, HBA_WWN structure [Storage Devices], HBA_wwn, HBA_wwn structure [Storage Devices], PHBA_WWN, PHBA_WWN structure pointer [Storage Devices], hbaapi/HBA_wwn, hbaapi/PHBA_WWN, storage.hba_wwn, structs-Fibre_89c3be90-1992-4d06-9a26-c3067dc69db8.xml"
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
-	HBA_WWN
product: Windows
targetos: Windows
req.typenames: HBA_WWN, *PHBA_WWN
---

# HBA_wwn structure


## -description


The HBA_wwn structure contains a 64 bit world-wide name (WWN) that uniquely identifies an HBA. 


## -syntax


````
typedef struct HBA_wwn {
  HBA_UINT8 wwn[8];
} HBA_WWN, *PHBA_WWN;
````


## -struct-fields




### -field wwn

Contains a 64 bit world-wide name (WWN) that uniquely identifies an HBA. .


## -see-also

<a href="..\hbaapi\ns-hbaapi-hba_portattributes.md">HBA_PortAttributes</a>



<a href="..\hbaapi\ns-hbaapi-hba_adapterattributes.md">HBA_AdapterAttributes</a>



<a href="..\hbaapi\ns-hbaapi-hba_mgmtinfo.md">HBA_MgmtInfo</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_wwn structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

