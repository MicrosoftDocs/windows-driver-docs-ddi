---
UID: NS:hidpi._HIDP_EXTENDED_ATTRIBUTES
title: "_HIDP_EXTENDED_ATTRIBUTES"
author: windows-driver-content
description: The HIDP_EXTENDED_ATTRIBUTES structure contains information about the global items specified for a HID control that the HID parser did not recognize.
old-location: hid\hidp_extended_attributes.htm
old-project: hid
ms.assetid: 03be8b22-2108-4a13-be1e-642373095ab5
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: "*PHIDP_EXTENDED_ATTRIBUTES, HIDP_EXTENDED_ATTRIBUTES, HIDP_EXTENDED_ATTRIBUTES structure [Human Input Devices], PHIDP_EXTENDED_ATTRIBUTES, PHIDP_EXTENDED_ATTRIBUTES structure pointer [Human Input Devices], _HIDP_EXTENDED_ATTRIBUTES, hid.hidp_extended_attributes, hidpi/HIDP_EXTENDED_ATTRIBUTES, hidpi/PHIDP_EXTENDED_ATTRIBUTES, hidstrct_7f0e134c-f292-4558-b805-02861407032f.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	hidpi.h
api_name:
-	HIDP_EXTENDED_ATTRIBUTES
product:
- Windows
targetos: Windows
req.typenames: HIDP_EXTENDED_ATTRIBUTES, *PHIDP_EXTENDED_ATTRIBUTES
---

# _HIDP_EXTENDED_ATTRIBUTES structure


## -description


The HIDP_EXTENDED_ATTRIBUTES structure contains information about the global items specified for a HID control that the HID parser did not recognize.


## -struct-fields




### -field NumGlobalUnknowns

Specifies the number of <a href="https://msdn.microsoft.com/library/windows/hardware/ff539808">HIDP_UNKNOWN_TOKEN</a> structures in the list specified by <b>Data</b>.


### -field Reserved

Reserved for internal system use only.


### -field GlobalUnknowns

Reserved for internal system use only.


### -field Data

Specifies the memory location where <a href="https://msdn.microsoft.com/library/windows/hardware/ff539721">HidP_GetExtendedAttributes</a> returns a variable length array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff539808">HIDP_UNKNOWN_TOKEN</a> structures.


## -remarks



The HIDP_EXTENDED_ATTRIBUTES structure is designed to be used with <b>HidP_GetExtendedAttributes</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539808">HIDP_UNKNOWN_TOKEN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539721">HidP_GetExtendedAttributes</a>
 

 

