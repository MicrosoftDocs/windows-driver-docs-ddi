---
UID: NF:wsk.WskDeregister
title: WskDeregister function (wsk.h)
description: The WskDeregister function unregisters a WSK application's registration instance that was previously created by WskRegister.
old-location: netvista\wskderegister.htm
tech.root: netvista
ms.assetid: b2ff3d7b-319d-4256-a574-cb32595fd02f
ms.date: 05/02/2018
keywords: ["WskDeregister function"]
ms.keywords: WskDeregister, WskDeregister function [Network Drivers Starting with Windows Vista], netvista.wskderegister, wsk/WskDeregister, wskref_45c2ad8f-a969-4a82-ac5e-67e4d3c96ffb.xml
f1_keywords:
 - "wsk/WskDeregister"
 - "WskDeregister"
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Netio.lib
- Netio.dll
api_name:
- WskDeregister
product:
- Windows
targetos: Windows
req.typenames: 
---

# WskDeregister function


## -description


The 
  <b>WskDeregister</b> function unregisters a WSK application's registration instance that was previously
  created by 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nf-wsk-wskregister">WskRegister</a>.


## -parameters




### -param WskRegistration [in]

A pointer to the memory location initialized by 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nf-wsk-wskregister">WskRegister</a> that identifies a WSK
     application's registration instance.


## -remarks



For each call to 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nf-wsk-wskregister">WskRegister</a> that returns a success code, there
    must be exactly one corresponding 
    <b>WskDeregister</b> call that uses the same 
    <i>WskRegistration</i> parameter that was passed to 
    <b>WskRegister</b>.

<b>WskDeregister</b> will wait to return until all of the following have completed:

<ul>
<li>
All captured instances of the provider NPI are released.

</li>
<li>
Any outstanding calls to functions pointed to by 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_provider_dispatch">WSK_PROVIDER_DISPATCH</a> members have
      returned.

</li>
<li>
All sockets are closed.

</li>
</ul>
For more information about attaching a WSK application to the WSK subsystem, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/registering-a-winsock-kernel-application">Registering a Winsock Kernel
    Application</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_registration">WSK_REGISTRATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nf-wsk-wskregister">WskRegister</a>
 

 

