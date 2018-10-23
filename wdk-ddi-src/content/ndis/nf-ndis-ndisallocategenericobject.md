---
UID: NF:ndis.NdisAllocateGenericObject
title: NdisAllocateGenericObject function
author: windows-driver-content
description: Components that do not have an NDIS handle use the NdisAllocateGenericObject function to allocate a generic NDIS object.
old-location: netvista\ndisallocategenericobject.htm
tech.root: netvista
ms.assetid: 166584fb-8a81-4a5b-93c9-3ad5348e15a7
ms.date: 05/02/2018
ms.keywords: NdisAllocateGenericObject, NdisAllocateGenericObject function [Network Drivers Starting with Windows Vista], ndis/NdisAllocateGenericObject, ndis_object_ref_bb08930d-d264-4580-be64-a48061ab8ad4.xml, netvista.ndisallocategenericobject
ms.topic: function
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
-	NdisAllocateGenericObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisAllocateGenericObject function


## -description


Components that do not have an NDIS handle use the 
  <b>NdisAllocateGenericObject</b> function to allocate a generic NDIS object.


## -parameters




### -param DriverObject [optional]

A driver object to associate with the generic object. This parameter can be <b>NULL</b>.


### -param Tag

The kernel memory tag that NDIS should use to allocate memory for the generic object.


### -param Size

The amount of memory, in bytes, to reserve for the caller. This does not include the size of the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff565680">NDIS_GENERIC_OBJECT</a> structure. Use the
     additional memory space for your own purposes. To access the additional memory, use 
     sizeof(NDIS_GENERIC_OBJECT) to skip over the generic object structure.


## -returns



<b>NdisAllocateGenericObject</b> returns a pointer to the NDIS_GENERIC_OBJECT that it allocated. If NDIS
     failed to create the object, the return value is <b>NULL</b>.




## -remarks



NDIS uses a generic object to manage resources that are allocated by a component that does not
    otherwise have an NDIS handle. Such a component uses the returned generic object pointer as an NDIS
    handle in some NDIS resource allocation APIs that require an NDIS handle.

NDIS drivers must call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561850">NdisFreeGenericObject</a> function to
    free a generic object that was created with 
    <b>NdisAllocateGenericObject</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff565680">NDIS_GENERIC_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561850">NdisFreeGenericObject</a>
 

 

