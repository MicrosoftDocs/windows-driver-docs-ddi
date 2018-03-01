---
UID: NF:dispmprt.DxgkInitializeDisplayOnlyDriver
title: DxgkInitializeDisplayOnlyDriver function
author: windows-driver-content
description: Loads and initializes the DirectX graphics kernel subsystem (Dxgkrnl.sys) for use by a kernel mode display-only driver (KMDOD).
old-location: display\dxgkinitializedisplayonlydriver.htm
old-project: display
ms.assetid: d80d2d6a-758f-4b11-b33c-4b176a458bd2
ms.author: windowsdriverdev
ms.date: 2/26/2018
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
product: Windows
targetos: Windows
req.typenames: DXGK_SURPRISE_REMOVAL_TYPE
---

# DxgkInitializeDisplayOnlyDriver function


## -description


Loads and initializes the DirectX graphics kernel subsystem (Dxgkrnl.sys) for use by a kernel mode display-only driver (KMDOD).


## -syntax


````
NTSTATUS DxgkInitializeDisplayOnlyDriver(
  _In_ PDRIVER_OBJECT              DriverObject,
  _In_ PUNICODE_STRING             RegistryPath,
  _In_ PKMDDOD_INITIALIZATION_DATA KmdDodInitializationData
);
````


## -parameters




### -param DriverObject [in]

A pointer to a <a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a> structure. The KMDOD previously obtained this pointer in its <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> function.


### -param RegistryPath [in]

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that supplies the path to the KMDOD's service registry key.  The KMDOD previously obtained this pointer in its <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> function.


### -param KmdDodInitializationData [in]

A pointer to a <a href="..\dispmprt\ns-dispmprt-_kmddod_initialization_data.md">KMDDOD_INITIALIZATION_DATA</a> structure that supplies the DirectX graphics kernel subsystem with pointers to functions implemented by the KMDOD.


## -returns




      Returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.




## -remarks



All parameters that are supplied by the KMDOD can be in paged memory.




## -see-also

<a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\dispmprt\ns-dispmprt-_kmddod_initialization_data.md">KMDDOD_INITIALIZATION_DATA</a>



<a href="..\dispmprt\nf-dispmprt-dxgkinitialize.md">DxgkInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556157">DriverEntry of Display Miniport Driver</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DxgkInitializeDisplayOnlyDriver function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

