---
UID: NF:ndis.FILTER_SYNCHRONOUS_OID_REQUEST
title: FILTER_SYNCHRONOUS_OID_REQUEST function
author: windows-driver-content
description: This callback function is reserved.
old-location: netvista\filter_synchronous_oid_request.htm
old-project: netvista
ms.assetid: AC84B27B-6FBF-429D-A8FA-F3C8F583F738
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: FILTER_SYNCHRONOUS_OID_REQUEST, FilterSynchronousOidRequest, FilterSynchronousOidRequest function [Network Drivers Starting with Windows Vista], ndis/FilterSynchronousOidRequest, netvista.filter_synchronous_oid_request
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ndis.h
api_name:
-	FilterSynchronousOidRequest
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# FILTER_SYNCHRONOUS_OID_REQUEST function


## -description


<div class="alert"><b>Warning</b>  In Windows 10, version 1709, Synchronous OID requests are supported only for miniport and protocol drivers. Filter drivers cannot make Synchronous OID request calls in Windows 10, version 1709.</div><div> </div>This callback function is reserved.


## -parameters




### -param FilterModuleContext

Reserved.


### -param OidRequest [in, out]

Reserved.


### -param CallContext [out]

Reserved.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/synchronous-oid-request-interface-in-ndis-6-80">Synchronous OID Request Interface in NDIS 6.80</a>
 

 

