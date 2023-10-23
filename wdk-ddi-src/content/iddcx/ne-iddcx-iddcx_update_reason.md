---
UID: NE:iddcx.IDDCX_UPDATE_REASON
title: IDDCX_UPDATE_REASON (iddcx.h)
description: Learn more about the IDDCX_UPDATE_REASON enumeration.
tech.root: display
ms.date: 09/22/2023
keywords: ["IDDCX_UPDATE_REASON enumeration"]
ms.keywords: IDDCX_UPDATE_REASON, IDDCX_UPDATE_REASON enumeration [Display Devices], IDDCX_UPDATE_REASON_CONFIGURATION_CONSTRAINTS, IDDCX_UPDATE_REASON_DISPLAY_LINK_BANDWIDTH, IDDCX_UPDATE_REASON_HOST_LINK_BANDWIDTH, IDDCX_UPDATE_REASON_OTHER, IDDCX_UPDATE_REASON_POWER_CONSTRAINTS, IDDCX_UPDATE_REASON_UNINITIALIZED, display.iddcx_update_reason, iddcx/IDDCX_UPDATE_REASON, iddcx/IDDCX_UPDATE_REASON_CONFIGURATION_CONSTRAINTS, iddcx/IDDCX_UPDATE_REASON_DISPLAY_LINK_BANDWIDTH, iddcx/IDDCX_UPDATE_REASON_HOST_LINK_BANDWIDTH, iddcx/IDDCX_UPDATE_REASON_OTHER, iddcx/IDDCX_UPDATE_REASON_POWER_CONSTRAINTS, iddcx/IDDCX_UPDATE_REASON_UNINITIALIZED
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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
 - IDDCX_UPDATE_REASON
 - iddcx/IDDCX_UPDATE_REASON
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDDCX_UPDATE_REASON
---

# IDDCX_UPDATE_REASON enumeration

## -description

A **IDDCX_UPDATE_REASON** value describes why the driver is calling to update the mode list.

## -enum-fields

### -field IDDCX_UPDATE_REASON_UNINITIALIZED:0

Indicates that an **IDDCX_UPDATE_REASON** variable has not yet been assigned a meaningful value.

### -field IDDCX_UPDATE_REASON_POWER_CONSTRAINTS:1

The mode list is changing due to changed power constraints on the host system.

### -field IDDCX_UPDATE_REASON_HOST_LINK_BANDWIDTH:2

The mode list is changing due to changes in bandwidth between the system and the indirect display device.

### -field IDDCX_UPDATE_REASON_DISPLAY_LINK_BANDWIDTH:3

The mode list is changing due to changes in bandwidth between the indirect display device and the monitor.

### -field IDDCX_UPDATE_REASON_CONFIGURATION_CONSTRAINTS:4

The mode list is changing due to constraints of the product when in a new configuration.

### -field IDDCX_UPDATE_REASON_OTHER:5

The mode list is changing due to another reason not listed above.

## -see-also

[**IDARG_IN_MAXDISPLAYPIPELINERATE**](ns-iddcx-idarg_in_maxdisplaypipelinerate.md)

[**IDARG_IN_UPDATEMODES**](ns-iddcx-idarg_in_updatemodes.md)

[**IddCxAdapterUpdateMaxDisplayPipelineRate**](nf-iddcx-iddcxadapterupdatemaxdisplaypipelinerate.md)

[**IddCxMonitorUpdateModes2**](nf-iddcx-iddcxmonitorupdatemodes2.md)

[**IddCxMonitorUpdateModes**](nf-iddcx-iddcxmonitorupdatemodes.md)
