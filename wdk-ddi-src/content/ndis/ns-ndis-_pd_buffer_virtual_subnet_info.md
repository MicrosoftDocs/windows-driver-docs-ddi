---
UID: NS:ndis._PD_BUFFER_VIRTUAL_SUBNET_INFO
title: "_PD_BUFFER_VIRTUAL_SUBNET_INFO"
author: windows-driver-content
description: This structure contains the virtual subnet information.
old-location: netvista\pd_buffer_virtual_subnet_info.htm
old-project: netvista
ms.assetid: 569424A2-4279-4758-A6F1-402D25F9B04F
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , ,, A, B, D, E, F, I, L, N, O, P, PD_BUFFER_VIRTUAL_SUBNET_INFO, PD_BUFFER_VIRTUAL_SUBNET_INFO structure [Network Drivers Starting with Windows Vista], PPD_BUFFER_VIRTUAL_SUBNET_INFO, PPD_BUFFER_VIRTUAL_SUBNET_INFO structure pointer [Network Drivers Starting with Windows Vista], R, S, T, U, V, _, _PD_BUFFER_VIRTUAL_SUBNET_INFO, ndis/PD_BUFFER_VIRTUAL_SUBNET_INFO, ndis/PPD_BUFFER_VIRTUAL_SUBNET_INFO, netvista.pd_buffer_virtual_subnet_info"
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
-	PD_BUFFER_VIRTUAL_SUBNET_INFO
product: Windows
targetos: Windows
req.typenames: PD_BUFFER_VIRTUAL_SUBNET_INFO
---

# _PD_BUFFER_VIRTUAL_SUBNET_INFO structure


## -description


This structure contains the virtual subnet information.


## -syntax


````
typedef struct _PD_BUFFER_VIRTUAL_SUBNET_INFO {
  UINT32 VirtualSubnetId  :24;
  UINT32 Reserved  :8;
} PD_BUFFER_VIRTUAL_SUBNET_INFO, *PPD_BUFFER_VIRTUAL_SUBNET_INFO;
````


## -struct-fields




### -field VirtualSubnetId

The virtual subnet ID.


### -field Reserved

Reserved.

