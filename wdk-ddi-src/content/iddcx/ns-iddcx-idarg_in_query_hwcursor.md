---
UID: NS:iddcx.IDARG_IN_QUERY_HWCURSOR
title: IDARG_IN_QUERY_HWCURSOR (iddcx.h)
description: Gives information about the cursor associated with the monitor.
old-location: display\idarg_in_query_hwcursor.htm
tech.root: display
ms.date: 08/05/2022
keywords: ["IDARG_IN_QUERY_HWCURSOR structure"]
ms.keywords: IDARG_IN_QUERY_HWCURSOR, IDARG_IN_QUERY_HWCURSOR structure [Display Devices], PIDARG_IN_QUERY_HWCURSOR, PIDARG_IN_QUERY_HWCURSOR structure pointer [Display Devices], display.idarg_in_query_hwcursor, iddcx/IDARG_IN_QUERY_HWCURSOR, iddcx/PIDARG_IN_QUERY_HWCURSOR
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
 - IDARG_IN_QUERY_HWCURSOR
 - iddcx/IDARG_IN_QUERY_HWCURSOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDARG_IN_QUERY_HWCURSOR
---

# IDARG_IN_QUERY_HWCURSOR structure

## -description

The **IDARG_IN_QUERY_HWCURSOR** structure is passed to [**IddCxMonitorQueryHardwareCursor**](nf-iddcx-iddcxmonitorqueryhardwarecursor.md) and [**IddCxMonitorQueryHardwareCursor2**](nf-iddcx-iddcxmonitorqueryhardwarecursor2.md) to provide information about the cursor associated with the monitor.

## -struct-fields

### -field LastShapeId [in]

The ID of the last cursor shape the driver received for this monitor. This ID is compared against the latest shape ID that the OS has. The new shape is only copied to the buffer that **pShapeBuffer** points to if the OS version has been updated since the last image driver was received.

### -field ShapeBufferSizeInBytes [in]

Size in bytes of the cursor shape buffer that **pShapeBuffer** points to.

### -field pShapeBuffer [out]

Pointer to a driver-allocated buffer that the OS will copy any new cursor image data into.

## -see-also

[**IddCxMonitorQueryHardwareCursor**](nf-iddcx-iddcxmonitorqueryhardwarecursor.md)

 [**IddCxMonitorQueryHardwareCursor2**](nf-iddcx-iddcxmonitorqueryhardwarecursor2.md)
