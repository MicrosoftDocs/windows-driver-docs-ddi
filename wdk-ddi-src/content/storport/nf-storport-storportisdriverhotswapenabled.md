---
UID: NF:storport.StorPortIsDriverHotSwapEnabled
tech.root: storage
title: StorPortIsDriverHotSwapEnabled
ms.date: 07/25/2024
targetos: Windows
description: Learn more about the StorPortIsDriverHotSwapEnabled function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: storport.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - StorPortIsDriverHotSwapEnabled
f1_keywords:
 - StorPortIsDriverHotSwapEnabled
 - storport/StorPortIsDriverHotSwapEnabled
dev_langs:
 - c++
helpviewer_keywords:
 - StorPortIsDriverHotSwapEnabled
---

## -description

A miniport driver calls the **StorPortIsDriverHotSwapEnabled** function to determine whether driver hot swap is enabled in the kernel.

## -parameters

### -param HwDeviceExtension

[in] A pointer to the hardware device extension for the host bus adapter (HBA).

### -param DriverObject

[in] Pointer to the driver object.

## -returns

**StorPortIsDriverHotSwapEnabled** returns a STOR_STATUS_SUCCESS if driver hot swap is enabled. Otherwise, it returns a value such as:

| Return value | Description |
|--------------|-------------|
| STOR_STATUS_INVALID_PARAMETER | The driver object is NULL. |
| STOR_STATUS_NOT_IMPLEMENTED | This function isn't implemented on the active operating system. |

## -remarks

## -see-also

[**StorPortRegisterDriverProxy**](nf-storport-storportregisterdriverproxy.md)

[**StorPortRegisterDriverProxyEndpoints**](nf-storport-storportregisterdriverproxyendpoints.md)

[**StorPortGetDriverProxyEndpointWrapper**](nf-storport-storportgetdriverproxyendpointwrapper.md)
