---
UID: NF:sercx.SerCxGetConnectionParameters
title: SerCxGetConnectionParameters function (sercx.h)
description: The SerCxGetConnectionParameters method retrieves the connection parameters for the associated peripheral device.
old-location: serports\sercxgetconnectionparameters.htm
tech.root: serports
ms.assetid: 361BC3A7-AE86-4C92-B7E1-A30D467D4A65
ms.date: 04/23/2018
keywords: ["SerCxGetConnectionParameters function"]
ms.keywords: 1/SerCxGetConnectionParameters, SerCxGetConnectionParameters, SerCxGetConnectionParameters method [Serial Ports], serports.sercxgetconnectionparameters
req.header: sercx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - SerCxGetConnectionParameters
 - sercx/SerCxGetConnectionParameters
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - 1.0\Sercx.h
api_name:
 - SerCxGetConnectionParameters
---

# SerCxGetConnectionParameters function


## -description

The <b>SerCxGetConnectionParameters</b> method retrieves the connection parameters for the associated peripheral device.

## -parameters

### -param Device 

[in]
A WDFDEVICE handle to the framework device object that represents the serial controller.

### -param ConnectionParameters 

[out]
A pointer to a location into which the method writes a pointer to the connection parameters. The caller must cast this pointer to the appropriate pointer type, parse the data structure for the connection parameters, read the configuration settings from this structure, and apply these settings to the serial controller hardware.

## -remarks

The serial framework extension (SerCx) obtains the connection parameters for the peripheral device from the ACPI resource descriptors in the platform firmware.

For more information about the data format of the connection parameters, see <a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx_apply_config">EvtSerCxApplyConfig</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx_apply_config">EvtSerCxApplyConfig</a>