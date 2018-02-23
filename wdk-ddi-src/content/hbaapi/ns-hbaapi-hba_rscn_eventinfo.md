---
UID: NS:hbaapi.HBA_RSCN_EventInfo
title: HBA_RSCN_EventInfo
author: windows-driver-content
description: The HBA_Link_EventInfo structure contains information about a WMI RSCN event associated with the fibre channel HBA API.
old-location: storage\hba_rscn_eventinfo.htm
old-project: storage
ms.assetid: d726d974-a877-464d-9721-6caf8a8402bf
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: HBA_RSCN_EventInfo structure [Storage Devices], PHBA_RSCN_EVENTINFO, HBA_RSCN_EVENTINFO structure [Storage Devices], storage.hba_rscn_eventinfo, PHBA_RSCN_EVENTINFO structure pointer [Storage Devices], hbaapi/HBA_RSCN_EventInfo, HBA_RSCN_EVENTINFO, hbaapi/PHBA_RSCN_EVENTINFO, *PHBA_RSCN_EVENTINFO, structs-Fibre_c0cb4c14-5ff5-44cb-abb4-08673227f193.xml, HBA_RSCN_EventInfo
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
-	HBA_RSCN_EVENTINFO
product: Windows
targetos: Windows
req.typenames: HBA_RSCN_EVENTINFO, *PHBA_RSCN_EVENTINFO
---

# HBA_RSCN_EventInfo structure


## -description


The HBA_Link_EventInfo structure contains information about a WMI RSCN event associated with the fibre channel HBA API. 


## -syntax


````
typedef struct HBA_RSCN_EventInfo {
  HBA_UINT32 PortFcId;
  HBA_UINT32 NPortPage;
  HBA_UINT32 Reserved[2];
} HBA_RSCN_EVENTINFO, *PHBA_RSCN_EVENTINFO;
````


## -struct-fields




### -field PortFcId

Indicates the port of type Nx_Port through which the event occurred. For a definition of Nx_Port, see the T11 committee's <i>Fibre Channel HBA API</i>.specification.


### -field NPortPage

Contains port page information. For information about what values this member can have, see section entitled "Affected N-Port Pages" in the <i>FC-FS </i>specification for RSCN ELS. 


### -field Reserved

Reserved. 


## -see-also

<a href="..\hbaapi\ns-hbaapi-hba_link_eventinfo.md">HBA_Link_EventInfo</a>



<a href="..\hbaapi\ns-hbaapi-hba_eventinfo.md">HBA_EventInfo</a>



<a href="..\hbaapi\ns-hbaapi-hba_pty_eventinfo.md">HBA_Pty_EventInfo</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_RSCN_EventInfo structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

