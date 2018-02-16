---
UID: NS:hbaapi.HBA_Link_EventInfo
title: HBA_Link_EventInfo
author: windows-driver-content
description: The HBA_Link_EventInfo structure contains information about a WMI link event associated with the fibre channel HBA API.
old-location: storage\hba_link_eventinfo.htm
old-project: storage
ms.assetid: be682bc7-61cb-40bd-920d-bc2224d6e426
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: hbaapi/PHBA_LINK_EVENTINFO, PHBA_LINK_EVENTINFO structure pointer [Storage Devices], HBA_Link_EventInfo structure [Storage Devices], HBA_LINK_EVENTINFO structure [Storage Devices], PHBA_LINK_EVENTINFO, storage.hba_link_eventinfo, HBA_LINK_EVENTINFO, HBA_Link_EventInfo, *PHBA_LINK_EVENTINFO, hbaapi/HBA_Link_EventInfo, structs-Fibre_eb994375-ebac-41f5-af82-341f14400b1f.xml
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
-	HBA_LINK_EVENTINFO
product: Windows
targetos: Windows
req.typenames: HBA_LINK_EVENTINFO, *PHBA_LINK_EVENTINFO
---

# HBA_Link_EventInfo structure


## -description


The HBA_Link_EventInfo structure contains information about a WMI link event associated with the fibre channel HBA API. 


## -syntax


````
typedef struct HBA_Link_EventInfo {
  HBA_UINT32 PortFcId;
  HBA_UINT32 Reserved[3];
} HBA_LINK_EVENTINFO, *PHBA_LINK_EVENTINFO;
````


## -struct-fields




### -field PortFcId

Indicates the port of type Nx_Port through which the event occurred. For a definition of Nx_Port, see the T11 committee's <i>Fibre Channel HBA API</i>.specification.


### -field Reserved

Reserved. 


## -see-also

<a href="..\hbaapi\ns-hbaapi-hba_rscn_eventinfo.md">HBA_RSCN_EventInfo</a>



<a href="..\hbaapi\ns-hbaapi-hba_eventinfo.md">HBA_EventInfo</a>



<a href="..\hbaapi\ns-hbaapi-hba_pty_eventinfo.md">HBA_Pty_EventInfo</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_Link_EventInfo structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

