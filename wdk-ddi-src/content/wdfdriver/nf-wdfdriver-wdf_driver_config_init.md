---
UID: NF:wdfdriver.WDF_DRIVER_CONFIG_INIT
title: WDF_DRIVER_CONFIG_INIT function (wdfdriver.h)
description: The WDF_DRIVER_CONFIG_INIT function initializes a driver's WDF_DRIVER_CONFIG structure.
old-location: wdf\wdf_driver_config_init.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WDF_DRIVER_CONFIG_INIT function"]
ms.keywords: DFDriverObjectRef_c8331742-9717-476d-8a48-f9e472cb3128.xml, WDF_DRIVER_CONFIG_INIT, WDF_DRIVER_CONFIG_INIT function, kmdf.wdf_driver_config_init, wdf.wdf_driver_config_init, wdfdriver/WDF_DRIVER_CONFIG_INIT
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
targetos: Windows
req.typenames: 
f1_keywords:
 - WDF_DRIVER_CONFIG_INIT
 - wdfdriver/WDF_DRIVER_CONFIG_INIT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfdriver.h
api_name:
 - WDF_DRIVER_CONFIG_INIT
---

# WDF_DRIVER_CONFIG_INIT function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The WDF_DRIVER_CONFIG_INIT function initializes a driver's <a href="/windows-hardware/drivers/ddi/wdfdriver/ns-wdfdriver-_wdf_driver_config">WDF_DRIVER_CONFIG</a> structure.

## -parameters

### -param Config [out]


A pointer to the <a href="/windows-hardware/drivers/ddi/wdfdriver/ns-wdfdriver-_wdf_driver_config">WDF_DRIVER_CONFIG</a> structure that the function will initialize.

### -param EvtDriverDeviceAdd [in, optional]


A pointer to the driver's <a href="/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function.

## -remarks

The WDF_DRIVER_CONFIG_INIT function is available in version 1.0 and later versions of KMDF.


#### Examples

For a code example that uses WDF_DRIVER_CONFIG_INIT, see <a href="/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfdrivercreate">WdfDriverCreate</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a>



<a href="/windows-hardware/drivers/ddi/wdfdriver/ns-wdfdriver-_wdf_driver_config">WDF_DRIVER_CONFIG</a>



<a href="/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfdrivercreate">WdfDriverCreate</a>
