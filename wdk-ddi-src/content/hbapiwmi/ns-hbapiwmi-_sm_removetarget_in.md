---
UID: NS:hbapiwmi._SM_RemoveTarget_IN
title: "_SM_RemoveTarget_IN"
author: windows-driver-content
description: The SM_RemoveTarget_IN structure is used to provide input parameters to the SM_RemoveTarget WMI method.
old-location: storage\sm_removetarget_in.htm
old-project: storage
ms.assetid: a32e2442-a6a8-4c1a-ab70-40fdb525bafb
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PSM_RemoveTarget_IN, structs-Fibre_6efe773b-e240-40d4-bcf6-c6d141061ac3.xml, SM_RemoveTarget_IN structure [Storage Devices], hbapiwmi/SM_RemoveTarget_IN, _SM_RemoveTarget_IN, PSM_RemoveTarget_IN structure pointer [Storage Devices], *PSM_RemoveTarget_IN, hbapiwmi/PSM_RemoveTarget_IN, storage.sm_removetarget_in, SM_RemoveTarget_IN
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	hbapiwmi.h
apiname:
-	SM_RemoveTarget_IN
product: Windows
targetos: Windows
req.typenames: "*PSM_RemoveTarget_IN, SM_RemoveTarget_IN"
---

# _SM_RemoveTarget_IN structure


## -description


The SM_RemoveTarget_IN structure is used to provide input parameters to the SM_RemoveTarget WMI method.


## -syntax


````
typedef struct _SM_RemoveTarget_IN {
  UCHAR HbaPortWWN[8];
  UCHAR DiscoveredPortWWN[8];
  UCHAR DomainPortWWN[8];
  ULONG AllTargets;
} SM_RemoveTarget_IN, *PSM_RemoveTarget_IN;
````


## -struct-fields




### -field HbaPortWWN

A worldwide name (WWN) that indicates the local port that should be removed from the list of ports whose events are reported to the WMI client.


### -field DiscoveredPortWWN

A worldwide name (WWN) that indicates the port that was discovered remotely. Remove this port from the list of ports whose events are reported to the WMI client.


### -field DomainPortWWN

A worldwide name (WWN) that specifies the SAS domain worldwide name of the local port.


### -field AllTargets

The scope of the target events that stop reporting. If this member is zero, the WMI provider client stops reporting events that are associated with the port that is indicated by DiscoveredPortWWN. If this member is nonzero, the WMI provider stops reporting events that are associated with any target.


## -remarks


The WMI tool suite generates a declaration of the SM_RemoveTarget_IN structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_EventControl WMI class.


