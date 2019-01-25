---
UID: NS:ndisndk._NDIS_OPEN_NDK_ADAPTER_PARAMETERS
title: "_NDIS_OPEN_NDK_ADAPTER_PARAMETERS" (ndisndk.h)
description: The NDIS_OPEN_NDK_ADAPTER_PARAMETERS structure specifies parameters to open an NDK adapter instance on the NDK-capable miniport adapter.
old-location: netvista\ndis_open_ndk_adapter_parameters.htm
tech.root: netvista
ms.assetid: AC8D4FA1-59E0-4934-A6C5-EA2E645C53FA
ms.date: 05/02/2018
ms.keywords: "*PNDIS_OPEN_NDK_ADAPTER_PARAMETERS, NDIS_OPEN_NDK_ADAPTER_PARAMETERS, NDIS_OPEN_NDK_ADAPTER_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_OPEN_NDK_ADAPTER_PARAMETERS, PNDIS_OPEN_NDK_ADAPTER_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_OPEN_NDK_ADAPTER_PARAMETERS, ndisndk/NDIS_OPEN_NDK_ADAPTER_PARAMETERS, ndisndk/PNDIS_OPEN_NDK_ADAPTER_PARAMETERS, netvista.ndis_open_ndk_adapter_parameters"
ms.topic: struct
req.header: ndisndk.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
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
-	ndisndk.h
api_name:
-	NDIS_OPEN_NDK_ADAPTER_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: NDIS_OPEN_NDK_ADAPTER_PARAMETERS, *PNDIS_OPEN_NDK_ADAPTER_PARAMETERS
---

# _NDIS_OPEN_NDK_ADAPTER_PARAMETERS structure


## -description


The <b>NDIS_OPEN_NDK_ADAPTER_PARAMETERS</b> structure specifies parameters to open an NDK adapter instance on the NDK-capable miniport adapter.


## -struct-fields




### -field Version

The version of the NDK provider interface (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439942">NDK_VERSION</a>) that is to be used. 

For NDIS 6.30 (Windows Server 2012), the major version number is 1. The  minor version number is 1.

For NDIS 6.40 (Windows Server 2012 R2), the major version number is 1. The  minor version number is 2.


### -field SwitchId

 


### -field VPortId

 




## -remarks



To open an NDK adapter, NDIS calls the <a href="https://msdn.microsoft.com/library/windows/hardware/hh440105">OPEN_NDK_ADAPTER_HANDLER</a> function and passes it a  pointer to an <b>NDIS_OPEN_NDK_ADAPTER_PARAMETERS</b> structure that defines the NDK adapter open parameters.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439942">NDK_VERSION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh440105">OPEN_NDK_ADAPTER_HANDLER</a>
 

 

