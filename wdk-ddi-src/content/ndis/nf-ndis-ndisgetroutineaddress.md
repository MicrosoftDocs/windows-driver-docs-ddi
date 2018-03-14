---
UID: NF:ndis.NdisGetRoutineAddress
title: NdisGetRoutineAddress function
author: windows-driver-content
description: The NdisGetRoutineAddress function returns the address of a routine given the routine's name.
old-location: netvista\ndisgetroutineaddress.htm
old-project: netvista
ms.assetid: 98257b56-e586-41e7-80c3-f9f96d471125
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisGetRoutineAddress, NdisGetRoutineAddress function [Network Drivers Starting with Windows Vista], ndis/NdisGetRoutineAddress, ndis_sysinfo_ref_d2259157-f4fd-4fd8-b86e-f685ab4213d5.xml, netvista.ndisgetroutineaddress
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisGetRoutineAddress (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisGetRoutineAddress (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miscellaneous_Function
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisGetRoutineAddress
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisGetRoutineAddress function


## -description


The 
  <b>NdisGetRoutineAddress</b> function returns the address of a routine given the routine's name.


## -syntax


````
PVOID NdisGetRoutineAddress(
  _In_ PNDIS_STRING NdisRoutineName
);
````


## -parameters




### -param NdisRoutineName [in]

A pointer to a 
     <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that specifies the
     string that contains the name of a routine.


## -returns



Returns the address of the routine whose name is specified at 
     <i>NdisRoutineName</i> if the routine is available; otherwise, <b>NULL</b>.




## -remarks



An NDIS driver can use 
    <b>NdisGetRoutineAddress</b> to obtain the address of an exported NDIS routine. The driver can then use
    this address to call the NDIS routine.

An NDIS driver can use 
    <b>NdisGetRoutineAddress</b> if the driver must remain backward compatible. For example, if such a driver
    imports an NDIS routine that is not exported by the version of NDIS that is currently running, the I/O
    manager will not load the driver on the operating system. However, the driver can first use 
    <b>NdisGetRoutineAddress</b> to determine whether the routine is available in the version of NDIS that is
    currently running. If available, the address of the routine is returned. The driver can then use the
    address to call the routine. If not available, <b>NULL</b> is returned. The driver cannot call the routine, but
    the driver still loads on the operating system.

No performance improvement is gained by using the address that is returned by 
    <b>NdisGetRoutineAddress</b> instead of calling the specified routine by name. Therefore, do not write an
    NDIS driver to use 
    <b>NdisGetRoutineAddress</b> if you know that the NDIS version with which the driver will run exports the
    specified routine.

Typically, an NDIS driver calls 
    <b>NdisGetRoutineAddress</b> in its 
    <a href="..\wudfwdm\nc-wudfwdm-driver_initialize.md">DriverEntry</a> routine.




## -see-also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\wudfwdm\nc-wudfwdm-driver_initialize.md">DriverEntry</a>



 

 


