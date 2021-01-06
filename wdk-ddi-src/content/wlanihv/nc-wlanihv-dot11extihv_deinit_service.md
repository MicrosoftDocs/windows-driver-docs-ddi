---
UID: NC:wlanihv.DOT11EXTIHV_DEINIT_SERVICE
title: DOT11EXTIHV_DEINIT_SERVICE (wlanihv.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvdeinitservice.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11EXTIHV_DEINIT_SERVICE callback"]
ms.keywords: DOT11EXTIHV_DEINIT_SERVICE, Dot11ExtIhvDeinitService, Dot11ExtIhvDeinitService callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_02e9e301-f950-47e3-9a1f-4212ae55387e.xml, netvista.dot11extihvdeinitservice, wlanihv/Dot11ExtIhvDeinitService
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
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
f1_keywords:
 - DOT11EXTIHV_DEINIT_SERVICE
 - wlanihv/DOT11EXTIHV_DEINIT_SERVICE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wlanihv.h
api_name:
 - Dot11ExtIhvDeinitService
---

# DOT11EXTIHV_DEINIT_SERVICE callback


## -description

<div class="alert"><b>Important</b>  The <a href="/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The operating system calls the
  <i>Dot11ExtIhvDeinitService</i> function to halt the IHV Extensions DLL.

## -parameters

## -prototype

```cpp
DOT11EXTIHV_DEINIT_SERVICE Dot11ExtIhvDeinitService;

VOID APIENTRY Dot11ExtIhvDeinitService(
   VOID
)
{ ... }
```

## -remarks

When the
    <i>Dot11ExtIhvDeinitService</i> function is called, the IHV Extensions DLL must be brought to a state that
    it can safely be unloaded by the operating system. The DLL must follow these guidelines when this
    function is called.

<ul>
<li>
The operating system calls the
      <a href="..\wlanihv\nc-wlanihv-dot11extihv_deinit_adapter.md">
      Dot11ExtIhvDeinitAdapter</a> function prior to calling the
      <i>Dot11ExtIhvDeinitService</i> function. As a result, the
      <i>Dot11ExtIhvDeinitService</i> function should not initiate any operations on the WLAN adapter.
      Instead,
      <i>Dot11ExtIhvDeinitService</i> should prepare the DLL to be unloaded by the operating system.

</li>
<li>
The DLL must terminate all executing threads that it created. The DLL must not return from the
      <i>Dot11ExtIhvDeinitService</i> function call until all threads have been terminated.

</li>
<li>
The DLL must free any allocated resources for the DLL itself. In particular, all memory the DLL
      allocated through calls to
      <a href="..\wlanihv\nc-wlanihv-dot11ext_allocate_buffer.md">Dot11ExtAllocateBuffer</a> must be
      freed through calls to
      <a href="..\wlanihv\nc-wlanihv-dot11ext_free_buffer.md">Dot11ExtFreeBuffer</a>.

</li>
</ul>

## -see-also

<a href="..\wlanihv\nc-wlanihv-dot11ext_allocate_buffer.md">Dot11ExtAllocateBuffer</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_deinit_adapter.md">Dot11ExtIhvDeinitAdapter</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_free_buffer.md">Dot11ExtFreeBuffer</a>
