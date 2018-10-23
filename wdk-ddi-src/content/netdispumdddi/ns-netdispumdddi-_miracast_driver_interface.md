---
UID: NS:netdispumdddi._MIRACAST_DRIVER_INTERFACE
title: "_MIRACAST_DRIVER_INTERFACE"
author: windows-driver-content
description: Contains pointers to wireless display (Miracast) functions that are implemented by the Miracast user-mode driver.
old-location: display\miracast_driver_interface.htm
tech.root: display
ms.assetid: a3b9695e-b317-471b-91de-e191c1f5cb17
ms.date: 05/10/2018
ms.keywords: "*PMIRACAST_DRIVER_INTERFACE, MIRACAST_DRIVER_INTERFACE, MIRACAST_DRIVER_INTERFACE structure [Display Devices], PMIRACAST_DRIVER_INTERFACE, PMIRACAST_DRIVER_INTERFACE structure pointer [Display Devices], _MIRACAST_DRIVER_INTERFACE, display.miracast_driver_interface, netdispumdddi/MIRACAST_DRIVER_INTERFACE, netdispumdddi/PMIRACAST_DRIVER_INTERFACE"
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Netdispumdddi.h
api_name:
-	MIRACAST_DRIVER_INTERFACE
product:
- Windows
targetos: Windows
req.typenames: MIRACAST_DRIVER_INTERFACE, *PMIRACAST_DRIVER_INTERFACE
---

# _MIRACAST_DRIVER_INTERFACE structure


## -description


Contains pointers to wireless display (Miracast) functions that are implemented by the Miracast user-mode driver.


## -struct-fields




### -field Size

The size, in bytes, of the <b>MIRACAST_DRIVER_INTERFACE</b> structure that the driver returns when the operating system calls the <a href="https://msdn.microsoft.com/a8833f8c-7e3f-422c-922e-e75476358ee9">QueryMiracastDriverInterface</a> function.


### -field CreateMiracastContext

A pointer to the driver's  <a href="https://msdn.microsoft.com/3b10ddd9-a48d-4f96-b35e-db017d1f9583">CreateMiracastContext</a> function.


### -field DestroyMiracastContext

A pointer to the driver's  <a href="https://msdn.microsoft.com/1b155e15-1e4e-45bb-98cc-f1c19923ed2c">DestroyMiracastContext</a> function.


### -field StartMiracastSession

A pointer to the driver's  <a href="https://msdn.microsoft.com/2778d9d0-7f97-416f-a5ae-3754b17e8a29">StartMiracastSession</a> function.


### -field StopMiracastSession

A pointer to the driver's   <a href="https://msdn.microsoft.com/ab9ad8ee-9390-41a4-9a69-2e98579b2b77">StopMiracastSession</a> function.


### -field HandleKernelModeMessage

A pointer to the driver's  <a href="https://msdn.microsoft.com/9DE4F3B0-915A-4C66-85F8-AE248B8471B5">HandleKernelModeMessage</a> function.


## -see-also




<a href="https://msdn.microsoft.com/3b10ddd9-a48d-4f96-b35e-db017d1f9583">CreateMiracastContext</a>



<a href="https://msdn.microsoft.com/1b155e15-1e4e-45bb-98cc-f1c19923ed2c">DestroyMiracastContext</a>



<a href="https://msdn.microsoft.com/9DE4F3B0-915A-4C66-85F8-AE248B8471B5">HandleKernelModeMessage</a>



<a href="https://msdn.microsoft.com/a8833f8c-7e3f-422c-922e-e75476358ee9">QueryMiracastDriverInterface</a>



<a href="https://msdn.microsoft.com/2778d9d0-7f97-416f-a5ae-3754b17e8a29">StartMiracastSession</a>



<a href="https://msdn.microsoft.com/ab9ad8ee-9390-41a4-9a69-2e98579b2b77">StopMiracastSession</a>
 

 

