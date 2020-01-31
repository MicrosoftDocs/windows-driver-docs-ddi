---
UID: NS:ntddndis._NDIS_NDK_LOCAL_ENDPOINT_ENTRY
title: _NDIS_NDK_LOCAL_ENDPOINT_ENTRY (ntddndis.h)
description: The NDIS_NDK_LOCAL_ENDPOINT_ENTRY structure specifies an ND local endpoint entry for an ND local endpoint on a miniport adapter.
old-location: netvista\ndis_ndk_local_endpoint_entry.htm
tech.root: netvista
ms.assetid: 83B88D3D-8FBF-4DC1-8A73-FAB306281F36
ms.date: 05/02/2018
ms.keywords: NDIS_NDK_LOCAL_ENDPOINT_ENTRY, NDIS_NDK_LOCAL_ENDPOINT_ENTRY structure [Network Drivers Starting with Windows Vista], _NDIS_NDK_LOCAL_ENDPOINT_ENTRY, netvista.ndis_ndk_local_endpoint_entry, ntddndis/NDIS_NDK_LOCAL_ENDPOINT_ENTRY
f1_keywords:
 - "ntddndis/NDIS_NDK_LOCAL_ENDPOINT_ENTRY"
req.header: ntddndis.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddndis.h
api_name:
- NDIS_NDK_LOCAL_ENDPOINT_ENTRY
product:
- Windows
targetos: Windows
req.typenames: NDIS_NDK_LOCAL_ENDPOINT_ENTRY
---

# _NDIS_NDK_LOCAL_ENDPOINT_ENTRY structure


## -description


The <b>NDIS_NDK_LOCAL_ENDPOINT_ENTRY</b> structure specifies an ND  local endpoint entry for an ND  local endpoint on a miniport adapter.


## -struct-fields




### -field Local

The local IP address and port.


### -field UserModeOwner

A BOOLEAN value that is TRUE if the connection is an NDS user-mode connection, or FALSE if it is an NDK kernel-mode connection.


### -field Listener

A BOOLEAN value that  is TRUE if the connection is a listener or FALSE if it is a shared endpoint.


### -field OwnerPid

A process identifier for an NDS user-mode connection.


## -remarks



The NDIS_NDK_LOCAL_ENDPOINT_ENTRY structure is used in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_ndk_local_endpoints">NDIS_NDK_LOCAL_ENDPOINTS</a> structure to specify an array of local endpoints.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_ndk_local_endpoints">NDIS_NDK_LOCAL_ENDPOINTS</a>
 

 

