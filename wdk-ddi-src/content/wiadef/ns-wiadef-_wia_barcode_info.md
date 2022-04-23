---
UID: NS:wiadef._WIA_BARCODE_INFO
title: WIA_BARCODE_INFO (wiadef.h)
description: The WIA_BARCODE_INFO structure stores information for one decoded barcode.
tech.root: image
ms.date: 04/19/2022
keywords: ["WIA_BARCODE_INFO structure"]
ms.keywords: WIA_BARCODE_INFO, WIA_BARCODE_INFO structure [Imaging Devices], _WIA_BARCODE_INFO, image.wia_barcode_info, wiadef/WIA_BARCODE_INFO
req.header: wiadef.h
req.include-header: Wiadef.h
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
req.typenames: WIA_BARCODE_INFO
f1_keywords:
 - _WIA_BARCODE_INFO
 - wiadef/_WIA_BARCODE_INFO
 - WIA_BARCODE_INFO
 - wiadef/WIA_BARCODE_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wiadef.h
api_name:
 - _WIA_BARCODE_INFO
 - WIA_BARCODE_INFO
---

## -description

The **WIA_BARCODE_INFO** structure stores information for one decoded barcode.

## -struct-fields

### -field Size

The total size of this structure, in bytes.

### -field Type

The barcode type. One of the [WIA_IPS_SUPPORTED_BARCODE_TYPES](/windows-hardware/drivers/image/wia-ips-supported-barcode-types) values.

### -field Page

The page number where the barcode was detected. A zero-based index referring to the current scan job.

### -field Confidence

The confidence level. A value in the range from 0 (no confidence) to 10 (maximum confidence).

### -field XOffset

The horizontal coordinate, in pixels (relative to the scanned image), where the top-left origin of the barcode was detected. This value can be 0 if it is unknown.

### -field YOffset

The vertical coordinate, in pixels (relative to the scanned image), where the top-left origin of the barcode was detected. This value can be 0 if it is unknown.

### -field Rotation

The rotation of the barcode, in degrees. A value in the rage from 0 to 359. This value can be 0 if it is unknown.

### -field Length

The number of text characters in the character string containing the decoded barcode text, excluding the length of the NULL terminator.

### -field Text

Placeholder for the character string containing the decoded barcode text (double byte characters, NULL terminated).
