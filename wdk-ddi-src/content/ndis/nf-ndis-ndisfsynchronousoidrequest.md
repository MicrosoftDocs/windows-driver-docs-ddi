---
UID: NF:ndis.NdisFSynchronousOidRequest
title: NdisFSynchronousOidRequest function
author: windows-driver-content
description: This function is reserved.
old-location: netvista\ndisfsynchronousoidrequest.htm
old-project: netvista
ms.assetid: 01B625EB-AB6D-496F-95F2-22845460324A
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NdisFSynchronousOidRequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisFSynchronousOidRequest
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisFSynchronousOidRequest function



## -description

## -syntax

````
NDIS_STATUS NdisFSynchronousOidRequest(
  _In_ NDIS_HANDLE      NdisFilterModuleHandle,
  _In_ NDIS_OID_REQUEST OidRequest
);
````


## -parameters

### -param NdisFilterModuleHandle [in]

Reserved.


### -param OidRequest [in]

Reserved.


## -remarks
