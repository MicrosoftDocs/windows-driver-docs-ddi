---
UID: NS:windot11._DOT11_PHY_TYPE_INFO
title: "_DOT11_PHY_TYPE_INFO"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_phy_type_info.htm
old-project: netvista
ms.assetid: 9b0cbcc4-e38a-4266-afc5-8b2755d79f4c
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.dot11_phy_type_info, PDOT11_PHY_TYPE_INFO structure pointer [Network Drivers Starting with Windows Vista], *PDOT11_PHY_TYPE_INFO, windot11/DOT11_PHY_TYPE_INFO, PDOT11_PHY_TYPE_INFO, _DOT11_PHY_TYPE_INFO, Native_802.11_data_types_20e3d688-253f-416e-b9b0-8adec6bf7415.xml, windot11/PDOT11_PHY_TYPE_INFO, DOT11_PHY_TYPE_INFO, DOT11_PHY_TYPE_INFO structure [Network Drivers Starting with Windows Vista]
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
-	DOT11_PHY_TYPE_INFO
product: Windows
targetos: Windows
req.typenames: "*PDOT11_PHY_TYPE_INFO, DOT11_PHY_TYPE_INFO"
req.product: Windows 10 or later.
---

# _DOT11_PHY_TYPE_INFO structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_PHY_TYPE_INFO structure defines parameters that the 802.11 station uses to configure a PHY
  when performing an explicit scan operation. The station performs the explicit scan operation following a
  set request of 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff569413">OID_DOT11_SCAN_REQUEST</a>.


## -syntax


````
typedef struct _DOT11_PHY_TYPE_INFO {
  union {
    DOT11_PHY_TYPE dot11PhyType;
    ULONG          uPhyId;
  };
  BOOLEAN             bUseParameters;
  ULONG               uProbeDelay;
  ULONG               uMinChannelTime;
  ULONG               uMaxChannelTime;
  CH_DESCRIPTION_TYPE ChDescriptionType;
  ULONG               uChannelListSize;
  UCHAR               ucChannelListBuffer[1];
} DOT11_PHY_TYPE_INFO, *PDOT11_PHY_TYPE_INFO;
````


## -struct-fields




### -field dot11PhyType

The type of PHY that the 802.11 station will use for the scan. The PHY type is defined by the 
       <a href="..\windot11\ne-windot11-_dot11_phy_type.md">DOT11_PHY_TYPE</a> enumeration. 
       <div class="alert"><b>Note</b>  The miniport driver must ignore this member if it is operating in Extensible
       Station (ExtSTA) mode.</div>
<div> </div>



### -field bUseParameters

If this member is <b>TRUE</b>, the 802.11 station uses the other members of this structure to configure
     the PHY for the scan operation.
     

If this member is <b>FALSE</b>, the 802.11 station configures the PHY using its own settings for the scan
     operation.


<div class="alert"><b>Note</b>  If the miniport driver is operating in ExtSTA mode, the operating system will
      always set this member to <b>FALSE</b>.</div>
<div> </div>



### -field uProbeDelay

The amount of time, in microseconds, that the 802.11 station must wait before transmitting an
     802.11 Probe Request frame during active scanning.


### -field uMinChannelTime

The minimum amount of time, in 802.11 time units (TU), that the 802.11 station spends on each
     channel when scanning. One TU is 1024 microseconds.
     

This member must be greater than or equal to 
     <b>uProbeDelay</b> .


### -field uMaxChannelTime

The maximum amount of time, in 802.11 time units (TU), that the 802.11 station spends on each
     channel when scanning.
     

This member must be greater than or equal to 
     <b>uProbeDelay</b> .


### -field ChDescriptionType

This member specifies the method used to interpret the entries in the 
     <b>ucChannelListBuffer</b> array. The data type for this member is the CH_DESCRIPTION_TYPE enumeration,
     which declares the following values:
     





#### ch_description_type_logical

The channel entry is defined by a logical channel number to conform with the IEEE 802.11
       standard.



#### ch_description_type_center_frequency

The channel entry is defined, in units of megahertz (MHz), by a channel center frequency.


### -field uChannelListSize

The length, in bytes, of the 
     <b>ucChannelListBuffer</b> array. Each entry in this array is formatted as a ULONG data type.


### -field ucChannelListBuffer

An array containing channel descriptions for the PHY type specified in the 
     <b>dot11PhyType</b> member.


#### - uPhyId

The identifier (ID) of the PHY that the 802.11 station will use for the scan. The PHY ID is the
       index within the list of supported PHYs returned by the driver through a query of 
       <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-supported-phy-types">
       OID_DOT11_SUPPORTED_PHY_TYPES</a>.

<div class="alert"><b>Note</b>  The miniport driver must ignore this member if it is operating in ExtSTA
       mode.</div>
<div> </div>

## -remarks



The 
    <a href="..\windot11\ns-windot11-_dot11_scan_request_v2.md">DOT11_SCAN_REQUEST_V2</a> structure, which
    accompanies a set request of 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569413">OID_DOT11_SCAN_REQUEST</a>, contains an
    array of zero or more DOT11_PHY_TYPE_INFO entries.

For more information about the scan operations performed by a Native 802.11 miniport driver, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/native-802-11-scan-operations">Native 802.11 Scan
    Operations</a>.

For more information about the ExtSTA operation mode, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/extensible-station-operation-mode">Extensible Station Operation
    Mode</a>.




## -see-also

<a href="..\windot11\ns-windot11-_dot11_scan_request_v2.md">DOT11_SCAN_REQUEST_V2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569413">OID_DOT11_SCAN_REQUEST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_PHY_TYPE_INFO structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

