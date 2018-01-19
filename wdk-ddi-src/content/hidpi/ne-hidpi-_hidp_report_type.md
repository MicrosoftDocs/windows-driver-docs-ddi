---
UID: NE:hidpi._HIDP_REPORT_TYPE
title: _HIDP_REPORT_TYPE
author: windows-driver-content
description: The HIDP_REPORT_TYPE enumeration type is used to specify a HID report type.
old-location: hid\hidp_report_type.htm
old-project: hid
ms.assetid: adb2f0cc-f261-41d2-b30f-58286b351e4f
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: _HIDP_REPORT_TYPE, HIDP_REPORT_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: hidpi.h
req.include-header: Hidpi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HIDP_REPORT_TYPE
req.alt-loc: hidpi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: HIDP_REPORT_TYPE
---

# _HIDP_REPORT_TYPE enumeration



## -description
The HIDP_REPORT_TYPE enumeration type is used to specify a HID report type.



## -syntax

````
typedef enum _HIDP_REPORT_TYPE { 
  HidP_Input,
  HidP_Output,
  HidP_Feature
} HIDP_REPORT_TYPE;
````


## -enum-fields

### -field HidP_Input

Indicates an input report.


### -field HidP_Output

Indicates an output report.


### -field HidP_Feature

Indicates a feature report.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\hidpi\nf-hidpi-hidp_getdata.md">HidP_GetData</a>
</dt>
<dt>
<a href="..\hidpi\nf-hidpi-hidp_setdata.md">HidP_SetData</a>
</dt>
<dt>
<a href="..\hidpi\ns-hidpi-_hidp_button_caps.md">HIDP_BUTTON_CAPS</a>
</dt>
<dt>
<a href="..\hidpi\ns-hidpi-_hidp_value_caps.md">HIDP_VALUE_CAPS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HIDP_REPORT_TYPE enumeration%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

