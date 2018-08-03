---
UID: NF:ndis.NdisFreeCloneOidRequest
title: NdisFreeCloneOidRequest function
author: windows-driver-content
description: The NdisFreeCloneOidRequest function frees a cloned NDIS_OID_REQUEST structure.
old-location: netvista\ndisfreecloneoidrequest.htm
tech.root: netvista
ms.assetid: f610fdf7-5c0e-41e0-994b-6da575541fca
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: NdisFreeCloneOidRequest, NdisFreeCloneOidRequest function [Network Drivers Starting with Windows Vista], ndis/NdisFreeCloneOidRequest, ndis_request_ref_450d80e2-3414-4c02-aca1-848c75f824a6.xml, netvista.ndisfreecloneoidrequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_OID_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisFreeCloneOidRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisFreeCloneOidRequest function


## -description


The 
  <b>NdisFreeCloneOidRequest</b> function frees a cloned 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a> structure.


## -parameters




### -param SourceHandle [in]

An NDIS handle that identifies a filter module or an intermediate driver's protocol
     binding.


### -param Request [in]

A pointer to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a> structure that is to be
     freed.


## -returns



None




## -remarks



An NDIS intermediate driver or filter driver calls 
    <b>NdisFreeCloneOidRequest</b> to free an NDIS_OID_REQUEST structure that was allocated by calling the 
    <a href="https://msdn.microsoft.com/426ff4f4-7924-4115-9f66-b4152e2ba5bb">
    NdisAllocateCloneOidRequest</a> function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560706">NdisAllocateCloneOidRequest</a>
 

 

