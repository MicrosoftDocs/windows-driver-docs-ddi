---
UID: NF:ndis.NdisFDeregisterFilterDriver
title: NdisFDeregisterFilterDriver function (ndis.h)
description: A filter drivers calls the NdisFDeregisterFilterDriver function to release resources that it previously allocated with the NdisFRegisterFilterDriver function.
old-location: netvista\ndisfderegisterfilterdriver.htm
tech.root: netvista
ms.assetid: f97ecce3-73b9-4c51-b4a4-e114420af2c9
ms.date: 05/02/2018
ms.keywords: NdisFDeregisterFilterDriver, NdisFDeregisterFilterDriver function [Network Drivers Starting with Windows Vista], filter_ndis_functions_ref_d158c9c1-1e83-464f-b00a-421b658c8c32.xml, ndis/NdisFDeregisterFilterDriver, netvista.ndisfderegisterfilterdriver
ms.topic: function
f1_keywords:
 - "ndis/NdisFDeregisterFilterDriver"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Filter_Driver_Function, NdisFDeregisterFilterDriver
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisFDeregisterFilterDriver
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisFDeregisterFilterDriver function


## -description


A filter drivers calls the
  <b>NdisFDeregisterFilterDriver</b> function to release resources that it previously allocated with the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfregisterfilterdriver">
  NdisFRegisterFilterDriver</a> function.


## -parameters




### -param NdisFilterDriverHandle [in]

The filter driver handle that identifies this filter driver. NDIS returned the handle to the
     filter driver in a call to 
     <b>NdisFRegisterFilterDriver</b>.


## -remarks



A filter driver must call 
    <b>NdisFDeregisterFilterDriver</b> from its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/unloading-a-filter-driver">FilterDriverUnload</a> routine.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/unloading-a-filter-driver">FilterDriverUnload</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfregisterfilterdriver">NdisFRegisterFilterDriver</a>
 

 

