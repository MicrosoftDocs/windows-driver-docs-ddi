---
UID: NS:winsplp._MONITOREX
title: _MONITOREX (winsplp.h)
description: The MONITOREX structure is obsolete and supported for compatibility purposes only.
old-location: print\monitorex.htm
tech.root: print
ms.date: 03/21/2019
keywords: ["MONITOREX structure"]
ms.keywords: "*LPMONITOREX, LPMONITOREX, LPMONITOREX structure pointer [Print Devices], MONITOREX, MONITOREX structure [Print Devices], _MONITOREX, print.monitorex, spoolfnc_4910913b-826e-4947-8186-7737d7b3c3fa.xml, winsplp/LPMONITOREX, winsplp/MONITOREX"
req.header: winsplp.h
req.include-header: Winsplp.h
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
req.typenames: MONITOREX, *LPMONITOREX
f1_keywords:
 - _MONITOREX
 - winsplp/_MONITOREX
 - LPMONITOREX
 - winsplp/LPMONITOREX
 - MONITOREX
 - winsplp/MONITOREX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - winsplp.h
api_name:
 - _MONITOREX
 - LPMONITOREX
 - MONITOREX
---

# _MONITOREX structure


## -description

> [!IMPORTANT]
> The MONITOREX structure is obsolete and supported for compatibility purposes only. New print monitors should the implement [InitializePrintMonitor2](./nf-winsplp-initializeprintmonitor2.md) function and [MONITOR2](./ns-winsplp-_monitor2.md) structure so that they can be used with print server clusters.

The MONITOREX structure is used as the return value for a print monitor's [InitializePrintMonitor](./nf-winsplp-initializeprintmonitor.md) function.

## -struct-fields

### -field dwMonitorSize

Specifies the size, in bytes, of the Monitor **member**.

### -field Monitor

A [MONITOR](./ns-winsplp-_monitor.md) structure.

## -remarks

Print monitors are responsible for filling in the MONITOREX and MONITOR structures.

## -see-also

[MONITOR](./ns-winsplp-_monitor.md)

