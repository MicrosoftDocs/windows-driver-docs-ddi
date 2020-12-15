---
UID: NF:wdfdevice.WDF_IO_TYPE_CONFIG_INIT
title: WDF_IO_TYPE_CONFIG_INIT function (wdfdevice.h)
description: The WDF_IO_TYPE_CONFIG_INIT function initializes a driver's WDF_IO_TYPE_CONFIG structure.
old-location: wdf\wdf_io_type_config_init.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WDF_IO_TYPE_CONFIG_INIT function"]
ms.keywords: WDF_IO_TYPE_CONFIG_INIT, WDF_IO_TYPE_CONFIG_INIT function, wdf.wdf_io_type_config_init, wdfdevice/WDF_IO_TYPE_CONFIG_INIT
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.13
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
 - WDF_IO_TYPE_CONFIG_INIT
 - wdfdevice/WDF_IO_TYPE_CONFIG_INIT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfdevice.h
api_name:
 - WDF_IO_TYPE_CONFIG_INIT
---

# WDF_IO_TYPE_CONFIG_INIT function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_IO_TYPE_CONFIG_INIT</b> function initializes a driver's <a href="/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_io_type_config">WDF_IO_TYPE_CONFIG</a> structure.

## -parameters

### -param IoTypeConfig 

[out]
A pointer to a driver-allocated <a href="/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_io_type_config">WDF_IO_TYPE_CONFIG</a> structure.

## -remarks

The <b>WDF_IO_TYPE_CONFIG_INIT</b> function zeros the specified <a href="/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_io_type_config">WDF_IO_TYPE_CONFIG</a> structure and sets the  structure's <b>Size</b> member. It then sets the <b>ReadWriteIoType</b> member to <b>WdfDeviceIoBuffered</b>, and the <b>DeviceControlIoType</b> member to <b>WdfDeviceIoBuffered</b>.


#### Examples

For a code example that uses <b>WDF_IO_TYPE_CONFIG_INIT</b>, see <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetiotypeex">WdfDeviceInitSetIoTypeEx</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_io_type_config">WDF_IO_TYPE_CONFIG</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetiotypeex">WdfDeviceInitSetIoTypeEx</a>
