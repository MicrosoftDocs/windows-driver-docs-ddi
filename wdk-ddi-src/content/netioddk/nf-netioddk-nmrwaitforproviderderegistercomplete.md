---
UID: NF:netioddk.NmrWaitForProviderDeregisterComplete
title: NmrWaitForProviderDeregisterComplete function
description: The NmrWaitForProviderDeregisterComplete function waits for the deregistration of a provider module to complete.
old-location: netvista\nmrwaitforproviderderegistercomplete.htm
tech.root: netvista
ms.assetid: ec6e75e8-f24a-4d76-b6e1-af35b5402f91
ms.date: 05/02/2018
ms.keywords: NmrWaitForProviderDeregisterComplete, NmrWaitForProviderDeregisterComplete function [Network Drivers Starting with Windows Vista], netioddk/NmrWaitForProviderDeregisterComplete, netvista.nmrwaitforproviderderegistercomplete, nmrref_bd063787-0438-49de-9816-e5a110528d54.xml
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
req.irql: "< DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	netio.lib
-	netio.dll
api_name:
-	NmrWaitForProviderDeregisterComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# NmrWaitForProviderDeregisterComplete function


## -description


The 
  <b>NmrWaitForProviderDeregisterComplete</b> function waits for the deregistration of a provider module to
  complete.


## -parameters




### -param NmrProviderHandle [in]

A handle used by the NMR to represent the registration of the provider module. The NMR returns
     this handle to the provider module when the provider module calls the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568784">NmrRegisterProvider</a> function.


## -returns



The 
     <b>NmrWaitForProviderDeregisterComplete</b> function returns one of the following NTSTATUS codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The NMR completed deregistering the provider module.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The provider module called the 
       <b>NmrWaitForProviderDeregisterComplete</b> function before calling the 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff568778">NmrDeregisterProvider</a> function,
       or the handle specified in the NmrClientHandle parameter is not a valid provider handle.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred.

</td>
</tr>
</table>
 




## -remarks



A provider module calls the 
    <b>NmrWaitForProviderDeregisterComplete</b> function to wait for the deregistration of the provider module
    to complete. A provider module calls the 
    <b>NmrWaitForProviderDeregisterComplete</b> function only after calling the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568778">NmrDeregisterProvider</a> function.

A provider module typically calls the 
    <b>NmrWaitForProviderDeregisterComplete</b> function from its 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564886">Unload</a> function to wait until it is completely
    deregistered from the NMR before the provider module is unloaded from the system. A provider module must
    not return from a call to its 
    <i>Unload</i> function until after deregistration is
    complete.


<div class="alert"><b>Note</b>  If a provider module uses the Windows Driver Framework, it will typically call the
     
     <b>NmrWaitForProviderDeregisterComplete</b> function from its 
     <a href="https://msdn.microsoft.com/2a2ed215-1b62-4ff1-bea6-e38fafbcf7d0">EvtDriverUnload</a> event callback function. In
     this situation, the provider module must not return from a call to its 
     <i>EvtDriverUnload</i> function until after
     deregistration is complete.</div>
<div> </div>





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568778">NmrDeregisterProvider</a>
 

 

