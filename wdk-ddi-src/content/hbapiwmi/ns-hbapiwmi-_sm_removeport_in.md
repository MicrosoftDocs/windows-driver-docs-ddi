---
UID: NS:hbapiwmi._SM_RemovePort_IN
title: _SM_RemovePort_IN (hbapiwmi.h)
description: The SM_RemovePort_IN structure is used to provide input parameters to the SM_RemovePort WMI method.
old-location: storage\sm_removeport_in.htm
tech.root: storage
ms.assetid: b8eb6321-928f-4366-9553-c75900fa1ac6
ms.date: 03/29/2018
keywords: ["_SM_RemovePort_IN structure"]
ms.keywords: "*PSM_RemovePort_IN, PSM_RemovePort_IN, PSM_RemovePort_IN structure pointer [Storage Devices], SM_RemovePort_IN, SM_RemovePort_IN structure [Storage Devices], _SM_RemovePort_IN, hbapiwmi/PSM_RemovePort_IN, hbapiwmi/SM_RemovePort_IN, storage.sm_removeport_in, structs-Fibre_0290cc86-0661-47ae-89db-3a3756c5d681.xml"
f1_keywords:
 - "hbapiwmi/SM_RemovePort_IN"
 - "SM_RemovePort_IN"
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
- SM_RemovePort_IN
targetos: Windows
req.typenames: SM_RemovePort_IN, *PSM_RemovePort_IN
---

# _SM_RemovePort_IN structure


## -description


The SM_RemovePort_IN structure is used to provide input parameters to the SM_RemovePort WMI method.


## -struct-fields




### -field PortWWN

A worldwide name (WWN) that indicates the port that should be removed from the list of ports whose events are reported to the WMI client.


### -field EventType

An event type value.


## -remarks



The WMI tool suite generates a declaration of the SM_RemovePort_IN structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_EventControl WMI class.



