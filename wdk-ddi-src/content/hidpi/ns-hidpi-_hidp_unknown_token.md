---
UID: NS:hidpi._HIDP_UNKNOWN_TOKEN
title: _HIDP_UNKNOWN_TOKEN (hidpi.h)
description: The HIDP_UNKNOWN_TOKEN structure contains information about a global item that the HID parser did not recognize.
old-location: hid\hidp_unknown_token.htm
tech.root: hid
ms.assetid: 6c9e0477-1698-41bf-9ce6-43e7e8741425
ms.date: 04/30/2018
ms.keywords: "*PHIDP_UNKNOWN_TOKEN, HIDP_UNKNOWN_TOKEN, HIDP_UNKNOWN_TOKEN structure [Human Input Devices], PHIDP_UNKNOWN_TOKEN, PHIDP_UNKNOWN_TOKEN structure pointer [Human Input Devices], _HIDP_UNKNOWN_TOKEN, hid.hidp_unknown_token, hidpi/HIDP_UNKNOWN_TOKEN, hidpi/PHIDP_UNKNOWN_TOKEN, hidstrct_646ea225-5fff-4430-9112-06bb4cf8c988.xml"
ms.topic: struct
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- hidpi.h
api_name:
- HIDP_UNKNOWN_TOKEN
product:
- Windows
targetos: Windows
req.typenames: HIDP_UNKNOWN_TOKEN, *PHIDP_UNKNOWN_TOKEN
---

# _HIDP_UNKNOWN_TOKEN structure


## -description


The HIDP_UNKNOWN_TOKEN structure contains information about a global item that the HID parser did not recognize.


## -struct-fields




### -field Token

Specifies the one-byte prefix of a global item.


### -field Reserved

Reserved for internal system use.


### -field BitField

Specifies the data part of the global item.


## -remarks



HIDP_UNKNOWN_TOKEN is designed to be used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539701">HIDP_EXTENDED_ATTRIBUTES</a> structure. <a href="https://msdn.microsoft.com/library/windows/hardware/ff539721">HidP_GetExtendedAttributes</a> returns a HIDP_EXTENDED_ATTRIBUTES structure, which contains a variable length array of <b>HIDP_UNKNOWN_TOKEN</b> structures.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539701">HIDP_EXTENDED_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539721">HidP_GetExtendedAttributes</a>
 

 

