---
UID: NS:hidspicx._HIDSPICX_REPORT
tech.root: hid
title: HIDSPICX_REPORT
ms.date: 06/14/2021
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

Input and output reports are represented using the **HIDSPICX_REPORT** structure.

## -struct-fields

### -field ReportType

The content type of the report.

### -field ReportContentLength

The length of the *ReportContent* field.

### -field ReportId

A unique report identifier.

### -field ReportContent

The raw HID report or command parameters.

## -remarks

This structure is used rather than the full report structure including the header as the client is expected to marshall the data structures to be sent on the wire.

## -see-also

[**HIDSPICX_DEVICE_CONFIG_INIT**](nf-hidspicx-hidspicx_device_config_init.md)

[**HIDSPICX_DEVICE_CONFIG**](ns-hidspicx-hidspicx_device_config.md)
