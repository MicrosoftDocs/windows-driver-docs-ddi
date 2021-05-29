---
UID: NS:hidspicx._HIDSPICX_REPORT
tech.root: hid
title: HIDSPICX_REPORT
ms.date: 
targetos: Windows
description: 
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: hidspicx.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: WIN10_NEXT
req.target-min-winversvr: 
req.target-type: 
req.typenames: HIDSPICX_REPORT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - hidspicx.h
api_name:
 - _HIDSPICX_REPORT
 - HIDSPICX_REPORT
f1_keywords:
 - _HIDSPICX_REPORT
 - hidspicx/_HIDSPICX_REPORT
 - HIDSPICX_REPORT
 - hidspicx/HIDSPICX_REPORT
dev_langs:
 - c++
---

## -description

Input and Output reports are represented using the **HIDSPICX_REPORT** structure.

## -struct-fields

### -field ReportType

### -field ReportContentLength

### -field ReportId

### -field ReportContent

## -remarks

The fields correspond to their meanings as defined in the HIDSPI protocol specification, and the structure above is identical to the body part of a HIDSPI report. This is used rather than the full HIDSPI report structure including header, as the client is expected to marshall the data structures to be sent on the wire.

## -see-also
