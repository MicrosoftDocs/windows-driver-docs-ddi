---
UID: NS:mpiodisk._DSM_QueryLBPolicy
title: _DSM_QueryLBPolicy (mpiodisk.h)
description: The DSM_QueryLBPolicy structure is used to query a LUN's current load balance policy.
old-location: storage\dsm_querylbpolicy.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["DSM_QueryLBPolicy structure"]
ms.keywords: "*PDSM_QueryLBPolicy, DSM_QueryLBPolicy, DSM_QueryLBPolicy structure [Storage Devices], PDSM_QueryLBPolicy, PDSM_QueryLBPolicy structure pointer [Storage Devices], _DSM_QueryLBPolicy, mpiodisk/DSM_QueryLBPolicy, mpiodisk/PDSM_QueryLBPolicy, storage.dsm_querylbpolicy, structs-scsibus_f1a0bedd-e5ba-474d-9a45-ae6a2863cfb3.xml"
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
targetos: Windows
req.typenames: DSM_QueryLBPolicy, *PDSM_QueryLBPolicy
f1_keywords:
 - _DSM_QueryLBPolicy
 - mpiodisk/_DSM_QueryLBPolicy
 - PDSM_QueryLBPolicy
 - mpiodisk/PDSM_QueryLBPolicy
 - DSM_QueryLBPolicy
 - mpiodisk/DSM_QueryLBPolicy
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - mpiodisk.h
api_name:
 - _DSM_QueryLBPolicy
 - PDSM_QueryLBPolicy
 - DSM_QueryLBPolicy
---

# _DSM_QueryLBPolicy structure


## -description

The DSM_QueryLBPolicy structure is used to query a LUN's current load balance policy.

## -struct-fields

### -field LoadBalancePolicy

An instance of a DSM_Load_Balance_Policy structure that has information about the current load balance policy that is being applied by the DSM on the targeted pseudo-LUN.

