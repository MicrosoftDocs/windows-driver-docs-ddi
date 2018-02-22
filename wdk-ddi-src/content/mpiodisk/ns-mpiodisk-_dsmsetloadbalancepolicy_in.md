---
UID: NS:mpiodisk._DsmSetLoadBalancePolicy_IN
title: "_DsmSetLoadBalancePolicy_IN"
author: windows-driver-content
description: The DsmSetLoadBalancePolicy_IN structure provides an input parameter to the DsmSetLoadBalancePolicy method.
old-location: storage\dsmsetloadbalancepolicy_in.htm
old-project: storage
ms.assetid: 1a249c0e-1b8d-4c50-9b01-03bfe84e0937
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "_DsmSetLoadBalancePolicy_IN, DsmSetLoadBalancePolicy_IN structure [Storage Devices], *PDsmSetLoadBalancePolicy_IN, storage.dsmsetloadbalancepolicy_in, mpiodisk/DsmSetLoadBalancePolicy_IN, PDsmSetLoadBalancePolicy_IN structure pointer [Storage Devices], structs-scsibus_f8d1e2b3-b630-45df-91f7-d564910f83d0.xml, DsmSetLoadBalancePolicy_IN, mpiodisk/PDsmSetLoadBalancePolicy_IN, PDsmSetLoadBalancePolicy_IN"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: mpiodisk.h
req.include-header: Mpiowmi.h
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
-	mpiodisk.h
apiname:
-	DsmSetLoadBalancePolicy_IN
product: Windows
targetos: Windows
req.typenames: "*PDsmSetLoadBalancePolicy_IN, DsmSetLoadBalancePolicy_IN"
---

# _DsmSetLoadBalancePolicy_IN structure


## -description


The DsmSetLoadBalancePolicy_IN structure provides an input parameter to the DsmSetLoadBalancePolicy method.


## -syntax


````
typedef struct _DsmSetLoadBalancePolicy_IN {
  DSM_Load_Balance_Policy LoadBalancePolicy;
} DsmSetLoadBalancePolicy_IN, *PDsmSetLoadBalancePolicy_IN;
````


## -struct-fields




### -field LoadBalancePolicy

A structure of type DSM_Load_Balance_Policy.

