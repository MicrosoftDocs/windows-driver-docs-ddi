---
UID: NC:wlanihv.DOT11EXTIHV_GET_VERSION_INFO
title: DOT11EXTIHV_GET_VERSION_INFO (wlanihv.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvgetversioninfo.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11EXTIHV_GET_VERSION_INFO callback"]
ms.keywords: DOT11EXTIHV_GET_VERSION_INFO, Dot11ExtIhvGetVersionInfo, Dot11ExtIhvGetVersionInfo callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_1b6acc66-1f69-45c3-8596-3f0c96e21a91.xml, netvista.dot11extihvgetversioninfo, wlanihv/Dot11ExtIhvGetVersionInfo
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
 - DOT11EXTIHV_GET_VERSION_INFO
 - wlanihv/DOT11EXTIHV_GET_VERSION_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - wlanihv.h
api_name:
 - Dot11ExtIhvGetVersionInfo
---

# DOT11EXTIHV_GET_VERSION_INFO callback


## -description

<div class="alert"><b>Important</b>  The <a href="/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The operating system calls the
  <i>Dot11ExtIhvGetVersionInfo</i> function immediately after loading the IHV Extensions DLL to determine the
  version of the interface supported by the DLL.

## -parameters

### -param pDot11IHVVersionInfo 

[out]
A pointer to a
     <a href="..\wlanihv\ns-wlanihv-_dot11_ihv_version_info.md">DOT11_IHV_VERSION_INFO</a> structure,
     which contains the interface version numbers.

## -returns

If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in
     Winerror.h.

## -prototype

```cpp
DOT11EXTIHV_GET_VERSION_INFO Dot11ExtIhvGetVersionInfo;

DWORD APIENTRY Dot11ExtIhvGetVersionInfo(
  _Out_ PDOT11_IHV_VERSION_INFO pDot11IHVVersionInfo
)
{ ... }
```

## -remarks

The operating system calls the
    <i>Dot11ExtIhvGetVersionInfo</i> function to determine what version of the interface to use with the IHV
    Extension DLL. The operating system makes this call immediately after loading the DLL, and this call is
    the first that the operating system makes into the DLL.

Unlike other IHV Extensibility and Handler functions, whose addresses are resolved through a table of
    function pointers that are exchanged through a call to
    <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_service.md">Dot11ExtIhvInitService</a>, the
    address of the
    <i>Dot11ExtIhvGetVersionInfo</i> function is resolved by the operating system by the operating system
    calling the
    <b>GetProcAddress</b> function. As a result, the developer of the IHV Extensions DLL must follow these
    guidelines.

<ul>
<li>
The DLL must implement a function named Dot11ExtIhvGetVersionInfo, which has the format that is
      described in this topic.

</li>
<li>
The
      <b>EXPORTS</b> statement of the source module-definition (.def) file, which is used to build the IHV
      Extensions DLL, must contain a function name entry for the
      <i>Dot11ExtIhvGetVersionInfo</i> function.

</li>
</ul>
For more information about
    <b>GetProcAddress</b>, refer to the Microsoft Windows SDK documentation.

## -see-also

<a href="..\wlanihv\ns-wlanihv-_dot11_ihv_version_info.md">DOT11_IHV_VERSION_INFO</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_service.md">Dot11ExtIhvInitService</a>
