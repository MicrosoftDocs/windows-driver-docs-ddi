---
UID: NS:windot11._DOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS
title: _DOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS
author: windows-driver-content
description: The DOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS structure indicates the success of the discovery of networks in the offload list.
old-location: netvista\dot11_offload_network_status_parameters.htm
old-project: netvista
ms.assetid: 4A911BFF-5515-4E51-953D-86CECA123DA0
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS, *PDOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS, DOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Versions: Supported in Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS
req.alt-loc: Windot11.h
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
req.typenames: *PDOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS, DOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS
req.product: Windows 10 or later.
---

# _DOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS structure



## -description

## -syntax

````
typedef struct _DOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  NDIS_STATUS        Status;
} DOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS, *PDOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS;
````


## -struct-fields

### -field Header

The type, revision, and size of the DOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS structure. The required settings for the members of <b>Header</b> are the following.

<table>
<tr>
<th>Member</th>
<th>Setting</th>
</tr>
<tr>
<td><b>Type</b></td>
<td>NDIS_OBJECT_TYPE_DEFAULT</td>
</tr>
<tr>
<td><b>Revision</b></td>
<td>DOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_OFFLOAD_NETWORK_STATUS_PARAMETERS_REVISION_1</td>
</tr>
</table>
 


### -field Status

This must be STATUS_SUCCESS.


## -remarks
