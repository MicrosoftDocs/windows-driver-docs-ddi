---
UID: NS:hbapiwmi._RemoveTarget_IN
title: _RemoveTarget_IN (hbapiwmi.h)
description: The RemoveTarget_IN structure is used by a WMI client to deliver input parameter data to the RemoveTarget WMI method.
old-location: storage\removetarget_in.htm
tech.root: storage
ms.assetid: 54fcbb64-09ce-4f18-963b-fee2627d4231
ms.date: 03/29/2018
keywords: ["_RemoveTarget_IN structure"]
ms.keywords: "*PRemoveTarget_IN, PRemoveTarget_IN, PRemoveTarget_IN structure pointer [Storage Devices], RemoveTarget_IN, RemoveTarget_IN structure [Storage Devices], _RemoveTarget_IN, hbapiwmi/PRemoveTarget_IN, hbapiwmi/RemoveTarget_IN, storage.removetarget_in, structs-Fibre_e284d48f-3a57-449f-8227-2e8637118dcd.xml"
f1_keywords:
 - "hbapiwmi/RemoveTarget_IN"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- hbapiwmi.h
api_name:
- RemoveTarget_IN
product:
- Windows
targetos: Windows
req.typenames: RemoveTarget_IN, *PRemoveTarget_IN
---

# _RemoveTarget_IN structure


## -description


The RemoveTarget_IN structure is used by a WMI client to deliver input parameter data to the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/removetarget">RemoveTarget</a> WMI method.


## -struct-fields




### -field HbaPortWWN

Contains a worldwide name that indicates the local port that should be removed from the list of ports whose events are reported to the WMI client.. 


### -field DiscoveredPortWWN

Contains a worldwide name that indicates the remote discovered port that should be removed from the list of ports whose events are reported to the WMI client.. 


### -field AllTargets

Indicates the scope of the target events to cease reporting. If this member is zero, the WMI provider client will cease reporting events associated with the port that is indicated by <b>DiscoveredPortWWN</b>. If this member is nonzero, the WMI provider will cease reporting all events associated any target. 


## -remarks



The WMI tool suite generates a declaration of the RemoveTarget_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msfc-eventcontrol-wmi-class">MSFC_EventControl WMI Class</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/removetarget">RemoveTarget</a>
 

 

