---
UID: NF:dispmprt.DxgkInitializeDisplayOnlyDriver
title: DxgkInitializeDisplayOnlyDriver function (dispmprt.h)
description: Loads and initializes the DirectX graphics kernel subsystem (Dxgkrnl.sys) for use by a kernel mode display-only driver (KMDOD).
old-location: display\dxgkinitializedisplayonlydriver.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DxgkInitializeDisplayOnlyDriver function"]
ms.keywords: DxgkInitializeDisplayOnlyDriver, DxgkInitializeDisplayOnlyDriver function [Display Devices], display.dxgkinitializedisplayonlydriver, dispmprt/DxgkInitializeDisplayOnlyDriver
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
targetos: Windows
req.typenames: 
f1_keywords:
 - DxgkInitializeDisplayOnlyDriver
 - dispmprt/DxgkInitializeDisplayOnlyDriver
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Displib.lib
 - Displib.dll
api_name:
 - DxgkInitializeDisplayOnlyDriver
---

# DxgkInitializeDisplayOnlyDriver function


## -description

Loads and initializes the DirectX graphics kernel subsystem (Dxgkrnl.sys) for use by a kernel mode display-only driver (KMDOD).

## -parameters

### -param DriverObject 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a> structure. The KMDOD previously obtained this pointer in its <a href="/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> function.

### -param RegistryPath 

[in]
A pointer to a <a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that supplies the path to the KMDOD's service registry key.  The KMDOD previously obtained this pointer in its <a href="/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> function.

### -param KmdDodInitializationData 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_kmddod_initialization_data">KMDDOD_INITIALIZATION_DATA</a> structure that supplies the DirectX graphics kernel subsystem with pointers to functions implemented by the KMDOD.

## -returns

      Returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.

## -remarks

All parameters that are supplied by the KMDOD can be in paged memory.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a>



<a href="/windows-hardware/drivers/display/driverentry-of-display-miniport-driver">DriverEntry of Display Miniport Driver</a>



<a href="/windows-hardware/drivers/ddi/dispmprt/nf-dispmprt-dxgkinitialize">DxgkInitialize</a>



<a href="/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_kmddod_initialization_data">KMDDOD_INITIALIZATION_DATA</a>



<a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
