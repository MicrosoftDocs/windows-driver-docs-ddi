---
UID: NS:netdispumdddi._MIRACAST_DRIVER_INTERFACE
title: _MIRACAST_DRIVER_INTERFACE (netdispumdddi.h)
description: Contains pointers to wireless display (Miracast) functions that are implemented by the Miracast user-mode driver.
old-location: display\miracast_driver_interface.htm
tech.root: display
ms.assetid: a3b9695e-b317-471b-91de-e191c1f5cb17
ms.date: 05/10/2018
keywords: ["MIRACAST_DRIVER_INTERFACE structure"]
ms.keywords: "*PMIRACAST_DRIVER_INTERFACE, MIRACAST_DRIVER_INTERFACE, MIRACAST_DRIVER_INTERFACE structure [Display Devices], PMIRACAST_DRIVER_INTERFACE, PMIRACAST_DRIVER_INTERFACE structure pointer [Display Devices], _MIRACAST_DRIVER_INTERFACE, display.miracast_driver_interface, netdispumdddi/MIRACAST_DRIVER_INTERFACE, netdispumdddi/PMIRACAST_DRIVER_INTERFACE"
req.header: netdispumdddi.h
req.include-header: Netdispumdddi.h
req.target-type: Windows
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
targetos: Windows
req.typenames: MIRACAST_DRIVER_INTERFACE, *PMIRACAST_DRIVER_INTERFACE
f1_keywords:
 - _MIRACAST_DRIVER_INTERFACE
 - netdispumdddi/_MIRACAST_DRIVER_INTERFACE
 - PMIRACAST_DRIVER_INTERFACE
 - netdispumdddi/PMIRACAST_DRIVER_INTERFACE
 - MIRACAST_DRIVER_INTERFACE
 - netdispumdddi/MIRACAST_DRIVER_INTERFACE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Netdispumdddi.h
api_name:
 - MIRACAST_DRIVER_INTERFACE
---

# _MIRACAST_DRIVER_INTERFACE structure


## -description

Contains pointers to wireless display (Miracast) functions that are implemented by the Miracast user-mode driver.

## -struct-fields

### -field Size

The size, in bytes, of the <b>MIRACAST_DRIVER_INTERFACE</b> structure that the driver returns when the operating system calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-query_miracast_driver_interface">QueryMiracastDriverInterface</a> function.

### -field CreateMiracastContext

A pointer to the driver's  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_create_miracast_context">CreateMiracastContext</a> function.

### -field DestroyMiracastContext

A pointer to the driver's  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_destroy_miracast_context">DestroyMiracastContext</a> function.

### -field StartMiracastSession

A pointer to the driver's  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_start_miracast_session">StartMiracastSession</a> function.

### -field StopMiracastSession

A pointer to the driver's   <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_stop_miracast_session">StopMiracastSession</a> function.

### -field HandleKernelModeMessage

A pointer to the driver's  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_handle_kmd_message">HandleKernelModeMessage</a> function.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_create_miracast_context">CreateMiracastContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_destroy_miracast_context">DestroyMiracastContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_handle_kmd_message">HandleKernelModeMessage</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-query_miracast_driver_interface">QueryMiracastDriverInterface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_start_miracast_session">StartMiracastSession</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_stop_miracast_session">StopMiracastSession</a>

