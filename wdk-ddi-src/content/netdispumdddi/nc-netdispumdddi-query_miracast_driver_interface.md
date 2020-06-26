---
UID: NC:netdispumdddi.QUERY_MIRACAST_DRIVER_INTERFACE
title: QUERY_MIRACAST_DRIVER_INTERFACE (netdispumdddi.h)
description: Called by the operating system to query the Miracast user-mode driver interface, MIRACAST_DRIVER_INTERFACE.
old-location: display\querymiracastdriverinterface.htm
tech.root: display
ms.assetid: a8833f8c-7e3f-422c-922e-e75476358ee9
ms.date: 05/10/2018
keywords: ["QUERY_MIRACAST_DRIVER_INTERFACE callback function"]
ms.keywords: QUERY_MIRACAST_DRIVER_INTERFACE, QUERY_MIRACAST_DRIVER_INTERFACE callback, QueryMiracastDriverInterface, QueryMiracastDriverInterface callback function [Display Devices], display.query_miracast_driver_interface, display.querymiracastdriverinterface, netdispumdddi/QueryMiracastDriverInterface
f1_keywords:
 - "netdispumdddi/QueryMiracastDriverInterface"
req.header: netdispumdddi.h
req.include-header: Netdispumdddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Netdispumdddi.h
api_name:
- QueryMiracastDriverInterface
product:
- Windows
targetos: Windows
req.typenames: 
---

# QUERY_MIRACAST_DRIVER_INTERFACE callback function


## -description


Called by the operating system to query the Miracast user-mode driver interface, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/ns-netdispumdddi-_miracast_driver_interface">MIRACAST_DRIVER_INTERFACE</a>.


## -parameters




### -param MiracastDriverInterfaceVersion [in]

The version of the Miracast display interface, supplied by the operating system. 

This version is defined in Netdispumdddi.h as a <b>MIRACAST_DRIVER_INTERFACE_VERSION_XXX</b> value. For Windows 8.1, the value is <b>MIRACAST_DRIVER_INTERFACE_VERSION_1</b>.


### -param MiracastDriverInterfaceSize [in]

The size, supplied by the operating system, of the buffer pointed to by <i>pMiracastDriverInterface</i>.


### -param pMiracastDriverInterface [out]

A pointer to a buffer, supplied by the operating system, that holds the returned Miracast display driver interface, which is a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/ns-netdispumdddi-_miracast_driver_interface">MIRACAST_DRIVER_INTERFACE</a>.


## -returns



On success, this function returns <b>STATUS_SUCCESS</b>. Otherwise, the function returns an error code defined in the Ntstatus.h header.




## -remarks



When the Miracast user-mode driver is loaded, the operating system calls the <a href="https://docs.microsoft.com/windows/desktop/api/libloaderapi/nf-libloaderapi-getprocaddress">GetProcAddress</a> function with "QueryMiracastDriverInterface" entered as the function name in the <i>lpProcName</i> parameter.

<div class="alert"><b>Note</b>  If the Miracast user-mode driver doesn't supply a function with this name, the operating system fails the Miracast display device.</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/libloaderapi/nf-libloaderapi-getprocaddress">GetProcAddress</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/ns-netdispumdddi-_miracast_driver_interface">MIRACAST_DRIVER_INTERFACE</a>
 

 

