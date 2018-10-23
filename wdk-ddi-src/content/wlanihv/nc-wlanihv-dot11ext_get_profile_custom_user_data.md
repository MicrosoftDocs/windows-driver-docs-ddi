---
UID: NC:wlanihv.DOT11EXT_GET_PROFILE_CUSTOM_USER_DATA
title: DOT11EXT_GET_PROFILE_CUSTOM_USER_DATA
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extgetprofilecustomuserdata.htm
tech.root: netvista
ms.assetid: 1a88138f-aada-410a-a985-249de793aa51
ms.date: 02/16/2018
ms.keywords: DOT11EXT_GET_PROFILE_CUSTOM_USER_DATA, Dot11ExtGetProfileCustomUserData, Dot11ExtGetProfileCustomUserData callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_ee7fad1d-d3c2-400d-bf87-b2bdccd61f58.xml, netvista.dot11extgetprofilecustomuserdata, wlanihv/Dot11ExtGetProfileCustomUserData
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
-	Dot11ExtGetProfileCustomUserData
product:
- Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXT_GET_PROFILE_CUSTOM_USER_DATA callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The IHV Extensions DLL calls the
  <b>Dot11ExtGetProfileCustomUserData</b> function to retrieve data from the system
  registry specific to the current user and network profile used for the basic service set (BSS) network
  connection.


## -prototype


```cpp
DWORD WINAPI * Dot11ExtGetProfileCustomUserData(
  _In_opt_ HANDLE hDot11SvcHandle,
  _In_opt_ HANDLE hConnectSession,
  _In_     DWORD  dwSessionID,
  _Out_    DWORD  *pdwDataSize,
  _Out_    LPVOID *ppvData
);
```


## -parameters




### -param hDot11SvcHandle [in, optional]

The handle used by the operating system to reference the wireless LAN (WLAN) adapter. This handle
     value was specified through a previous call to the
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


### -param hConnectSession [in, optional]

The handle used by the operating system to reference the connection session with the basic service
     set (BSS) network. This handle value was specified through a previous call to the
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_pre_associate.md">
     Dot11ExtIhvPerformPreAssociate</a> IHV Handler function.


### -param dwSessionID [in]

The session identifier (session ID) of the current user.


### -param *pdwDataSize [out]

A pointer to a caller-supplied variable that stores the size, in bytes, of the buffer referenced
     by
     <i>ppvData</i> .


### -param *ppvData [out]

The address of a pointer variable that stores the address of the buffer containing the user
     data.


## -returns



If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in
     Winerror.h.




## -remarks



The operating system does not decrypt the data referenced by the
    <i>ppvData</i> parameter after reading it from the system registry. The IHV Extensions DLL should use its
    own decryption algorithm to decrypt the data after calling
    <b>Dot11ExtGetProfileCustomUserData</b>.

For every wireless WLAN profile used by the Native Wifi AutoConfig service, Windows maintains the
    concept of custom user data. This custom user data is initially non-existent, but can be set by calling
    the
    <a href="..\wlanihv\nc-wlanihv-dot11ext_set_profile_custom_user_data.md">
    Dot11ExtSetProfileCustomUserData</a> function. The custom user data gets reset to empty any time the
    profile is modified by calling the
    <a href="..\wlanihv\nc-wlanihv-dot11ext_set_current_profile.md">
    Dot11ExtSetCurrentProfile</a> function.

After custom user data has been set, this data can be accessed using the
    <b>Dot11ExtGetProfileCustomUserData</b> function.

The caller is responsible for freeing the memory allocated for the buffer pointed to by the
    <i>ppvData</i> parameter using the
    <a href="..\wlanihv\nc-wlanihv-dot11ext_free_buffer.md">Dot11ExtFreeBuffer</a> function.




## -see-also

<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_free_buffer.md">Dot11ExtFreeBuffer</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_set_profile_custom_user_data.md">
   Dot11ExtSetProfileCustomUserData</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_pre_associate.md">
   Dot11ExtIhvPerformPreAssociate</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_set_current_profile.md">Dot11ExtSetCurrentProfile</a>



 

 


