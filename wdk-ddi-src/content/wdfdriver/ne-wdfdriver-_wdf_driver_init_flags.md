---
UID: NE:wdfdriver._WDF_DRIVER_INIT_FLAGS
title: "_WDF_DRIVER_INIT_FLAGS"
author: windows-driver-content
description: The WDF_DRIVER_INIT_FLAGS enumeration specifies driver initialization flags.
old-location: wdf\wdf_driver_init_flags.htm
old-project: wdf
ms.assetid: cbabd178-3496-4851-9acf-f0718eaebdcd
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDriverObjectRef_a77b530c-fd37-4ffe-a006-7deaa8156040.xml, WDF_DRIVER_INIT_FLAGS, WDF_DRIVER_INIT_FLAGS enumeration, WdfDriverInitNoDispatchOverride, WdfDriverInitNonPnpDriver, WdfVerifierOn, WdfVerifyOn, _WDF_DRIVER_INIT_FLAGS, kmdf.wdf_driver_init_flags, wdf.wdf_driver_init_flags, wdfdriver/WDF_DRIVER_INIT_FLAGS, wdfdriver/WdfDriverInitNoDispatchOverride, wdfdriver/WdfDriverInitNonPnpDriver, wdfdriver/WdfVerifierOn, wdfdriver/WdfVerifyOn
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfdriver.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfdriver.h
api_name:
-	WDF_DRIVER_INIT_FLAGS
product: Windows
targetos: Windows
req.typenames: WDF_DRIVER_INIT_FLAGS
---

# _WDF_DRIVER_INIT_FLAGS enumeration


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The WDF_DRIVER_INIT_FLAGS enumeration specifies driver initialization flags.


## -enum-fields




### -field WdfDriverInitNonPnpDriver

The driver does not support Plug and Play (PnP). If this value is set, the driver must not supply an <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function. For more information about non-PnP drivers, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-kernel-mode-driver-framework-with-non-pnp-drivers">Using Kernel-Mode Driver Framework with Non-PnP Drivers</a>.


### -field WdfDriverInitNoDispatchOverride

The driver is a miniport driver and, therefore, the framework must not provide dispatch routines for the driver. In other words, the framework must not intercept I/O request packets (IRPs) that the I/O manager has directed to the driver. In addition, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff547193">WdfDriverMiniportUnload</a> when the port driver informs the miniport driver that it is about to be unloaded. For more information about this flag and how to write framework-based miniport drivers, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-kmdf-miniport-drivers">Using Kernel-Mode Driver Framework with Miniport Drivers</a>.


### -field WdfVerifyOn

Reserved for system use. Drivers must not use this flag.


### -field WdfVerifierOn

Reserved for system use. Drivers must not use this flag.


### -field WdfDriverInitCompanion




## -remarks



The WDF_DRIVER_INIT_FLAGS enumeration is used to specify the value for the <b>DriverInitFlags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551300">WDF_DRIVER_CONFIG</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551300">WDF_DRIVER_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547193">WdfDriverMiniportUnload</a>
 

 

