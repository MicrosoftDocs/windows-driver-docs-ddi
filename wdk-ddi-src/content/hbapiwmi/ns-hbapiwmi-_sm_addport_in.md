---
UID: NS:hbapiwmi._SM_AddPort_IN
title: "_SM_AddPort_IN"
author: windows-driver-content
description: The SM_AddPort_IN structure is used to provide input parameters to the SM_AddPort WMI method.
old-location: storage\sm_addport_in.htm
old-project: storage
ms.assetid: 29b05fa7-0393-47df-a77e-63745c0cd1e1
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PSM_AddPort_IN, PSM_AddPort_IN, PSM_AddPort_IN structure pointer [Storage Devices], SM_AddPort_IN, SM_AddPort_IN structure [Storage Devices], _SM_AddPort_IN, hbapiwmi/PSM_AddPort_IN, hbapiwmi/SM_AddPort_IN, storage.sm_addport_in, structs-Fibre_c9c9fceb-e4ec-414c-98f8-e9867b69add5.xml"
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
-	SM_AddPort_IN
product: Windows
targetos: Windows
req.typenames: SM_AddPort_IN, *PSM_AddPort_IN
---

# _SM_AddPort_IN structure


## -description


The SM_AddPort_IN structure is used to provide input parameters to the SM_AddPort WMI method.


## -syntax


````
typedef struct _SM_AddPort_IN {
  UCHAR PortWWN[8];
  ULONG EventType;
} SM_AddPort_IN, *PSM_AddPort_IN;
````


## -struct-fields




### -field PortWWN

A worldwide name (WWN) that indicates the port whose events are to be reported.


### -field EventType

An event type value.

