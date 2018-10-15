---
UID: NC:wlanihv.DOT11EXTIHV_DEINIT_ADAPTER
title: DOT11EXTIHV_DEINIT_ADAPTER
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvdeinitadapter.htm
tech.root: netvista
ms.assetid: bf2e7ed3-cefc-47f3-a21b-aea3f0e569fe
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: DOT11EXTIHV_DEINIT_ADAPTER, Dot11ExtIhvDeinitAdapter, Dot11ExtIhvDeinitAdapter callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_5816e619-b6ca-4515-8bf6-99d053c108b0.xml, netvista.dot11extihvdeinitadapter, wlanihv/Dot11ExtIhvDeinitAdapter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wlanihv.h
req.include-header: Wlanihv.h
req.target-type: Desktop
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
-	UserDefined
api_location:
-	wlanihv.h
api_name:
-	Dot11ExtIhvDeinitAdapter
product:
- Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXTIHV_DEINIT_ADAPTER callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The operating system calls the
  <i>Dot11ExtIhvDeinitAdapter</i> function to have the IHV Extensions DLL halt all operations for the wireless
  LAN (WLAN) adapter, as well as free any resources allocated for the station.


## -prototype


```
DOT11EXTIHV_DEINIT_ADAPTER Dot11ExtIhvDeinitAdapter;

VOID APIENTRY Dot11ExtIhvDeinitAdapter(
  _In_opt_ HANDLE hIhvExtAdapter
)
{ ... }
```


## -parameters




### -param hIhvExtAdapter [in, optional]

The handle used by the IHV Extensions DLL to reference the WLAN adapter. This handle value was
     specified through a previous call to the
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


## -returns



None




## -remarks



The operating system calls the
    <i>Dot11ExtIhvDeinitAdapter</i> function whenever a WLAN adapter becomes unavailable and is disabled for
    use, such as when a PCMCIA adapter is removed.

The operating system also calls the
    <i>Dot11ExtIhvDeinitAdapter</i> function for every adapter managed by the IHV Extensions DLL before the
    operating system unloads the DLL. In this situation, the operating system calls the
    <a href="..\wlanihv\nc-wlanihv-dot11extihv_deinit_service.md">Dot11ExtIhvDeinitService</a> IHV
    Handler function after the last WLAN adapter has been halted through a call to the
    <i>Dot11ExtIhvDeinitAdapter</i> function.

For more information about operations that are performed when the WLAN adapter is removed, see
    <a href="https://msdn.microsoft.com/2181d284-7987-48db-b7a4-d1296d8313ed">802.11 WLAN Adapter Removal</a>.




## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/native-802-11-ihv-extensibility-functions">Native 802.11 IHV
   Extensibility Functions</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_deinit_service.md">Dot11ExtIhvDeinitService</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



 

 


