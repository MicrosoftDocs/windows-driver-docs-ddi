---
UID: NC:wlanihv.DOT11EXT_SET_PROFILE_CUSTOM_USER_DATA
title: DOT11EXT_SET_PROFILE_CUSTOM_USER_DATA (wlanihv.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extsetprofilecustomuserdata.htm
tech.root: netvista
ms.assetid: 25e1462c-6eaa-480a-9f9e-6f8689da05c5
ms.date: 02/16/2018
keywords: ["DOT11EXT_SET_PROFILE_CUSTOM_USER_DATA callback"]
ms.keywords: DOT11EXT_SET_PROFILE_CUSTOM_USER_DATA, Dot11ExtSetProfileCustomUserData, Dot11ExtSetProfileCustomUserData callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_87f713b8-bd3e-4165-adce-c37fbb829cdb.xml, netvista.dot11extsetprofilecustomuserdata, wlanihv/Dot11ExtSetProfileCustomUserData
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
 - DOT11EXT_SET_PROFILE_CUSTOM_USER_DATA
 - wlanihv/DOT11EXT_SET_PROFILE_CUSTOM_USER_DATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - wlanihv.h
api_name:
 - Dot11ExtSetProfileCustomUserData
---

# DOT11EXT_SET_PROFILE_CUSTOM_USER_DATA callback


## -description

<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The IHV Extensions DLL calls the
  <b>Dot11ExtSetProfileCustomUserData</b> function to save data within the system
  registry that is specific to the current user and network profile used for the basic service set (BSS)
  network connection.

## -parameters

### -param hDot11SvcHandle 

[in, optional]
The handle used by the operating system to reference the wireless LAN (WLAN) adapter. This handle
     value was specified through a previous call to the
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.

### -param hConnectSession 

[in, optional]
The handle used by the operating system to reference the connection session with the BSS network.
     This handle value was specified through a previous call to the
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_pre_associate.md">
     Dot11ExtIhvPerformPreAssociate</a> IHV Handler function.

### -param dwSessionID 

[in]
The session identifier (session ID) of the current user.

### -param dwDataSize 

[in]
The size, in bytes, of the buffer referenced by
     <i>pvData</i> .

### -param pvData 

[in]
A pointer to a caller-allocated buffer, which contains the data in a format defined by the
     IHV.

## -returns

If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in
     Winerror.h.

## -prototype

```cpp
DWORD WINAPI * Dot11ExtSetProfileCustomUserData(
  _In_opt_ HANDLE hDot11SvcHandle,
  _In_opt_ HANDLE hConnectSession,
  _In_     DWORD  dwSessionID,
  _In_     DWORD  dwDataSize,
  _In_     LPVOID pvData
);
```

## -remarks

The operating system will not encrypt the data referenced by the
    <i>pvData</i> parameter before storing it within the system registry. The IHV Extensions DLL should use
    its own encryption algorithm to encrypt the data prior to calling
    <b>Dot11ExtSetProfileCustomUserData</b>.

For every wireless WLAN profile used by the Native Wifi AutoConfig service, Windows maintains the
    concept of custom user data. This custom user data is initially non-existent, but can be set by calling
    the
    <i>Dot11ExtSetProfileCustomUserData</i> function. The custom user data gets reset to empty any time the
    profile is modified by calling the
    <a href="..\wlanihv\nc-wlanihv-dot11ext_set_current_profile.md">
    Dot11ExtSetCurrentProfile</a> function.

After custom user data has been set, this data can be accessed using the
    <a href="..\wlanihv\nc-wlanihv-dot11ext_get_profile_custom_user_data.md">
    Dot11ExtGetProfileCustomUserData</a> function. The operating system stores the data under the system
    registry HKEY_CURRENT_USER key for the user that is referenced by the handle passed in the
    <i>dwSessionID</i> parameter.

## -see-also

<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_set_current_profile.md">Dot11ExtSetCurrentProfile</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_pre_associate.md">
   Dot11ExtIhvPerformPreAssociate</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_get_profile_custom_user_data.md">
   Dot11ExtGetProfileCustomUserData</a>

