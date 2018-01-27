---
UID: NE:windot11._DOT11_PHY_TYPE
title: _DOT11_PHY_TYPE
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_phy_type.htm
old-project: netvista
ms.assetid: 45ef8085-512e-4f9b-a7ea-e4f445555cf8
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: PDOT11_PHY_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], windot11/dot11_phy_type_unknown, dot11_phy_type_fhss, dot11_phy_type_irbaseband, windot11/DOT11_PHY_TYPE, windot11/dot11_phy_type_dsss, dot11_phy_type_ht, dot11_phy_type_dsss, windot11/dot11_phy_type_ofdm, windot11/dot11_phy_type_IHV_start, windot11/dot11_phy_type_fhss, _DOT11_PHY_TYPE, dot11_phy_type_IHV_start, dot11_phy_type_hrdsss, windot11/dot11_phy_type_any, PDOT11_PHY_TYPE, DOT11_PHY_TYPE enumeration [Network Drivers Starting with Windows Vista], windot11/dot11_phy_type_ht, *PDOT11_PHY_TYPE, DOT11_PHY_TYPE, netvista.dot11_phy_type, dot11_phy_type_any, windot11/dot11_phy_type_irbaseband, dot11_phy_type_erp, windot11/dot11_phy_type_erp, dot11_phy_type_ofdm, dot11_phy_type_vht, windot11/dot11_phy_type_IHV_end, dot11_phy_type_IHV_end, windot11/PDOT11_PHY_TYPE, windot11/dot11_phy_type_vht, dot11_phy_type_unknown, Native_802.11_data_types_814496a3-4f7e-44a0-925c-0dbf64eb3f72.xml, windot11/dot11_phy_type_hrdsss
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
-	DOT11_PHY_TYPE
product: Windows
targetos: Windows
req.typenames: DOT11_PHY_TYPE, *PDOT11_PHY_TYPE
req.product: Windows 10 or later.
---

# _DOT11_PHY_TYPE enumeration


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_PHY_TYPE enumeration defines an 802.11 PHY and media type.


## -syntax


````
typedef enum _DOT11_PHY_TYPE { 
  dot11_phy_type_unknown     = 0,
  dot11_phy_type_any         = dot11_phy_type_unknown,
  dot11_phy_type_fhss        = 1,
  dot11_phy_type_dsss        = 2,
  dot11_phy_type_irbaseband  = 3,
  dot11_phy_type_ofdm        = 4,
  dot11_phy_type_hrdsss      = 5,
  dot11_phy_type_erp         = 6,
  dot11_phy_type_ht          = 7,
  dot11_phy_type_vht         = 8,
  dot11_phy_type_IHV_start   = 0x80000000,
  dot11_phy_type_IHV_end     = 0xffffffff
} DOT11_PHY_TYPE, *PDOT11_PHY_TYPE;
````


## -enum-fields




### -field dot11_phy_type_unknown

Specifies an unknown or uninitialized PHY type.


### -field dot11_phy_type_any

Specifies an unknown or uninitialized PHY type.


### -field dot11_phy_type_fhss

Specifies a frequency-hopping spread-spectrum (FHSS) PHY.


### -field dot11_phy_type_dsss

Specifies a direct sequence spread spectrum (DSSS) PHY.


### -field dot11_phy_type_irbaseband

Specifies an infrared (IR) baseband PHY.


### -field dot11_phy_type_ofdm

Specifies an orthogonal frequency division multiplexing (OFDM) 802.11a PHY.


### -field dot11_phy_type_hrdsss

Specifies a high-rate DSSS (HRDSSS) 802.11b PHY.


### -field dot11_phy_type_erp

Specifies an extended-rate 802.11g PHY (ERP).


### -field dot11_phy_type_ht

Specifies a high-throughput (HT) 802.11n PHY. Each 802.11n PHY, whether dual-band or not, is
     specified as this PHY type.


### -field dot11_phy_type_vht

Specifies a very high-throughput (VHT) 802.11ac PHY.


### -field dot11_phy_type_dmg



### -field dot11_phy_type_IHV_start

Specifies the start of the range that is used to define proprietary PHY types that are developed
     by an independent hardware vendor (IHV).
     

The 
     <b>dot11_phy_type_IHV_start</b> enumerator value is valid only when the miniport driver is operating in
     Extensible Station (ExtSTA) mode.


### -field dot11_phy_type_IHV_end

Specifies the end of the range that is used to define proprietary PHY types that are developed by
     an IHV.
     

The 
     <b>dot11_phy_type_IHV_end</b> enumerator value is valid only when the miniport driver is operating in
     ExtSTA mode.


### -field v1_enum




## -remarks


An IHV can assign a value for its proprietary PHY types from 
    <b>dot11_phy_type_IHV_start</b> through 
    <b>dot11_phy_type_IHV_end</b>. The IHV must assign a unique number from this range for each of its
    proprietary PHY types.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569407">OID_DOT11_RECV_SENSITIVITY_LIST</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-supported-phy-types">OID_DOT11_SUPPORTED_PHY_TYPES</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569413">OID_DOT11_SCAN_REQUEST</a>

<mshelp:link keywords="netvista.dot11_association_completion_parameters" tabindex="0"><b>
   DOT11_ASSOCIATION_COMPLETION_PARAMETERS</b></mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_PHY_TYPE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

