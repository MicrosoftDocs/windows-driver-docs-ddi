---
UID: NS:mpiodisk._DSM_Load_Balance_Policy_V2
title: "_DSM_Load_Balance_Policy_V2"
author: windows-driver-content
description: The DSM_Load_Balance_Policy_V2 structure is used to represent a load balance policy that is applied to a LUN.
old-location: storage\dsm_load_balance_policy_v2.htm
old-project: storage
ms.assetid: b1522320-110c-46dc-be50-df7c05d61351
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PDSM_Load_Balance_Policy_V2, DSM_Load_Balance_Policy_V2, DSM_Load_Balance_Policy_V2 structure [Storage Devices], PDSM_Load_Balance_Policy_V2, PDSM_Load_Balance_Policy_V2 structure pointer [Storage Devices], _DSM_Load_Balance_Policy_V2, mpiodisk/DSM_Load_Balance_Policy_V2, mpiodisk/PDSM_Load_Balance_Policy_V2, storage.dsm_load_balance_policy_v2, structs-scsibus_f53c7618-49ab-452b-97e7-402d9392a419.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	mpiodisk.h
api_name:
-	DSM_Load_Balance_Policy_V2
product: Windows
targetos: Windows
req.typenames: DSM_Load_Balance_Policy_V2, *PDSM_Load_Balance_Policy_V2
---

# _DSM_Load_Balance_Policy_V2 structure


## -description


The DSM_Load_Balance_Policy_V2 structure is used to represent a load balance policy that is applied to a LUN. It is similar to the DSM_Load_Balance_Policy structure, except that it uses the MPIO_DSM_Path_V2 structure to capture and expose path information.


## -syntax


````
typedef struct _DSM_Load_Balance_Policy_V2 {
  ULONG            Version;
  ULONG            LoadBalancePolicy;
  ULONG            DSMPathCount;
  ULONG            Reserved;
  MPIO_DSM_Path_V2 DSM_Paths[1];
} DSM_Load_Balance_Policy_V2, *PDSM_Load_Balance_Policy_V2;
````


## -struct-fields




### -field Version

The version of WMI class supported. Set to 2.


### -field LoadBalancePolicy

An unsigned 32-bitfield that represents the load balance policy type that is currently being applied to the LUN if the LUN is being queried, or the new policy to apply to the LUN if the LUN is being set.


### -field DSMPathCount

An unsigned 32-bitfield that represents the number of paths that expose the LUN's instances.


### -field Reserved

Should be zero.


### -field DSM_Paths

An array of MPIO_DSM_Path_V2 structures that represent path attributes for each of the LUN's instances.

