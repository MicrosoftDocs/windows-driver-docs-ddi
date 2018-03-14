---
UID: NF:ndis.NdisIMGetBindingContext
title: NdisIMGetBindingContext function
author: windows-driver-content
description: The NdisIMGetBindingContext function allows an NDIS protocol driver to access the device context area, which was created by an underlying intermediate driver, for a virtual miniport to which the higher level protocol driver is bound.
old-location: netvista\ndisimgetbindingcontext.htm
old-project: netvista
ms.assetid: fc0668b3-9242-4d30-9dc9-820f6d596d6c
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisIMGetBindingContext, NdisIMGetBindingContext function [Network Drivers Starting with Windows Vista], intermediate_ref_ef5b6cf4-209a-4e51-be20-2e0e7bcc1ac8.xml, ndis/NdisIMGetBindingContext, netvista.ndisimgetbindingcontext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisIMGetBindingContext (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisIMGetBindingContext (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_IM_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "< DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisIMGetBindingContext
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisIMGetBindingContext function


## -description


The 
  <b>NdisIMGetBindingContext</b> function allows an NDIS protocol driver to access the device context area,
  which was created by an underlying intermediate driver, for a virtual miniport to which the higher level
  protocol driver is bound.


## -syntax


````
NDIS_HANDLE NdisIMGetBindingContext(
  _In_ NDIS_HANDLE NdisBindingHandle
);
````


## -parameters




### -param NdisBindingHandle [in]

The binding handle that the 
     <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a> function returned at
     the 
     <i>NdisBindingHandle</i> parameter that identifies the virtual miniport of the next lower intermediate
     driver to which the caller is bound.


## -returns



<b>NdisIMGetBindingContext</b> returns a handle to the device context area for the given virtual
     miniport, or it returns <b>NULL</b> if no such context area exists.




## -remarks



A protocol driver or intermediate driver can call 
    <b>NdisIMGetBindingContext</b> from its 
    <a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a> function to
    access the device context for a virtual miniport to which it is bound. The device context provides a
    common context area for all overlying protocol drivers that are bound to the same underlying intermediate
    driver.

Such a device context area was allocated and defined by the lower level NDIS intermediate driver and
    passed to NDIS in a call to the 
    <a href="..\ndis\nf-ndis-ndisiminitializedeviceinstanceex.md">
    NdisIMInitializeDeviceInstanceEx</a> function.

All protocol drivers that call 
    <b>NdisIMGetBindingContext</b> can safely assume that the underlying intermediate driver allocated its
    context area from nonpaged pool. They should treat the returned context area as read-only, preserving the
    state set up by the underlying NDIS intermediate driver that defined it.




## -see-also

<a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a>



<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>



<a href="..\ndis\nf-ndis-ndisiminitializedeviceinstanceex.md">
   NdisIMInitializeDeviceInstanceEx</a>



 

 


