---
UID: NS:hbaapi.HBA_Pty_EventInfo
title: HBA_Pty_EventInfo
author: windows-driver-content
description: The HBA_Link_EventInfo structure contains information about a WMI proprietary event associated with the fibre channel HBA API.
old-location: storage\hba_pty_eventinfo.htm
old-project: storage
ms.assetid: 4291e6cd-9497-4106-82bf-c054108a0946
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PHBA_PTY_EVENTINFO, HBA_PTY_EVENTINFO, HBA_PTY_EVENTINFO structure [Storage Devices], HBA_Pty_EventInfo, HBA_Pty_EventInfo structure [Storage Devices], PHBA_PTY_EVENTINFO, PHBA_PTY_EVENTINFO structure pointer [Storage Devices], hbaapi/HBA_Pty_EventInfo, hbaapi/PHBA_PTY_EVENTINFO, storage.hba_pty_eventinfo, structs-Fibre_78e65a2e-556a-459c-9cb0-95cfbfbe4c84.xml"
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
-	HBA_PTY_EVENTINFO
product: Windows
targetos: Windows
req.typenames: HBA_PTY_EVENTINFO, *PHBA_PTY_EVENTINFO
---

# HBA_Pty_EventInfo structure


## -description


The HBA_Link_EventInfo structure contains information about a WMI proprietary event associated with the fibre channel HBA API. 


## -syntax


````
typedef struct HBA_Pty_EventInfo {
  HBA_UINT32 PtyData[4];
} HBA_PTY_EVENTINFO, *PHBA_PTY_EVENTINFO;
````


## -struct-fields




### -field PtyData

Contains proprietary data defined by the vendor. 


## -see-also

<a href="..\hbaapi\ns-hbaapi-hba_rscn_eventinfo.md">HBA_RSCN_EventInfo</a>



<a href="..\hbaapi\ns-hbaapi-hba_eventinfo.md">HBA_EventInfo</a>



<a href="..\hbaapi\ns-hbaapi-hba_link_eventinfo.md">HBA_Link_EventInfo</a>



 

 


