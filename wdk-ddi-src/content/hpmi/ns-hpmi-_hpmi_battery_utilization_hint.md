---
UID: NS:hpmi._HPMI_BATTERY_UTILIZATION_HINT
title: "_HPMI_BATTERY_UTILIZATION_HINT"
author: windows-driver-content
description: This hint indicates if the OEM Battery Manager should attempt to save as much charge as possible in the non-hot swappable batteries (i.e.
old-location: powermeter\hpmi_battery_utilization_hint.htm
old-project: powermeter
ms.assetid: A974998F-C9AF-496E-88B1-510413C17C4A
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: HPMI_BATTERY_UTILIZATION_HINT structure [Power Metering and Budgeting Devices], HPMI_BATTERY_UTILIZATION_HINT, hpmi/HPMI_BATTERY_UTILIZATION_HINT, powermeter.hpmi_battery_utilization_hint, PHPMI_BATTERY_UTILIZATION_HINT, PHPMI_BATTERY_UTILIZATION_HINT structure pointer [Power Metering and Budgeting Devices], *PHPMI_BATTERY_UTILIZATION_HINT, hpmi/PHPMI_BATTERY_UTILIZATION_HINT, _HPMI_BATTERY_UTILIZATION_HINT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hpmi.h
req.include-header: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	hpmi.h
apiname:
-	HPMI_BATTERY_UTILIZATION_HINT
product: Windows
targetos: Windows
req.typenames: HPMI_BATTERY_UTILIZATION_HINT, *PHPMI_BATTERY_UTILIZATION_HINT
---

# _HPMI_BATTERY_UTILIZATION_HINT structure


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

This hint indicates if the OEM Battery Manager should attempt to save as
	much charge as possible in the non-hot swappable batteries (i.e. the
	batteries are generally referred to as "internal batteries", these
	batteries cannot be removed while system is operational).


## -syntax


````
typedef struct _HPMI_BATTERY_UTILIZATION_HINT {
  ULONG          Version;
  HPMI_HINT_BOOL PreserveNonHotSwappableBatteries;
} HPMI_BATTERY_UTILIZATION_HINT, *PHPMI_BATTERY_UTILIZATION_HINT;
````


## -struct-fields




### -field Version

Set to HPMI_BATTERY_UTILIZATION_HINT_VERSION_1.


### -field PreserveNonHotSwappableBatteries

 Interpretation of values:


    - HpmiBoolUnavailable:
    Battery utilization hint is unavailable at the moment.

  - HpmiBoolFalse:
    It is not necessary to preserve charge in the internal batteries
	at the moment.

- HpmiBoolTrue:
    Every attempt should be made to save as much charge as possible in
    the internal batteries.


## -see-also

<a href="..\hpmi\ne-hpmi-_hpmi_hint_bool.md">HPMI_HINT_BOOL</a>



<a href="..\hpmi\ni-hpmi-ioctl_hpmi_battery_utilization_hint.md">IOCTL_HPMI_BATTERY_UTILIZATION_HINT</a>



<a href="https://msdn.microsoft.com/35934D6C-3FB4-4AD4-AA50-BD3A7790269F">hpmi.h</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [powermeter\powermeter]:%20HPMI_BATTERY_UTILIZATION_HINT structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

