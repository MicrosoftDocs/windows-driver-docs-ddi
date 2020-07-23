---
UID: NS:bdatypes._BDANODE_DESCRIPTOR
title: _BDANODE_DESCRIPTOR (bdatypes.h)
description: The BDANODE_DESCRIPTOR structure describes a BDA node.
old-location: stream\bdanode_descriptor.htm
tech.root: stream
ms.assetid: 324eddca-f619-44e2-b32f-34cefd4c9cdc
ms.date: 04/23/2018
keywords: ["_BDANODE_DESCRIPTOR structure"]
ms.keywords: "*PBDANODE_DESCRIPTOR, BDANODE_DESCRIPTOR, BDANODE_DESCRIPTOR structure [Streaming Media Devices], PBDANODE_DESCRIPTOR, PBDANODE_DESCRIPTOR structure pointer [Streaming Media Devices], _BDANODE_DESCRIPTOR, bdaref_0610ecfc-d15b-4031-9d88-b041ef21e2fb.xml, bdatypes/BDANODE_DESCRIPTOR, bdatypes/PBDANODE_DESCRIPTOR, stream.bdanode_descriptor"
f1_keywords:
 - "bdatypes/BDANODE_DESCRIPTOR"
 - "BDANODE_DESCRIPTOR"
req.header: bdatypes.h
req.include-header: Bdatypes.h
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
- bdatypes.h
api_name:
- BDANODE_DESCRIPTOR
targetos: Windows
req.typenames: BDANODE_DESCRIPTOR, *PBDANODE_DESCRIPTOR
---

# _BDANODE_DESCRIPTOR structure


## -description


The BDANODE_DESCRIPTOR structure describes a BDA node. 


## -struct-fields




### -field ulBdaNodeType

The node type as the BDA template topology identifies it. The BDA node-type identifier typically corresponds to the index of the element in the zero-based array of node types. This array of node types is an array of KSNODE_DESCRIPTOR structures. 


### -field guidFunction

GUID that describes the node's function. See <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/bda-node-category-guids">BDA Node Category GUIDs</a> for a list of these GUIDs.


### -field guidName

GUID that can be used to store a string containing the name of the node. Applications can search the registry for this GUID to obtain the node's name and then can display the name. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/bda-node-category-guids">BDA Node Category GUIDs</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksnode_descriptor">KSNODE_DESCRIPTOR</a>
 

 

