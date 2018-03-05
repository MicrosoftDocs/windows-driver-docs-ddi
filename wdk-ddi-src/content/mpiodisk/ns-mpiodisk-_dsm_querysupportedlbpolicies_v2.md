---
UID: NS:mpiodisk._DSM_QuerySupportedLBPolicies_V2
title: "_DSM_QuerySupportedLBPolicies_V2"
author: windows-driver-content
description: The DSM_QuerySupportedLBPolicies_V2 structure is used to query the list of load balance policies that are supported on the LUN.
old-location: storage\dsm_querysupportedlbpolicies_v2.htm
old-project: storage
ms.assetid: b62f60e2-9a5c-4346-8a77-985873a7ae20
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PDSM_QuerySupportedLBPolicies_V2, DSM_QuerySupportedLBPolicies_V2, DSM_QuerySupportedLBPolicies_V2 structure [Storage Devices], PDSM_QuerySupportedLBPolicies_V2, PDSM_QuerySupportedLBPolicies_V2 structure pointer [Storage Devices], _DSM_QuerySupportedLBPolicies_V2, mpiodisk/DSM_QuerySupportedLBPolicies_V2, mpiodisk/PDSM_QuerySupportedLBPolicies_V2, storage.dsm_querysupportedlbpolicies_v2, structs-scsibus_33717938-d010-4155-a87b-4fb94831315e.xml"
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
-	DSM_QuerySupportedLBPolicies_V2
product: Windows
targetos: Windows
req.typenames: DSM_QuerySupportedLBPolicies_V2, *PDSM_QuerySupportedLBPolicies_V2
---

# _DSM_QuerySupportedLBPolicies_V2 structure


## -description


The DSM_QuerySupportedLBPolicies_V2 structure is used to query the list of load balance policies that are supported on the LUN. It is basically the same as the DSM_QuerySupportedLBPolicies except that it passes back the supported policies as an array of DSM_Load_Balance_Policy_V2 structures instead of DSM_Load_Balance_Policy structures. The caller must direct the WMI call for querying to a pseudo-LUN that is addressed by the WMI instance name that corresponds to the pseudo-LUN. All DSMs must register and implement this class, even if they do not support any load balance policies for the devices they control.


## -syntax


````
typedef struct _DSM_QuerySupportedLBPolicies_V2 {
  ULONG                      SupportedLBPoliciesCount;
  ULONG                      Reserved;
  DSM_Load_Balance_Policy_V2 Supported_LB_Policies[1];
} DSM_QuerySupportedLBPolicies_V2, *PDSM_QuerySupportedLBPolicies_V2;
````


## -struct-fields




### -field SupportedLBPoliciesCount

An unsigned 32-bitfield that returns the number of load balance policies that are supported for the LUN by the controlling DSM.


### -field Reserved

Should be zero.


### -field Supported_LB_Policies

An array of DSM_Load_Balance_Policy_V2 structures, one for each of the supported load balance policies. The number of array elements will be the same as <i>SupportedLBPoliciesCount</i>. Each element of the array lists the supported load balance policy type. It is not expected that the element return path specifics.

