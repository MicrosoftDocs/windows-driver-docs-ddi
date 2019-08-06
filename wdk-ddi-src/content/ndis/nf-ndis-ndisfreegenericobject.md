---
UID: NF:ndis.NdisFreeGenericObject
title: NdisFreeGenericObject function (ndis.h)
description: Call the NdisFreeGenericObject function to free a generic object that was created with the NdisAllocateGenericObject function.
old-location: netvista\ndisfreegenericobject.htm
tech.root: netvista
ms.assetid: 02c0ea87-d25d-4363-85e3-e47c4c5d8a9b
ms.date: 05/02/2018
ms.keywords: NdisFreeGenericObject, NdisFreeGenericObject function [Network Drivers Starting with Windows Vista], ndis/NdisFreeGenericObject, ndis_object_ref_d796ffda-61f1-473d-98ea-5ad3570889e9.xml, netvista.ndisfreegenericobject
ms.topic: function
f1_keywords:
 - "ndis/NdisFreeGenericObject"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miscellaneous_Function, NdisAllocateGenericObject
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisFreeGenericObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisFreeGenericObject function


## -description


Call the 
  <b>NdisFreeGenericObject</b> function to free a generic object that was created with the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisallocategenericobject">
  NdisAllocateGenericObject</a> function.


## -parameters




### -param NdisObject

A pointer to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_generic_object">NDIS_GENERIC_OBJECT</a> structure to be
     freed.

## -returns



None




## -remarks



An NDIS handle is required to allocate some NDIS resources (for example, buffer pools). Components
    that do not otherwise have an NDIS handle use a pointer to an 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_generic_object">NDIS_GENERIC_OBJECT</a> structure as an NDIS
    handle. All resources that were allocated with this generic object pointer as the handle must be freed
    before freeing the generic object.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_generic_object">NDIS_GENERIC_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisallocategenericobject">NdisAllocateGenericObject</a>
 

 

