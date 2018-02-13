---
UID: NS:windot11._DOT11_SUPPORTED_OFDM_FREQUENCY_LIST
title: "_DOT11_SUPPORTED_OFDM_FREQUENCY_LIST"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_supported_ofdm_frequency_list.htm
old-project: netvista
ms.assetid: 0c967358-821b-4f78-acbc-dacee24dcd57
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: DOT11_SUPPORTED_OFDM_FREQUENCY_LIST structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_428915da-fa98-469c-829b-5d0313a59c3b.xml, windot11/PDOT11_SUPPORTED_OFDM_FREQUENCY_LIST, PDOT11_SUPPORTED_OFDM_FREQUENCY_LIST, windot11/DOT11_SUPPORTED_OFDM_FREQUENCY_LIST, *PDOT11_SUPPORTED_OFDM_FREQUENCY_LIST, netvista.dot11_supported_ofdm_frequency_list, _DOT11_SUPPORTED_OFDM_FREQUENCY_LIST, PDOT11_SUPPORTED_OFDM_FREQUENCY_LIST structure pointer [Network Drivers Starting with Windows Vista], DOT11_SUPPORTED_OFDM_FREQUENCY_LIST
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating   systems.
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
-	DOT11_SUPPORTED_OFDM_FREQUENCY_LIST
product: Windows
targetos: Windows
req.typenames: "*PDOT11_SUPPORTED_OFDM_FREQUENCY_LIST, DOT11_SUPPORTED_OFDM_FREQUENCY_LIST"
req.product: Windows 10 or later.
---

# _DOT11_SUPPORTED_OFDM_FREQUENCY_LIST structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_SUPPORTED_OFDM_FREQUENCY_LIST structure specifies a list of channel center frequencies that
  the 802.11 station can operate with.


## -syntax


````
typedef struct _DOT11_SUPPORTED_OFDM_FREQUENCY_LIST {
  ULONG                          uNumOfEntries;
  ULONG                          uTotalNumOfEntries;
  DOT11_SUPPORTED_OFDM_FREQUENCY dot11SupportedOFDMFrequency[1];
} DOT11_SUPPORTED_OFDM_FREQUENCY_LIST, *PDOT11_SUPPORTED_OFDM_FREQUENCY_LIST;
````


## -struct-fields




### -field uNumOfEntries

The number of entries in the 
     <b>dot11SupportedOFDMFrequency</b> array.


### -field uTotalNumOfEntries

The maximum number of entries that the 
     <b>dot11SupportedOFDMFrequency</b> array can contain.


### -field dot11SupportedOFDMFrequency

An array that specifies the list of supported channel center frequencies that the NIC can operate
     with. Each element in this list is formatted as a 
     <a href="..\windot11\ns-windot11-_dot11_supported_ofdm_frequency.md">
     DOT11_SUPPORTED_OFDM_FREQUENCY</a> structure.


## -remarks



A miniport driver returns the DOT11_SUPPORTED_OFDM_FREQUENCY_LIST structure when queried by 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-supported-ofdm-frequency-list">
    OID_DOT11_SUPPORTED_OFDM_FREQUENCY_LIST</a>.




## -see-also

<a href="..\windot11\ns-windot11-_dot11_supported_ofdm_frequency.md">
   DOT11_SUPPORTED_OFDM_FREQUENCY</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-supported-ofdm-frequency-list">
   OID_DOT11_SUPPORTED_OFDM_FREQUENCY_LIST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_SUPPORTED_OFDM_FREQUENCY_LIST structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

