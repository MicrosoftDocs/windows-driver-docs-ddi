---
UID: NF:ks.KsCreateTopologyNode
title: KsCreateTopologyNode function
author: windows-driver-content
description: The KsCreateTopologyNode function creates a handle to a topology node instance. The function can only be called at PASSIVE_LEVEL.
old-location: stream\kscreatetopologynode.htm
tech.root: stream
ms.assetid: aeed8086-b413-428c-b275-d555523b5503
ms.date: 04/23/2018
ms.keywords: KsCreateTopologyNode, KsCreateTopologyNode function [Streaming Media Devices], ks/KsCreateTopologyNode, ksfunc_15092cdb-3f97-4f13-a10e-9dbc92d20776.xml, stream.kscreatetopologynode
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ks.lib
-	ks.dll
api_name:
-	KsCreateTopologyNode
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsCreateTopologyNode function


## -description


The <b>KsCreateTopologyNode</b> function creates a handle to a topology node instance. The function can only be called at <b>PASSIVE_LEVEL</b>.


## -parameters




### -param ParentHandle [in]

Specifies the handle to the parent on which the node is created.


### -param NodeCreate [in]

Specifies topology node create parameters.


### -param DesiredAccess [in]

Specifies an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> indicating the desired access to the object. This is typically <b>GENERIC_READ</b> and/or <b>GENERIC_WRITE</b>.


### -param NodeHandle [out]

Location for the topology node handle.


## -returns



Returns <b>STATUS_SUCCESS</b>, or an error if unable to create a node. 




## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff563471">KSNODE_CREATE</a> structure describes the set of information used to create the node handle.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563471">KSNODE_CREATE</a>
 

 

