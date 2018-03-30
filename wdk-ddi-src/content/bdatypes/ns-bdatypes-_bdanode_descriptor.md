---
UID: NS:bdatypes._BDANODE_DESCRIPTOR
title: "_BDANODE_DESCRIPTOR"
author: windows-driver-content
description: The BDANODE_DESCRIPTOR structure describes a BDA node.
old-location: stream\bdanode_descriptor.htm
old-project: stream
ms.assetid: 324eddca-f619-44e2-b32f-34cefd4c9cdc
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PBDANODE_DESCRIPTOR, BDANODE_DESCRIPTOR, BDANODE_DESCRIPTOR structure [Streaming Media Devices], PBDANODE_DESCRIPTOR, PBDANODE_DESCRIPTOR structure pointer [Streaming Media Devices], _BDANODE_DESCRIPTOR, bdaref_0610ecfc-d15b-4031-9d88-b041ef21e2fb.xml, bdatypes/BDANODE_DESCRIPTOR, bdatypes/PBDANODE_DESCRIPTOR, stream.bdanode_descriptor"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bdatypes.h
api_name:
-	BDANODE_DESCRIPTOR
product: Windows
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

GUID that describes the node's function. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff556529">BDA Node Category GUIDs</a> for a list of these GUIDs.


### -field guidName

GUID that can be used to store a string containing the name of the node. Applications can search the registry for this GUID to obtain the node's name and then can display the name. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556529">BDA Node Category GUIDs</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563473">KSNODE_DESCRIPTOR</a>
 

 

