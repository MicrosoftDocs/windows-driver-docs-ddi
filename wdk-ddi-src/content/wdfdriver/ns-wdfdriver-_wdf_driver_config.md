---
UID: NS:wdfdriver._WDF_DRIVER_CONFIG
title: "_WDF_DRIVER_CONFIG"
author: windows-driver-content
description: The WDF_DRIVER_CONFIG structure is an input parameter to WdfDriverCreate.
old-location: wdf\wdf_driver_config.htm
tech.root: wdf
ms.assetid: 24197846-9664-4fc6-8578-5bcaf0e4a71c
ms.date: 02/26/2018
ms.keywords: "*PWDF_DRIVER_CONFIG, DFDriverObjectRef_89306ddc-557c-4142-a26b-a120acdffed6.xml, PWDF_DRIVER_CONFIG, PWDF_DRIVER_CONFIG structure pointer, WDF_DRIVER_CONFIG, WDF_DRIVER_CONFIG structure, _WDF_DRIVER_CONFIG, kmdf.wdf_driver_config, wdf.wdf_driver_config, wdfdriver/PWDF_DRIVER_CONFIG, wdfdriver/WDF_DRIVER_CONFIG"
ms.topic: struct
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfdriver.h
api_name:
-	WDF_DRIVER_CONFIG
product:
- Windows
targetos: Windows
req.typenames: WDF_DRIVER_CONFIG, *PWDF_DRIVER_CONFIG
---

# _WDF_DRIVER_CONFIG structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The WDF_DRIVER_CONFIG structure is an input parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547175">WdfDriverCreate</a>.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field EvtDriverDeviceAdd

A pointer to a driver's <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function.


### -field EvtDriverUnload

A pointer to a driver's <a href="https://msdn.microsoft.com/2a2ed215-1b62-4ff1-bea6-e38fafbcf7d0">EvtDriverUnload</a> callback function.


### -field DriverInitFlags

A bitwise OR of one or more <a href="https://msdn.microsoft.com/library/windows/hardware/ff551303">WDF_DRIVER_INIT_FLAGS</a>-typed values that identify driver initialization flags.


### -field DriverPoolTag

(KMDF versions 1.5 and later.) A driver-defined pool tag that the framework will assign to all of the driver's pool allocations. Debuggers display this tag. For more information about specifying a pool tag, see the following Remarks section.


## -remarks



Your driver can optionally specify a pool tag that the framework will assign to all of the driver's pool allocations. Drivers typically specify a character string of up to four characters, delimited by single quotation marks, in reverse order (for example, 'dcba'). The ASCII value of each character in the tag must be between 0 and 127.  

If <b>DriverPoolTag</b> is zero, the framework creates a default pool tag by using the first four characters of your driver's kernel-mode service name. If the service name begins with "WDF" (the name is not case sensitive and does not include the quotation marks), the next four characters are used. If fewer than four characters are available, "FxDr" is used. 

To initialize a WDF_DRIVER_CONFIG structure, drivers must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff551302">WDF_DRIVER_CONFIG_INIT</a>.




## -see-also




<a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a>



<a href="https://msdn.microsoft.com/2a2ed215-1b62-4ff1-bea6-e38fafbcf7d0">EvtDriverUnload</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551302">WDF_DRIVER_CONFIG_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551303">WDF_DRIVER_INIT_FLAGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547175">WdfDriverCreate</a>
 

 

