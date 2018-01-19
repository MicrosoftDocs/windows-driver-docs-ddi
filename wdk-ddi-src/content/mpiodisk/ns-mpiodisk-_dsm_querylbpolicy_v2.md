---
UID: NS:mpiodisk._DSM_QueryLBPolicy_V2
title: _DSM_QueryLBPolicy_V2
author: windows-driver-content
description: The DSM_QueryLBPolicy_V2 structure is used to query a LUN's current load balance policy. It is basically the same as the DSM_QueryLBPolicy structure except that it returns the load balance information by using the DSM_Load_Balance_Policy_V2 structure.
old-location: storage\dsm_querylbpolicy_v2.htm
old-project: storage
ms.assetid: f02f3442-e9c2-4f60-833d-e470de62118e
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _DSM_QueryLBPolicy_V2, DSM_QueryLBPolicy_V2, *PDSM_QueryLBPolicy_V2
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
req.alt-api: DSM_QueryLBPolicy_V2
req.alt-loc: mpiodisk.h
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
req.typenames: DSM_QueryLBPolicy_V2, *PDSM_QueryLBPolicy_V2
---

# _DSM_QueryLBPolicy_V2 structure



## -description
The DSM_QueryLBPolicy_V2 structure is used to query a LUN's current load balance policy. It is basically the same as the DSM_QueryLBPolicy structure except that it returns the load balance information by using the DSM_Load_Balance_Policy_V2 structure.



## -syntax

````
typedef struct _DSM_QueryLBPolicy_V2 {
  DSM_Load_Balance_Policy_V2 LoadBalancePolicy;
} DSM_QueryLBPolicy_V2, *PDSM_QueryLBPolicy_V2;
````


## -struct-fields

### -field LoadBalancePolicy

An instance of the DSM_Load_Balance_Policy_V2 structure that has information about the current load balance policy that is being applied by the DSM on the targeted pseudo-LUN.


## -remarks
