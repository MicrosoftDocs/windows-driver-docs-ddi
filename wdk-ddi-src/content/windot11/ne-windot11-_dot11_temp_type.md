---
UID: NE:windot11._DOT11_TEMP_TYPE
title: "_DOT11_TEMP_TYPE"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_temp_type.htm
old-project: netvista
ms.assetid: 73275e2e-b738-4adc-b89e-2cd152de6c75
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*PDOT11_TEMP_TYPE, dot11_temp_type_unknown, windot11/DOT11_TEMP_TYPE, dot11_temp_type_2, windot11/dot11_temp_type_2, PDOT11_TEMP_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], PDOT11_TEMP_TYPE, DOT11_TEMP_TYPE, Native_802.11_data_types_5b580f41-75a6-4d16-9ea5-cc3dc3622a84.xml, windot11/dot11_temp_type_1, DOT11_TEMP_TYPE enumeration [Network Drivers Starting with Windows Vista], windot11/dot11_temp_type_unknown, netvista.dot11_temp_type, windot11/PDOT11_TEMP_TYPE, _DOT11_TEMP_TYPE, dot11_temp_type_1"
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
-	DOT11_TEMP_TYPE
product: Windows
targetos: Windows
req.typenames: DOT11_TEMP_TYPE, *PDOT11_TEMP_TYPE
req.product: Windows 10 or later.
---

# _DOT11_TEMP_TYPE enumeration


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_TEMP_TYPE enumeration specifies the operating temperature range of a PHY on the 802.11
  station.


## -syntax


````
typedef enum _DOT11_TEMP_TYPE { 
  dot11_temp_type_unknown  = 0,
  dot11_temp_type_1        = 1,
  dot11_temp_type_2        = 2
} DOT11_TEMP_TYPE, *PDOT11_TEMP_TYPE;
````


## -enum-fields




### -field dot11_temp_type_unknown

An uninitialized or unknown temperature type.


### -field dot11_temp_type_1

The commercial temperature range from 0 through 40 degrees Celsius.


### -field dot11_temp_type_2

The industrial temperature range from -30 through 70 degrees Celsius.


## -remarks



There are different operating temperature requirements dependent on the anticipated environmental
    conditions. The DOT11_TEMP_TYPE enumeration describes a PHY's operating temperature range capability.




## -see-also

<a href="..\windot11\ns-windot11-dot11_phy_attributes.md">DOT11_PHY_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569431">OID_DOT11_TEMP_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_TEMP_TYPE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

