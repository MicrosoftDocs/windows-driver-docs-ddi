---
UID: NF:wsk.WskRegister
title: WskRegister function
author: windows-driver-content
description: The WskRegister function registers a WSK application, given the application's WSK client Network Programming Interface (NPI).
old-location: netvista\wskregister.htm
tech.root: netvista
ms.assetid: 340933ad-1a71-421c-b1e1-360aa9c441fd
ms.date: 05/02/2018
ms.keywords: WskRegister, WskRegister function [Network Drivers Starting with Windows Vista], netvista.wskregister, wsk/WskRegister, wskref_21a26aab-f817-457f-bfde-28bcf1e2c8d0.xml
ms.topic: function
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Universal
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Netio.lib
-	Netio.dll
api_name:
-	WskRegister
product:
- Windows
targetos: Windows
req.typenames: 
---

# WskRegister function


## -description


The 
  <b>WskRegister</b> function registers a WSK application, given the application's WSK client 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/network/network-programming-interface">Network Programming Interface
  (NPI)</a>.


## -parameters




### -param WskClientNpi [in]

A pointer to the client NPI implemented by the WSK application.


### -param WskRegistration [out]

A pointer to a memory location that identifies a WSK application's registration instance. This
     memory location will be initialized by the 
     <b>WskRegister</b> call and will be used by the other 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571179">WSK registration functions</a>. The
     WSK application should never change the contents of this memory location directly.


## -returns



<b>WskRegister</b> returns one of the following NTSTATUS codes:

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
The registration succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
The registration failed.

</td>
</tr>
</table>
 




## -remarks



A WSK client object can call this function multiple times, but a different 
    <i>WskRegistration</i> parameter must be used for each call in order to create multiple registration
    instances.

For each call to 
    <b>WskRegister</b> that returns a success code, there must be exactly one corresponding 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571128">WskDeregister</a> call that uses the same 
    <i>WskRegistration</i> parameter that was passed to 
    <b>WskRegister</b>.

The block of memory pointed to by 
    <i>WskRegistration</i> must be kept allocated (must not be freed or go out of scope) as long as there are
    outstanding calls to other 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571179">WSK registration functions</a>.
    
Using the 
    <b>WskRegister</b> and 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571128">WskDeregister</a> functions is the preferred
    method for registering and unregistering WSK applications. The 
    <a href="https://msdn.microsoft.com/23c15c42-94aa-410b-8551-fafa8b24ad86">Network Module Registrar</a> remains
    available for compatibility.

For more information about attaching a WSK application to the WSK subsystem, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/registering-a-winsock-kernel-application">Registering a Winsock Kernel
    Application</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff571163">WSK_CLIENT_NPI</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571178">WSK_REGISTRATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571128">WskDeregister</a>
 

 

