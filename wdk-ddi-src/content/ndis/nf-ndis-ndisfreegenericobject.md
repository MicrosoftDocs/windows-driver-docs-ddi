---
UID: NF:ndis.NdisFreeGenericObject
title: NdisFreeGenericObject function (ndis.h)
description: Call the NdisFreeGenericObject function to free a generic object that was created with the NdisAllocateGenericObject function.
old-location: netvista\ndisfreegenericobject.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisFreeGenericObject function"]
ms.keywords: NdisFreeGenericObject, NdisFreeGenericObject function [Network Drivers Starting with Windows Vista], ndis/NdisFreeGenericObject, ndis_object_ref_d796ffda-61f1-473d-98ea-5ad3570889e9.xml, netvista.ndisfreegenericobject
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
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisFreeGenericObject
 - ndis/NdisFreeGenericObject
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
---

# NdisFreeGenericObject function


## -description

Call the 
  <b>NdisFreeGenericObject</b> function to free a generic object that was created with the 
  <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocategenericobject">
  NdisAllocateGenericObject</a> function.

## -parameters

### -param NdisObject

A pointer to the 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_generic_object">NDIS_GENERIC_OBJECT</a> structure to be
     freed.

## -remarks

An NDIS handle is required to allocate some NDIS resources (for example, buffer pools). Components
    that do not otherwise have an NDIS handle use a pointer to an 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_generic_object">NDIS_GENERIC_OBJECT</a> structure as an NDIS
    handle. All resources that were allocated with this generic object pointer as the handle must be freed
    before freeing the generic object.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_generic_object">NDIS_GENERIC_OBJECT</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocategenericobject">NdisAllocateGenericObject</a>
