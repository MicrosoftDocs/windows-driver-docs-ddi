---
UID: NS:iddcx.IDDCX_ADAPTER_CAPS
title: IDDCX_ADAPTER_CAPS (iddcx.h)
description: Gives information about the capabilities of the adapter.
old-location: display\iddcx_adapter_caps.htm
tech.root: display
ms.date: 01/11/2021
keywords: ["IDDCX_ADAPTER_CAPS structure"]
ms.keywords: IDDCX_ADAPTER_CAPS, IDDCX_ADAPTER_CAPS structure [Display Devices], display.iddcx_adapter_caps, iddcx/IDDCX_ADAPTER_CAPS
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IDDCX_ADAPTER_CAPS
 - iddcx/IDDCX_ADAPTER_CAPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDDCX_ADAPTER_CAPS
---

# IDDCX_ADAPTER_CAPS structure

## -description

The **IDDCX_ADAPTER_CAPS** structure provides information about the capabilities of the adapter.

## -struct-fields

### -field Size

Size, in bytes, of the structure.

### -field Flags

An [**IDDCX_ADAPTER_FLAGS**](ne-iddcx-iddcx_adapter_flags.md) value specifying the adapter flags used by the driver.

### -field MaxDisplayPipelineRate

Value that represents the total display bandwidth for the adapter. Each mode the driver reports to the OS also has a display pipeline rate associated with it and the OS ensures that the combined display pipeline rate of all the active modes will never exceed this value. The driver decides how many units it uses.

Some hardware have resource dependencies that allow them to support all modes in all configurations. For example, an adapter might be able to individually support a 4k mode on each of its two outputs but not 4k on each of the outputs at the same time. If driver does not have these restrictions then it can set all bandwidths to zero.

### -field MaxMonitorsSupported

The maximum number of monitors that can be connected at the same time.

### -field EndPointDiagnostics

An [**IDDCX_ENDPOINT_DIAGNOSTIC_INFO**](ns-iddcx-iddcx_endpoint_diagnostic_info.md) structure containing endpoint diagnostics information. This information is used for telemetry; it is not used for runtime OS decision.

### -field StaticDesktopReencodeFrameCount

The number of frames to request after the desktop goes idle if the driver's encoder requires multiple frames to continue improving quality.

## -remarks

**IDDCX_ADAPTER_CAPS** is a member of the [**IDARG_IN_ADAPTER_INIT**](ns-iddcx-idarg_in_adapter_init.md) structure that is used to create a WDDM graphics adapter.

## -see-also

[**IDARG_IN_ADAPTER_INIT**](ns-iddcx-idarg_in_adapter_init.md)

[**IDDCX_ADAPTER_FLAGS**](ne-iddcx-iddcx_adapter_flags.md)

[**IDDCX_ENDPOINT_DIAGNOSTIC_INFO**](ns-iddcx-iddcx_endpoint_diagnostic_info.md)

[**IddCxAdapterInitAsync**](nf-iddcx-iddcxadapterinitasync.md)
