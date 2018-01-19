---
UID: NE:ntdd8042._KEYBOARD_SCAN_STATE
title: _KEYBOARD_SCAN_STATE
author: windows-driver-content
description: The KEYBOARD_SCAN_STATE enumeration type indicates the scan state of an input byte from a keyboard.
old-location: hid\keyboard_scan_state.htm
old-project: hid
ms.assetid: fd6cba1d-e32c-4ee8-b827-826e5065ca8b
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: _KEYBOARD_SCAN_STATE, *PKEYBOARD_SCAN_STATE, KEYBOARD_SCAN_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntdd8042.h
req.include-header: Ntdd8042.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KEYBOARD_SCAN_STATE
req.alt-loc: ntdd8042.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *PKEYBOARD_SCAN_STATE, KEYBOARD_SCAN_STATE
---

# _KEYBOARD_SCAN_STATE enumeration



## -description
The KEYBOARD_SCAN_STATE enumeration type indicates the scan state of an input byte from a keyboard.



## -syntax

````
typedef enum _KEYBOARD_SCAN_STATE { 
  Normal,
  GotE0,
  GotE1
} KEYBOARD_SCAN_STATE, *PKEYBOARD_SCAN_STATE;
````


## -enum-fields

### -field Normal

Indicates that the current byte is a <b>Normal</b> scan code (a nonextended code).


### -field GotE0

Indicates that the current byte is an E0 extended scan code.


### -field GotE1

Indicates that the current byte is an E1 extended scan code.


## -remarks
This enumeration type is used as input to an optional <a href="https://msdn.microsoft.com/0feca7de-aa80-4d1e-a5fc-901c18169649">KbFilter_IsrHook</a> routine, which can be supplied by a vendor-supplied keyboard filter driver.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/0feca7de-aa80-4d1e-a5fc-901c18169649">KbFilter_IsrHook</a>
</dt>
<dt>
<a href="..\ntdd8042\nc-ntdd8042-pi8042_keyboard_isr.md">PI8042_KEYBOARD_ISR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20KEYBOARD_SCAN_STATE enumeration%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

