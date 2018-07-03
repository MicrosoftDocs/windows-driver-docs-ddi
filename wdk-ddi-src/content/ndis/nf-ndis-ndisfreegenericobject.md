---
UID: NF:ndis.NdisFreeGenericObject
title: NdisFreeGenericObject function
author: windows-driver-content
description: Call the NdisFreeGenericObject function to free a generic object that was created with the NdisAllocateGenericObject function.
old-location: netvista\ndisfreegenericobject.htm
old-project: netvista
ms.assetid: 02c0ea87-d25d-4363-85e3-e47c4c5d8a9b
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: NdisFreeGenericObject, NdisFreeGenericObject function [Network Drivers Starting with Windows Vista], ndis/NdisFreeGenericObject, ndis_object_ref_d796ffda-61f1-473d-98ea-5ad3570889e9.xml, netvista.ndisfreegenericobject
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	NdisFreeGenericObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisFreeGenericObject function


## -description


Call the 
  <b>NdisFreeGenericObject</b> function to free a generic object that was created with the 
  <a href="https://msdn.microsoft.com/166584fb-8a81-4a5b-93c9-3ad5348e15a7">
  NdisAllocateGenericObject</a> function.


## -parameters




### -param NdisObject

A pointer to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff565680">NDIS_GENERIC_OBJECT</a> structure to be
     freed.

## -returns



None




## -remarks



An NDIS handle is required to allocate some NDIS resources (for example, buffer pools). Components
    that do not otherwise have an NDIS handle use a pointer to an 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff565680">NDIS_GENERIC_OBJECT</a> structure as an NDIS
    handle. All resources that were allocated with this generic object pointer as the handle must be freed
    before freeing the generic object.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff565680">NDIS_GENERIC_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561603">NdisAllocateGenericObject</a>
 

 

