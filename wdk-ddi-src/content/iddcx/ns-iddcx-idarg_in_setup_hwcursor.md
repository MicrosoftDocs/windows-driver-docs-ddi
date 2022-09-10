---
UID: NS:iddcx.IDARG_IN_SETUP_HWCURSOR
title: IDARG_IN_SETUP_HWCURSOR (iddcx.h)
description: Gives information about new cursors associated with a monitor.
old-location: display\idarg_in_setup_hwcursor.htm
tech.root: display
ms.date: 08/05/2022
keywords: ["IDARG_IN_SETUP_HWCURSOR structure"]
ms.keywords: IDARG_IN_SETUP_HWCURSOR, IDARG_IN_SETUP_HWCURSOR structure [Display Devices], display.idarg_in_setup_hwcursor, iddcx/IDARG_IN_SETUP_HWCURSOR
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
 - IDARG_IN_SETUP_HWCURSOR
 - iddcx/IDARG_IN_SETUP_HWCURSOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDARG_IN_SETUP_HWCURSOR
---

# IDARG_IN_SETUP_HWCURSOR structure

## -description

The **IDARG_IN_SETUP_HWCURSOR** structure is an input parameter passed to [**IddCxMonitorSetupHardwareCursor**](nf-iddcx-iddcxmonitorsetuphardwarecursor.md) to provide information about new cursors associated with a monitor.

## -struct-fields

### -field CursorInfo

[in] An [**IDDCX_CURSOR_CAPS**](ns-iddcx-iddcx_cursor_caps.md) structure that provides information about a cursor's capabilities for this path.

### -field hNewCursorDataAvailable

[in] An event handle that will be triggered when new cursor data is available.

## -see-also

[**CreateEvent**](/windows/win32/api/synchapi/nf-synchapi-createeventa)

[**IddCxMonitorSetupHardwareCursor**](nf-iddcx-iddcxmonitorsetuphardwarecursor.md)
