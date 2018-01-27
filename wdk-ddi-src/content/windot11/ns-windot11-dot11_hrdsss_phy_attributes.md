---
UID: NS:windot11.DOT11_HRDSSS_PHY_ATTRIBUTES
title: DOT11_HRDSSS_PHY_ATTRIBUTES
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_hrdsss_phy_attributes.htm
old-project: netvista
ms.assetid: 435e74b4-1a29-4031-bf21-92eae71e99a1
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: DOT11_HRDSSS_PHY_ATTRIBUTES, windot11/PDOT11_HRDSSS_PHY_ATTRIBUTES, DOT11_HRDSSS_PHY_ATTRIBUTES structure [Network Drivers Starting with Windows Vista], PDOT11_HRDSSS_PHY_ATTRIBUTES structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_hrdsss_phy_attributes, Native_802.11_data_types_5223e673-249b-42b9-9939-6d4d9aad5e0b.xml, windot11/DOT11_HRDSSS_PHY_ATTRIBUTES, *PDOT11_HRDSSS_PHY_ATTRIBUTES, PDOT11_HRDSSS_PHY_ATTRIBUTES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	DOT11_HRDSSS_PHY_ATTRIBUTES
product: Windows
targetos: Windows
req.typenames: DOT11_HRDSSS_PHY_ATTRIBUTES, *PDOT11_HRDSSS_PHY_ATTRIBUTES
req.product: Windows 10 or later.
---

# DOT11_HRDSSS_PHY_ATTRIBUTES structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_HRDSSS_PHY_ATTRIBUTES structure defines the attributes specific to a high-rate
  direct-sequence spread spectrum (HRDSS) PHY type.


## -syntax


````
typedef struct DOT11_HRDSSS_PHY_ATTRIBUTES {
  BOOLEAN bShortPreambleOptionImplemented;
  BOOLEAN bPBCCOptionImplemented;
  BOOLEAN bChannelAgilityPresent;
  ULONG   uHRCCAModeSupported;
} DOT11_HRDSSS_PHY_ATTRIBUTES, *PDOT11_HRDSSS_PHY_ATTRIBUTES;
````


## -struct-fields




### -field bShortPreambleOptionImplemented

A Boolean value that, if set to <b>TRUE</b>, specifies that the PHY supports the option to enable the
     short Physical Layer Convergence Procedure (PLCP) preamble and header. For more information about the
     short PLCP preamble and header, refer to Clause 18.2.2.2 of the IEEE 802.11b-1999 standard


### -field bPBCCOptionImplemented

A Boolean value that, if set to <b>TRUE</b>, specifies that the PHY supports enabled packet binary
     convolutional code (PBCC) modulation. For more information about PBCC modulation, refer to Clause
     18.4.6.6 of the IEEE 802.11b-1999 standard.


### -field bChannelAgilityPresent

A Boolean value that, if set to <b>TRUE</b>, specifies that the PHY supports channel agility. For more
     information about channel agility, refer to Clause 18 of the IEEE 802.11b-1999 standard and Clause 19 of
     the IEEE 802.11g-2003 standard.


### -field uHRCCAModeSupported

The type of clear channel assessment (CCA) mode supported by the current PHY type. For more
     information about CCA, refer to Clause 16.4.8.5 of the IEEE 802.11-2012 standard and Clause 18.4.8.4 of
     the IEEE 802.11b-1999 standard.
     

The CCA modes supported by the PHY are defined through the following bitmask:




##### - uHRCCAModeSupported.DOT11_CCA_MODE_CS_ONLY (0x00000002)

CCA mode using the carrier sense (CS) signal. For more information about the CS signal, refer to
       Clause 15.4.6.2 of the IEEE 802.11-2012 standard.


##### - uHRCCAModeSupported.DOT11_HR_CCA_MODE_CS_WITH_TIMER (0x00000008)

CCA mode using the CS signal with a timer. For more information about this CCA mode, refer to
       Clause 18.4.8.4 of the IEEE 802.11b-1999 standard.


##### - uHRCCAModeSupported.DOT11_HR_CCA_MODE_HRCS_AND_ED (0x00000010)

Both ED and CS modes on high-rate (HR) PHYs. For more information about this CCA mode, refer to
       Clause 18.4.8.4 of the IEEE 802.11b-1999 standard.


##### - uHRCCAModeSupported.DOT11_CCA_MODE_ED_and_CS (0x00000004)

Both ED and CS modes.


##### - uHRCCAModeSupported.DOT11_CCA_MODE_ED_ONLY (0x00000001)

CCA mode using the energy detect (ED) signal. For more information about the ED signal, refer to
       Clause 15.4.6.1 of the IEEE 802.11-2012 standard.


## -remarks


The miniport driver defines the attributes of a PHY on the 802.11 station through the 
    <a href="..\windot11\ns-windot11-dot11_phy_attributes.md">DOT11_PHY_ATTRIBUTES</a> structure, and
    formats the 
    <b>HRDSSSAttributes</b> member as a DOT11_HRDSSS_PHY_ATTRIBUTES structure. The driver must only do this if
    the PHY defined by the DOT11_PHY_ATTRIBUTES structure is an HRDSSS PHY type.



## -see-also

<a href="..\windot11\ns-windot11-dot11_phy_attributes.md">DOT11_PHY_ATTRIBUTES</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_HRDSSS_PHY_ATTRIBUTES structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

