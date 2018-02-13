---
UID: NE:windot11._DOT11_POWER_MODE
title: "_DOT11_POWER_MODE"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_power_mode.htm
old-project: netvista
ms.assetid: 4f18f937-e749-414d-aa21-96c6ab02982b
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: windot11/dot11_power_mode_powersave, *PDOT11_POWER_MODE, PDOT11_POWER_MODE, windot11/dot11_power_mode_active, dot11_power_mode_active, windot11/dot11_power_mode_unknown, Native_802.11_data_types_0c9f7464-7651-46e6-910b-2794649d13d0.xml, dot11_power_mode_powersave, windot11/PDOT11_POWER_MODE, _DOT11_POWER_MODE, DOT11_POWER_MODE enumeration [Network Drivers Starting with Windows Vista], windot11/DOT11_POWER_MODE, netvista.dot11_power_mode, dot11_power_mode_unknown, PDOT11_POWER_MODE enumeration pointer [Network Drivers Starting with Windows Vista], DOT11_POWER_MODE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
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
-	windot11.h
apiname:
-	DOT11_POWER_MODE
product: Windows
targetos: Windows
req.typenames: DOT11_POWER_MODE, *PDOT11_POWER_MODE
req.product: Windows 10 or later.
---

# _DOT11_POWER_MODE enumeration


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_POWER_MODE enumeration defines a power management mode for the PHY on the 802.11
  station.


## -syntax


````
typedef enum _DOT11_POWER_MODE { 
  dot11_power_mode_unknown    = 0,
  dot11_power_mode_active     = 1,
  dot11_power_mode_powersave  = 2
} DOT11_POWER_MODE, *PDOT11_POWER_MODE;
````


## -enum-fields




### -field dot11_power_mode_unknown

Specifies an undefined or uninitialized power mode.


### -field dot11_power_mode_active

Specifies an active power mode in which the PHY is always turned on.


### -field dot11_power_mode_powersave

Specifies a power-save mode in which the PHY is periodically turned off.


## -remarks



An 802.11 station advertises its power management mode through the Power Management subfield of the
    Frame Control field in the 802.11 MAC header of transmitted frames. For more information about the Power
    Management subfield, refer to Clause 8.2.4.1.7 of the IEEE 802.11-2012 standard.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569359">OID_DOT11_ENUM_ASSOCIATION_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_POWER_MODE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

