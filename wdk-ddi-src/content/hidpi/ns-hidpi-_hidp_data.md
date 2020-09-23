---
UID: NS:hidpi._HIDP_DATA
title: _HIDP_DATA (hidpi.h)
description: The HIDP_DATA structure contains information about a HID control's data index and value in a HID report.
old-location: hid\hidp_data.htm
tech.root: hid
ms.assetid: f48bbf84-027f-4579-b83c-7dfb1cbe6b65
ms.date: 04/30/2018
keywords: ["HIDP_DATA structure"]
ms.keywords: "*PHIDP_DATA, HIDP_DATA, HIDP_DATA structure [Human Input Devices], PHIDP_DATA, PHIDP_DATA structure pointer [Human Input Devices], _HIDP_DATA, hid.hidp_data, hidpi/HIDP_DATA, hidpi/PHIDP_DATA, hidstrct_690e0e92-9de7-44e0-8550-4f84d7bb768e.xml"
req.header: hidpi.h
req.include-header: Hidpi.h
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
req.typenames: HIDP_DATA, *PHIDP_DATA
f1_keywords:
 - _HIDP_DATA
 - hidpi/_HIDP_DATA
 - PHIDP_DATA
 - hidpi/PHIDP_DATA
 - HIDP_DATA
 - hidpi/HIDP_DATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hidpi.h
api_name:
 - HIDP_DATA
---

# _HIDP_DATA structure


## -description

The HIDP_DATA structure contains information about a HID control's <a href="/windows-hardware/drivers/hid/data-indices">data index</a> and value in a HID report.

## -struct-fields

### -field DataIndex

Specifies the data index of a control.

### -field Reserved

Reserved for internal system use only.

### -field RawValue

Contains the binary data extracted from a report if the control is a value.

### -field On

Specifies, if <b>TRUE</b> and the control is a button, that the button is set to ON (1). Otherwise, if <b>On</b> is <b>FALSE</b> and the control is a button, the button is set to OFF (zero).

## -remarks

See <a href="/windows-hardware/drivers/hid/extracting-and-setting-control-data-by-data-indices">Extracting and Setting Control Data by Data Indices</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getdata">HidP_GetData</a>



<a href="/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_setdata">HidP_SetData</a>