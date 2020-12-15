---
UID: NC:wlanihv.DOT11EXTIHV_INIT_SERVICE
title: DOT11EXTIHV_INIT_SERVICE (wlanihv.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvinitservice.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11EXTIHV_INIT_SERVICE callback"]
ms.keywords: DOT11EXTIHV_INIT_SERVICE, Dot11ExtIhvInitService, Dot11ExtIhvInitService callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_8e49584c-f0e7-4ff5-a3cb-5eafde2ff081.xml, netvista.dot11extihvinitservice, wlanihv/Dot11ExtIhvInitService
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
 - DOT11EXTIHV_INIT_SERVICE
 - wlanihv/DOT11EXTIHV_INIT_SERVICE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - wlanihv.h
api_name:
 - Dot11ExtIhvInitService
---

# DOT11EXTIHV_INIT_SERVICE callback


## -description

<div class="alert"><b>Important</b>  The <a href="/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The operating system calls the
  <i>Dot11ExtIhvInitService</i> function to initialize the IHV Extensions DLL as well as the API interface
  between the operating system and the DLL.

## -parameters

### -param dwVerNumUsed 

[in]
The interface version used by the operating system. The value of this parameter must be between
     the ranges of version numbers returned in the
     <i>pDot11IHVVersionInfo</i> parameter of the
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_get_version_info.md">
     Dot11ExtIhvGetVersionInfo</a> IHV Handler function.

### -param pDot11ExtAPI 

[in]
A pointer to a
     <a href="..\wlanihv\ns-wlanihv-_dot11ext_apis.md">DOT11EXT_APIS</a> structure, which contains the
     addresses of the IHV Extensibility functions that are supported by the operating system. The operating
     system formats this parameter with the function addresses before making the call to the
     <i>Dot11ExtIhvInitService</i> function.

### -param pvReserved

This parameter is reserved for use by the operating system.

### -param pDot11IHVHandlers 

[out]
A pointer to a
     <a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_handlers.md">DOT11EXT_IHV_HANDLERS</a> structure,
     which contains the addresses of the IHV Handler functions supported by the IHV Extensions DLL. The DLL
     formats this parameter with the function addresses before returning from the call to the
     <i>Dot11ExtIhvInitService</i> function.

## -returns

If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in
     Winerror.h.

## -prototype

```cpp
DOT11EXTIHV_INIT_SERVICE Dot11ExtIhvInitService;

DWORD APIENTRY Dot11ExtIhvInitService(
  _In_       DWORD                  dwVerNumUsed,
  _In_       PDOT11EXT_APIS         pDot11ExtAPI,
  _Reserved_ LPVOID                 pvReserved,
  _Out_      PDOT11EXT_IHV_HANDLERS pDot11IHVHandlers
)
{ ... }
```

## -remarks

The operating system calls the
    <i>Dot11ExtIhvInitService</i> function immediately after the call to the
    <a href="..\wlanihv\nc-wlanihv-dot11extihv_get_version_info.md">
    Dot11ExtIhvGetVersionInfo</a> function. When called,
    <i>Dot11ExtIhvInitService</i> must initialize the IHV Extensions DLL as necessary. When the function
    returns, the DLL must be prepared to accept additional calls to the IHV Handler function.

Unlike how it treats other IHV Extension and Handler functions whose addresses are resolved through
    the
    <i>pDot11IHVHandlers</i> parameter, the operating system resolves the address of the
    <i>Dot11ExtIhvInitService</i> function by calling the
    <b>GetProcAddress</b> function. As a result, the developer of the IHV Extensions DLL must follow these
    guidelines.

<ul>
<li>
The DLL must implement a function named Dot11ExtIhvInitService, which has the format that is
      described in this topic.

</li>
<li>
The
      <b>EXPORTS</b> statement of the source module-definition (.def) file, which is used to build the IHV
      Extensions DLL, must contain a function name entry for the
      <i>Dot11ExtIhvInitService</i> function.

</li>
</ul>
For more information about
    <b>GetProcAddress</b>, refer to the Microsoft Windows SDK documentation.

## -see-also

<a href="..\wlanihv\ns-wlanihv-_dot11ext_apis.md">DOT11EXT_APIS</a>



<a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_handlers.md">DOT11EXT_IHV_HANDLERS</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_get_version_info.md">Dot11ExtIhvGetVersionInfo</a>
