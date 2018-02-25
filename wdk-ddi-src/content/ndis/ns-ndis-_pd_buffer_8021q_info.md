---
UID: NS:ndis._PD_BUFFER_8021Q_INFO
title: "_PD_BUFFER_8021Q_INFO"
author: windows-driver-content
description: This structure contains the IEEE 802.1Q information.
old-location: netvista\pd_buffer_8021q_info.htm
old-project: netvista
ms.assetid: B5B2051E-C62F-4E3D-9C52-DE46145A2C24
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , ,, 0, 1, 2, 8, B, D, E, F, I, N, O, P, PD_BUFFER_8021Q_INFO, PD_BUFFER_8021Q_INFO structure [Network Drivers Starting with Windows Vista], PPD_BUFFER_8021Q_INFO, PPD_BUFFER_8021Q_INFO structure pointer [Network Drivers Starting with Windows Vista], Q, R, U, _, _PD_BUFFER_8021Q_INFO, ndis/PD_BUFFER_8021Q_INFO, ndis/PPD_BUFFER_8021Q_INFO, netvista.pd_buffer_8021q_info"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.irql: See Remarks section
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ndis.h
apiname:
-	PD_BUFFER_8021Q_INFO
product: Windows
targetos: Windows
req.typenames: PD_BUFFER_8021Q_INFO
---

# _PD_BUFFER_8021Q_INFO structure


## -description


This structure contains the IEEE 802.1Q information.


## -syntax


````
typedef struct _PD_BUFFER_8021Q_INFO {
  UINT16 UserPriority  :3;
  UINT16 CanonicalFormatId  :1;
  UINT16 VlanId  :12;
} PD_BUFFER_8021Q_INFO, *PPD_BUFFER_8021Q_INFO;
````


## -struct-fields




### -field UserPriority

The user priority.


### -field CanonicalFormatId

The canonical format ID.


### -field VlanId

The virtual LAN ID.

