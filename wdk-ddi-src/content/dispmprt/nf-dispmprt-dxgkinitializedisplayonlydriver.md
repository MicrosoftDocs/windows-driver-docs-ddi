---
UID: NF:dispmprt.DxgkInitializeDisplayOnlyDriver
title: DxgkInitializeDisplayOnlyDriver function
author: windows-driver-content
description: Loads and initializes the DirectX graphics kernel subsystem (Dxgkrnl.sys) for use by a kernel mode display-only driver (KMDOD).
old-location: display\dxgkinitializedisplayonlydriver.htm
old-project: display
ms.assetid: d80d2d6a-758f-4b11-b33c-4b176a458bd2
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DxgkInitializeDisplayOnlyDriver, DxgkInitializeDisplayOnlyDriver function [Display Devices], display.dxgkinitializedisplayonlydriver, dispmprt/DxgkInitializeDisplayOnlyDriver
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: dispmprt.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Displib.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Displib.lib
-	Displib.dll
api_name:
-	DxgkInitializeDisplayOnlyDriver
product:
- Windows
targetos: Windows
req.typenames: DXGK_SURPRISE_REMOVAL_TYPE
---

# DxgkInitializeDisplayOnlyDriver function


## -description


Loads and initializes the DirectX graphics kernel subsystem (Dxgkrnl.sys) for use by a kernel mode display-only driver (KMDOD).


## -parameters




### -param DriverObject [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544174">DRIVER_OBJECT</a> structure. The KMDOD previously obtained this pointer in its <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> function.


### -param RegistryPath [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that supplies the path to the KMDOD's service registry key.  The KMDOD previously obtained this pointer in its <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> function.


### -param KmdDodInitializationData [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh451571">KMDDOD_INITIALIZATION_DATA</a> structure that supplies the DirectX graphics kernel subsystem with pointers to functions implemented by the KMDOD.


## -returns




      Returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.




## -remarks



All parameters that are supplied by the KMDOD can be in paged memory.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544174">DRIVER_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556157">DriverEntry of Display Miniport Driver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560824">DxgkInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451571">KMDDOD_INITIALIZATION_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
 

 

