---
UID: NE:d3dkmddi._DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAGS
title: _DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAGS (d3dkmddi.h)
description: DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAGS provides additional information to the driver in a DxgkCbHardwareContentProtectionTeardown call.
old-location: display\dxgk_hardware_content_protection_teardown_flags.htm
ms.assetid: C9D2763D-D129-429C-AA30-85EF4D30F730
ms.date: 05/10/2018
keywords: ["DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAGS enumeration"]
ms.keywords: DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAGS, DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAGS enumeration [Display Devices], DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAG_PREEMPTIVE, _DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAGS, d3dkmddi/DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAGS, d3dkmddi/DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAG_PREEMPTIVE, display.dxgk_hardware_content_protection_teardown_flags
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
tech.root: display
req.typenames: DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAGS
f1_keywords:
 - _DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAGS
 - d3dkmddi/_DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAGS
 - DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAGS
 - d3dkmddi/DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAGS
---

# _DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAGS enumeration


## -description

<b>DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAGS</b> provides additional information to the driver in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_hardwarecontentprotectionteardown">DxgkCbHardwareContentProtectionTeardown</a> call.

## -enum-fields

### -field DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAG_PREEMPTIVE

Indicates that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_hardwarecontentprotectionteardown">DxgkCbHardwareContentProtectionTeardown</a> callback is being preemptively called prior to tear-down event actually occurring.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_hardwarecontentprotectionteardown">DxgkCbHardwareContentProtectionTeardown</a>

