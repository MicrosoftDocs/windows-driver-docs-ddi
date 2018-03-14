---
UID: NS:bdamedia.KSP_NODE_ESPID
title: KSP_NODE_ESPID
author: windows-driver-content
description: The KSP_NODE_ESPID structure describes property and node type for an Entitlement Control Message (ECM) map node along with the packet identifier (PID) for an elementary stream that the ECM map node processes.
old-location: stream\ksp_node_espid.htm
old-project: stream
ms.assetid: c5d0dbd8-bcce-436b-8fa7-bcb2b5c4ba59
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSP_NODE_ESPID, KSP_NODE_ESPID, KSP_NODE_ESPID structure [Streaming Media Devices], PKSP_NODE_ESPID, PKSP_NODE_ESPID structure pointer [Streaming Media Devices], bdamedia/KSP_NODE_ESPID, bdamedia/PKSP_NODE_ESPID, bdaref_aef92a8d-df0e-4283-b06a-4ece33b91809.xml, stream.ksp_node_espid"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bdamedia.h
req.include-header: Bdamedia.h
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
-	bdamedia.h
api_name:
-	KSP_NODE_ESPID
product: Windows
targetos: Windows
req.typenames: KSP_NODE_ESPID, *PKSP_NODE_ESPID
---

# KSP_NODE_ESPID structure


## -description


The KSP_NODE_ESPID structure describes property and node type for an Entitlement Control Message (ECM) map node along with the packet identifier (PID) for an elementary stream that the ECM map node processes.


## -syntax


````
typedef struct {
  KSP_NODE Property;
  ULONG    EsPid;
} KSP_NODE_ESPID, *PKSP_NODE_ESPID;
````


## -struct-fields




### -field Property

KSP_NODE structure that describes a property and node type.


### -field EsPid

Packet identifier (PID) that identifies packets in the elementary stream.


## -see-also

<a href="..\ks\ns-ks-ksp_node.md">KSP_NODE</a>



 

 


