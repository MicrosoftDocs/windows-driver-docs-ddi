---
UID: NS:wsk._WSK_CLIENT_NPI
title: _WSK_CLIENT_NPI (wsk.h)
description: The WSK_CLIENT_NPI structure identifies a Network Programming Interface (NPI) implemented by a WSK client.
old-location: netvista\wsk_client_npi.htm
tech.root: netvista
ms.assetid: 2f50b228-5565-436f-8c68-8885b8916001
ms.date: 05/02/2018
keywords: ["WSK_CLIENT_NPI structure"]
ms.keywords: "*PWSK_CLIENT_NPI, PWSK_CLIENT_NPI, PWSK_CLIENT_NPI structure pointer [Network Drivers Starting with Windows Vista], WSK_CLIENT_NPI, WSK_CLIENT_NPI structure [Network Drivers Starting with Windows Vista], _WSK_CLIENT_NPI, netvista.wsk_client_npi, wsk/PWSK_CLIENT_NPI, wsk/WSK_CLIENT_NPI, wskref_e498e50c-695d-4f5c-a1db-0f87f4313d4a.xml"
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: WSK_CLIENT_NPI, *PWSK_CLIENT_NPI
f1_keywords:
 - _WSK_CLIENT_NPI
 - wsk/_WSK_CLIENT_NPI
 - PWSK_CLIENT_NPI
 - wsk/PWSK_CLIENT_NPI
 - WSK_CLIENT_NPI
 - wsk/WSK_CLIENT_NPI
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wsk.h
api_name:
 - WSK_CLIENT_NPI
---

# _WSK_CLIENT_NPI structure


## -description

The WSK_CLIENT_NPI structure identifies a 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/network/network-programming-interface">Network Programming Interface
  (NPI)</a> implemented by a WSK client.

## -struct-fields

### -field ClientContext

A pointer to the context for the WSK application's binding to the WSK subsystem.

### -field Dispatch

A pointer to a constant 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_client_dispatch">WSK_CLIENT_DISPATCH</a> structure.

## -remarks

For more information about attaching a WSK application to the WSK subsystem, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/registering-a-winsock-kernel-application">Registering a Winsock Kernel
    Application</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_client_dispatch">WSK_CLIENT_DISPATCH</a>

