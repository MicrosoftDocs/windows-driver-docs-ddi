---
UID: NF:netioddk.NmrProviderDetachClientComplete
title: NmrProviderDetachClientComplete function
author: windows-driver-content
description: The NmrProviderDetachClientComplete function notifies the NMR that a provider module has completed detaching from a client module.
old-location: netvista\nmrproviderdetachclientcomplete.htm
old-project: netvista
ms.assetid: a52b3cfc-d6bd-4569-8b09-36dce65d017f
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: NmrProviderDetachClientComplete, NmrProviderDetachClientComplete function [Network Drivers Starting with Windows Vista], netioddk/NmrProviderDetachClientComplete, netvista.nmrproviderdetachclientcomplete, nmrref_c86f4d4f-b54f-4e31-b683-f692ff7ed1ba.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: netioddk.h
req.include-header: Wsk.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
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
req.lib: Netio.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	netio.lib
-	netio.dll
api_name:
-	NmrProviderDetachClientComplete
product: Windows
targetos: Windows
req.typenames: 
---

# NmrProviderDetachClientComplete function


## -description


The 
  <b>NmrProviderDetachClientComplete</b> function notifies the NMR that a provider module has completed
  detaching from a client module.


## -parameters




### -param NmrBindingHandle [in]

A handle used by the NMR to represent the binding between the client module and the provider
     module. The NMR passes this handle to the provider module when it calls the provider module's 
     <a href="https://msdn.microsoft.com/6c8e6cf1-0528-4da2-acc1-81ec9dbc23c3">ProviderAttachClient</a> callback
     function.


## -returns



None




## -remarks



A provider module calls the 
    <b>NmrProviderDetachClientComplete</b> function when it asynchronously completes detaching from a client
    module after returning STATUS_PENDING from its 
    <a href="https://msdn.microsoft.com/0f29bf89-856c-4019-a966-3e666a7fc78d">ProviderDetachClient</a> callback
    function.

A provider module should not call the 
    <b>NmrProviderDetachClientComplete</b> function if it returns STATUS_SUCCESS from its 
    <a href="https://msdn.microsoft.com/0f29bf89-856c-4019-a966-3e666a7fc78d">ProviderDetachClient</a> callback
    function.




## -see-also




<a href="https://msdn.microsoft.com/6c8e6cf1-0528-4da2-acc1-81ec9dbc23c3">ProviderAttachClient</a>



<a href="https://msdn.microsoft.com/0f29bf89-856c-4019-a966-3e666a7fc78d">ProviderDetachClient</a>
 

 

