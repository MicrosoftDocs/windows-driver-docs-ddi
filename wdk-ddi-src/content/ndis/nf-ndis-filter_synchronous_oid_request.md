---
UID: NF:ndis.FILTER_SYNCHRONOUS_OID_REQUEST
title: FILTER_SYNCHRONOUS_OID_REQUEST function
author: windows-driver-content
description: This callback function is reserved.
old-location: netvista\filter_synchronous_oid_request.htm
old-project: netvista
ms.assetid: AC84B27B-6FBF-429D-A8FA-F3C8F583F738
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.filter_synchronous_oid_request, FilterSynchronousOidRequest function [Network Drivers Starting with Windows Vista], FilterSynchronousOidRequest, ndis/FilterSynchronousOidRequest, FILTER_SYNCHRONOUS_OID_REQUEST
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ndis.h
apiname:
-	FilterSynchronousOidRequest
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# FILTER_SYNCHRONOUS_OID_REQUEST function


## -description


<div class="alert"><b>Warning</b>  In Windows 10, version 1709, Synchronous OID requests are supported only for miniport and protocol drivers. Filter drivers cannot make Synchronous OID request calls in Windows 10, version 1709.</div><div> </div>This callback function is reserved.


## -syntax


````
NDIS_STATUS FilterSynchronousOidRequest(
          NDIS_HANDLE      FilterModuleContext,
  _Inout_ NDIS_OID_REQUEST *OidRequest,
  _Out_   PVOID            *CallContext
);
````


## -parameters




### -param FilterModuleContext

Reserved.


### -param OidRequest [in, out]

Reserved.


### -param CallContext [out]

Reserved.


## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/synchronous-oid-request-interface-in-ndis-6-80">Synchronous OID Request Interface in NDIS 6.80</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FILTER_SYNCHRONOUS_OID_REQUEST function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

