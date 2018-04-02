---
UID: NS:hbaapi.HBA_Link_EventInfo
title: HBA_Link_EventInfo
author: windows-driver-content
description: The HBA_Link_EventInfo structure contains information about a WMI link event associated with the fibre channel HBA API.
old-location: storage\hba_link_eventinfo.htm
old-project: storage
ms.assetid: be682bc7-61cb-40bd-920d-bc2224d6e426
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PHBA_LINK_EVENTINFO, HBA_LINK_EVENTINFO, HBA_LINK_EVENTINFO structure [Storage Devices], HBA_Link_EventInfo, HBA_Link_EventInfo structure [Storage Devices], PHBA_LINK_EVENTINFO, PHBA_LINK_EVENTINFO structure pointer [Storage Devices], hbaapi/HBA_Link_EventInfo, hbaapi/PHBA_LINK_EVENTINFO, storage.hba_link_eventinfo, structs-Fibre_eb994375-ebac-41f5-af82-341f14400b1f.xml"
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
-	HBA_LINK_EVENTINFO
product: Windows
targetos: Windows
req.typenames: HBA_LINK_EVENTINFO, *PHBA_LINK_EVENTINFO
---

# HBA_Link_EventInfo structure


## -description


The HBA_Link_EventInfo structure contains information about a WMI link event associated with the fibre channel HBA API. 


## -struct-fields




### -field PortFcId

Indicates the port of type Nx_Port through which the event occurred. For a definition of Nx_Port, see the T11 committee's <i>Fibre Channel HBA API</i>.specification.


### -field Reserved

Reserved. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556048">HBA_EventInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557125">HBA_Pty_EventInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557188">HBA_RSCN_EventInfo</a>
 

 

