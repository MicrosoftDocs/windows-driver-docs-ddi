---
UID: NS:mpiodisk._DSM_QueryLBPolicy
title: "_DSM_QueryLBPolicy"
author: windows-driver-content
description: The DSM_QueryLBPolicy structure is used to query a LUN's current load balance policy.
old-location: storage\dsm_querylbpolicy.htm
old-project: storage
ms.assetid: f2ac985a-8fcb-48ad-b100-4137b5b1a777
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: mpiodisk/PDSM_QueryLBPolicy, *PDSM_QueryLBPolicy, mpiodisk/DSM_QueryLBPolicy, DSM_QueryLBPolicy structure [Storage Devices], _DSM_QueryLBPolicy, storage.dsm_querylbpolicy, structs-scsibus_f1a0bedd-e5ba-474d-9a45-ae6a2863cfb3.xml, PDSM_QueryLBPolicy structure pointer [Storage Devices], DSM_QueryLBPolicy, PDSM_QueryLBPolicy
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
-	DSM_QueryLBPolicy
product: Windows
targetos: Windows
req.typenames: "*PDSM_QueryLBPolicy, DSM_QueryLBPolicy"
---

# _DSM_QueryLBPolicy structure


## -description


The DSM_QueryLBPolicy structure is used to query a LUN's current load balance policy.


## -syntax


````
typedef struct _DSM_QueryLBPolicy {
  DSM_Load_Balance_Policy LoadBalancePolicy;
} DSM_QueryLBPolicy, *PDSM_QueryLBPolicy;
````


## -struct-fields




### -field LoadBalancePolicy

An instance of a DSM_Load_Balance_Policy structure that has information about the current load balance policy that is being applied by the DSM on the targeted pseudo-LUN.

