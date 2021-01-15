---
UID: NS:mpiodisk._DSM_Load_Balance_Policy
title: _DSM_Load_Balance_Policy (mpiodisk.h)
description: The DSM_Load_Balance_Policy structure is used to represent a load balance policy that is applied to a LUN.
old-location: storage\dsm_load_balance_policy.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["DSM_Load_Balance_Policy structure"]
ms.keywords: "*PDSM_Load_Balance_Policy, DSM_Load_Balance_Policy, DSM_Load_Balance_Policy structure [Storage Devices], PDSM_Load_Balance_Policy, PDSM_Load_Balance_Policy structure pointer [Storage Devices], _DSM_Load_Balance_Policy, mpiodisk/DSM_Load_Balance_Policy, mpiodisk/PDSM_Load_Balance_Policy, storage.dsm_load_balance_policy, structs-scsibus_f6e03429-a591-41f0-9890-e513479f8896.xml"
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
req.typenames: DSM_Load_Balance_Policy, *PDSM_Load_Balance_Policy
f1_keywords:
 - _DSM_Load_Balance_Policy
 - mpiodisk/_DSM_Load_Balance_Policy
 - PDSM_Load_Balance_Policy
 - mpiodisk/PDSM_Load_Balance_Policy
 - DSM_Load_Balance_Policy
 - mpiodisk/DSM_Load_Balance_Policy
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - mpiodisk.h
api_name:
 - _DSM_Load_Balance_Policy
 - PDSM_Load_Balance_Policy
 - DSM_Load_Balance_Policy
---

# _DSM_Load_Balance_Policy structure


## -description

The DSM_Load_Balance_Policy structure is used to represent a load balance policy that is applied to a LUN.

## -struct-fields

### -field Version

The version of WMI class supported. Set to 1.

### -field LoadBalancePolicy

An unsigned 32-bitfield that represents the load balance policy type that is currently being applied to the LUN if the LUN is queried, or the new policy to apply to the LUN if the LUN is being set.

### -field DSMPathCount

An unsigned 32-bitfield that represents the number of paths that expose the LUN's instances.

### -field Reserved

Should be zero.

### -field DSM_Paths

An array of MPIO_DSM_Path structures that represent path attributes for each of the LUN's instances.

