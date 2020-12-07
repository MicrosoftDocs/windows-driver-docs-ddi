---
UID: NS:iddcx.IDARG_IN_QUERY_HWCURSOR
title: IDARG_IN_QUERY_HWCURSOR (iddcx.h)
description: Gives information about the cursor associated with the monitor.
old-location: display\idarg_in_query_hwcursor.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["IDARG_IN_QUERY_HWCURSOR structure"]
ms.keywords: IDARG_IN_QUERY_HWCURSOR, IDARG_IN_QUERY_HWCURSOR structure [Display Devices], PIDARG_IN_QUERY_HWCURSOR, PIDARG_IN_QUERY_HWCURSOR structure pointer [Display Devices], display.idarg_in_query_hwcursor, iddcx/IDARG_IN_QUERY_HWCURSOR, iddcx/PIDARG_IN_QUERY_HWCURSOR
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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

Gives information about the cursor associated with the monitor.

## -struct-fields

### -field LastShapeId

[in] The shape id of the last cursor shape the driver received for this monitor. This is compared against the latest shape the OS has. The new shape is only copied to the buffer if the OS version has been updated since the last image driver was        received.

### -field ShapeBufferSizeInBytes

[in] Size of the cursor shape buffer <b>pShapeBuffer</b>.

### -field pShapeBuffer

[out] Buffer provided by driver that the OS will copy any new cursor image data into.

