---
UID: NS:wlclient._DOT11_ADAPTER
title: "_DOT11_ADAPTER"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_adapter.htm
tech.root: netvista
ms.assetid: dae4c499-86c7-4f2b-bd5a-df2a62cdb77f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PDOT11_ADAPTER, DOT11_ADAPTER, DOT11_ADAPTER structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_0575eb35-d3de-41ad-a956-1714e642b8b5.xml, PDOT11_ADAPTER, PDOT11_ADAPTER structure pointer [Network Drivers Starting with Windows Vista], _DOT11_ADAPTER, netvista.dot11_adapter, wlclient/DOT11_ADAPTER, wlclient/PDOT11_ADAPTER"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wlclient.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wlclient.h
api_name:
-	DOT11_ADAPTER
product:
- Windows
targetos: Windows
req.typenames: DOT11_ADAPTER, *PDOT11_ADAPTER
req.product: Windows 10 or later.
---

# _DOT11_ADAPTER structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_ADAPTER structure identifies a wireless LAN (WLAN) adapter, as well as the operating
  attributes of the instance of the Native 802.11 miniport driver that manages the adapter.


## -syntax


```cpp
typedef struct _DOT11_ADAPTER {
  GUID                         gAdapterId;
  LPWSTR                       pszDescription;
  DOT11_CURRENT_OPERATION_MODE Dot11CurrentOpMode;
} DOT11_ADAPTER, *PDOT11_ADAPTER;
```


## -struct-fields




### -field gAdapterId

The globally unique identifier (GUID) of the WLAN adapter.


### -field pszDescription

A description of the WLAN adapter.


### -field Dot11CurrentOpMode

The current Native 802.11 operation mode of the miniport driver instance that manages the WLAN
     adapter. The value of
     <b>Dot11CurrentOpMode</b> is formatted as a
     <a href="..\windot11\ns-windot11-_dot11_current_operation_mode.md">
     DOT11_CURRENT_OPERATION_MODE</a> value.


## -remarks



The operating system calls the
    <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
    handler function whenever a WLAN adapter becomes available and enabled for use, such as when a PCMCIA
    adapter is inserted. The operating system defines the WLAN adapter by passing in the DOT11_ADAPTER
    structure through the
    <i>pDot11Adapter</i> parameter of the
    <i>Dot11ExtIhvInitAdapter</i> function.




## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/native-802-11-ihv-handler-functions">Native 802.11 IHV Handler
   Functions</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



<a href="..\windot11\ns-windot11-_dot11_current_operation_mode.md">DOT11_CURRENT_OPERATION_MODE</a>



 

 


