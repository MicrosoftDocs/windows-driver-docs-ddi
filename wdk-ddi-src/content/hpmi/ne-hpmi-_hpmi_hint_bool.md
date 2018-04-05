---
UID: NE:hpmi._HPMI_HINT_BOOL
title: "_HPMI_HINT_BOOL"
author: windows-driver-content
description: Boolean type value used to track availability of HPMI hint data.
old-location: powermeter\hpmi_hint_bool.htm
old-project: powermeter
ms.assetid: E056400C-A0FE-4740-945D-C529C8804DF3
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PHPMI_HINT_BOOL, HPMI_HINT_BOOL, HPMI_HINT_BOOL enumeration [Power Metering and Budgeting Devices], HpmiBoolFalse, HpmiBoolMax, HpmiBoolTrue, HpmiBoolUnavailable, _HPMI_HINT_BOOL, hpmi/HPMI_HINT_BOOL, hpmi/HpmiBoolFalse, hpmi/HpmiBoolMax, hpmi/HpmiBoolTrue, hpmi/HpmiBoolUnavailable, powermeter.hpmi_hint_bool"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: hpmi.h
req.include-header: Hpmi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10, version 1709 and later versions of the Windows operating systems.
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
-	hpmi.h
api_name:
-	HPMI_HINT_BOOL
product:
- Windows
targetos: Windows
req.typenames: HPMI_HINT_BOOL, *PHPMI_HINT_BOOL
---

# _HPMI_HINT_BOOL enumeration


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

Boolean type value used to track availability of HPMI hint data. 


## -syntax


````
typedef enum _HPMI_HINT_BOOL { 
  HpmiBoolUnavailable  = 0,
  HpmiBoolFalse        = ,
  HpmiBoolTrue         = ,
  HpmiBoolMax          = 
} HPMI_HINT_BOOL;
````


## -enum-fields




### -field HpmiBoolUnavailable

No data is available.


### -field HpmiBoolFalse

Condition is asserted to be false.


### -field HpmiBoolTrue

Condition is asserted to be true.


### -field HpmiBoolMax

Value is not used. 


## -see-also

<a href="https://msdn.microsoft.com/35934D6C-3FB4-4AD4-AA50-BD3A7790269F">hpmi.h</a>



<a href="..\hpmi\ni-hpmi-ioctl_hpmi_battery_utilization_hint.md">IOCTL_HPMI_BATTERY_UTILIZATION_HINT</a>



<a href="..\hpmi\ns-hpmi-_hpmi_battery_utilization_hint.md">HPMI_BATTERY_UTILIZATION_HINT</a>



 

 


