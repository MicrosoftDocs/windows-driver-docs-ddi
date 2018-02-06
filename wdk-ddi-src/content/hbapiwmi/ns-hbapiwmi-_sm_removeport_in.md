---
UID: NS:hbapiwmi._SM_RemovePort_IN
title: "_SM_RemovePort_IN"
author: windows-driver-content
description: The SM_RemovePort_IN structure is used to provide input parameters to the SM_RemovePort WMI method.
old-location: storage\sm_removeport_in.htm
old-project: storage
ms.assetid: b8eb6321-928f-4366-9553-c75900fa1ac6
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: SM_RemovePort_IN, _SM_RemovePort_IN, hbapiwmi/SM_RemovePort_IN, *PSM_RemovePort_IN, PSM_RemovePort_IN structure pointer [Storage Devices], structs-Fibre_0290cc86-0661-47ae-89db-3a3756c5d681.xml, SM_RemovePort_IN structure [Storage Devices], storage.sm_removeport_in, PSM_RemovePort_IN, hbapiwmi/PSM_RemovePort_IN
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
-	SM_RemovePort_IN
product: Windows
targetos: Windows
req.typenames: "*PSM_RemovePort_IN, SM_RemovePort_IN"
---

# _SM_RemovePort_IN structure


## -description


The SM_RemovePort_IN structure is used to provide input parameters to the SM_RemovePort WMI method.


## -syntax


````
typedef struct _SM_RemovePort_IN {
  UCHAR PortWWN[8];
  ULONG EventType;
} SM_RemovePort_IN, *PSM_RemovePort_IN;
````


## -struct-fields




### -field PortWWN

A worldwide name (WWN) that indicates the port that should be removed from the list of ports whose events are reported to the WMI client.


### -field EventType

An event type value.


## -remarks


The WMI tool suite generates a declaration of the SM_RemovePort_IN structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_EventControl WMI class.


