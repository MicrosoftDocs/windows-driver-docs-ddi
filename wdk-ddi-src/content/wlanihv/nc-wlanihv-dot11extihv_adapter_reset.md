---
UID: NC:wlanihv.DOT11EXTIHV_ADAPTER_RESET
title: DOT11EXTIHV_ADAPTER_RESET (wlanihv.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvadapterreset.htm
tech.root: netvista
ms.assetid: c1e8cce7-6fa4-45d3-a8c8-9f2ef0a8e846
ms.date: 02/16/2018
ms.keywords: DOT11EXTIHV_ADAPTER_RESET, Dot11ExtIhvAdapterReset, Dot11ExtIhvAdapterReset callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_1749484b-7d42-42c0-bae2-5de47406f26b.xml, netvista.dot11extihvadapterreset, wlanihv/Dot11ExtIhvAdapterReset
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- wlanihv.h
api_name:
- Dot11ExtIhvAdapterReset
product:
- Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXTIHV_ADAPTER_RESET callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The operating system calls the IHV Extensions DLL
  <i>Dot11ExtIhvAdapterReset</i> function to reset the wireless LAN (WLAN) adapter.


## -prototype


```cpp
DOT11EXTIHV_ADAPTER_RESET Dot11ExtIhvAdapterReset;

DWORD APIENTRY Dot11ExtIhvAdapterReset(
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



If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in
     Winerror.h.




## -remarks



The operating system calls
    <i>Dot11ExtIhvAdapterReset</i> whenever one of the following events occurs.

<ul>
<li>
The WLAN adapter performs a disconnection operation. For more information about this operation, see
      <a href="https://docs.microsoft.com/windows-hardware/drivers/network/disconnection-operations">Disconnection Operations</a>.

</li>
<li>
The operating system resets the Native 802.11 miniport driver, which manages the adapter, through a
      set request of
      <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-reset-request">OID_DOT11_RESET_REQUEST</a>.

</li>
</ul>
The
    <i>Dot11ExtIhvAdapterReset</i> function must restore the WLAN adapter to the same state as when the DLL's
    <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> function
    was called.

For more information about the reset operation for WLAN adapters, see
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/802-11-wlan-adapter-reset">802.11 WLAN Adapter Reset</a>.




## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-reset-request">OID_DOT11_RESET_REQUEST</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



 

 


