---
UID: NF:wdfdriver.WDF_DRIVER_CONFIG_INIT
title: WDF_DRIVER_CONFIG_INIT function
author: windows-driver-content
description: The WDF_DRIVER_CONFIG_INIT function initializes a driver's WDF_DRIVER_CONFIG structure.
old-location: wdf\wdf_driver_config_init.htm
old-project: wdf
ms.assetid: d7520300-9345-4681-a10d-acf34838199a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDriverObjectRef_c8331742-9717-476d-8a48-f9e472cb3128.xml, WDF_DRIVER_CONFIG_INIT, WDF_DRIVER_CONFIG_INIT function, kmdf.wdf_driver_config_init, wdf.wdf_driver_config_init, wdfdriver/WDF_DRIVER_CONFIG_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdriver.h
req.include-header: Wdf.h
req.target-type: Universal
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
-	WDF_DRIVER_CONFIG_INIT
product: Windows
targetos: Windows
req.typenames: 
---

# WDF_DRIVER_CONFIG_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The WDF_DRIVER_CONFIG_INIT function initializes a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff551300">WDF_DRIVER_CONFIG</a> structure.


## -parameters




### -param Config [out]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551300">WDF_DRIVER_CONFIG</a> structure that the function will initialize.


### -param EvtDriverDeviceAdd [in, optional]

A pointer to the driver's <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function.


## -returns



None




## -remarks



The WDF_DRIVER_CONFIG_INIT function is available in version 1.0 and later versions of KMDF.


#### Examples

For a code example that uses WDF_DRIVER_CONFIG_INIT, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547175">WdfDriverCreate</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551300">WDF_DRIVER_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547175">WdfDriverCreate</a>
 

 

