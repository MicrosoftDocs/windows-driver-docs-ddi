---
UID: NF:ndis.FILTER_SYNCHRONOUS_OID_REQUEST_COMPLETE
title: FILTER_SYNCHRONOUS_OID_REQUEST_COMPLETE function
author: windows-driver-content
description: This callback function is reserved.
old-location: netvista\filter_synchronous_oid_request_complete.htm
old-project: netvista
ms.assetid: E0749F52-CC7C-484D-8350-1986154957C1
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: FILTER_SYNCHRONOUS_OID_REQUEST_COMPLETE, FilterSynchronousOidRequestComplete, FilterSynchronousOidRequestComplete function [Network Drivers Starting with Windows Vista], ndis/FilterSynchronousOidRequestComplete, netvista.filter_synchronous_oid_request_complete
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
-	FilterSynchronousOidRequestComplete
product:
- Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# FILTER_SYNCHRONOUS_OID_REQUEST_COMPLETE function


## -description


<div class="alert"><b>Warning</b>  In Windows 10, version 1709, Synchronous OID requests are supported only for miniport and protocol drivers. Filter drivers cannot make Synchronous OID request calls in Windows 10, version 1709.</div><div> </div>This callback function is reserved.


## -parameters




### -param FilterModuleContext [in]

Reserved.


### -param OidRequest [in, out]

Reserved.


### -param Status [in, out]

Reserved.


### -param CallContext [in]

Reserved.


## -returns



This function does not return a value.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/synchronous-oid-request-interface-in-ndis-6-80">Synchronous OID Request Interface in NDIS 6.80</a>
 

 

