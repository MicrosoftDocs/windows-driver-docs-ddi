---
UID: NC:wlanihv.DOT11EXT_SET_CURRENT_PROFILE
title: DOT11EXT_SET_CURRENT_PROFILE (wlanihv.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extsetcurrentprofile.htm
tech.root: netvista
ms.assetid: 2fcf4f93-8d50-44e1-a657-d98b7b00bcfc
ms.date: 02/16/2018
keywords: ["DOT11EXT_SET_CURRENT_PROFILE callback"]
ms.keywords: DOT11EXT_SET_CURRENT_PROFILE, Dot11ExtSetCurrentProfile, Dot11ExtSetCurrentProfile callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_0a4afb35-a806-47f0-8f52-76c88ba5ffac.xml, netvista.dot11extsetcurrentprofile, wlanihv/Dot11ExtSetCurrentProfile
f1_keywords:
 - "wlanihv/Dot11ExtSetCurrentProfile"
 - "Dot11ExtSetCurrentProfile"
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
- Dot11ExtSetCurrentProfile
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXT_SET_CURRENT_PROFILE callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The IHV Extensions DLL calls the
  <b>Dot11ExtSetCurrentProfile</b> function to specify the settings for the
  IHV-defined connectivity and security profile fragments. These fragments will be applied to the current
  network profile.


## -prototype


```cpp
DWORD WINAPI * Dot11ExtSetCurrentProfile(
  _In_opt_ HANDLE                             hDot11SvcHandle,
  _In_opt_ HANDLE                             hConnectSession,
  _In_opt_ PDOT11EXT_IHV_CONNECTIVITY_PROFILE pIhvConnProfile,
  _In_opt_ PDOT11EXT_IHV_SECURITY_PROFILE     pIhvSecProfile
);
```


## -parameters




### -param hDot11SvcHandle 
[in, optional]
The handle used by the operating system to reference the wireless LAN (WLAN) adapter. This handle
     value was specified through a previous call to the
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


### -param hConnectSession 
[in, optional]
The handle used by the operating system to reference the connection session with the basic service
     set (BSS) network. This handle value was specified through a previous call to the
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_pre_associate.md">
     Dot11ExtIhvPerformPreAssociate</a> IHV Handler function.


### -param pIhvConnProfile 
[in, optional]
A pointer to a
     <a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_connectivity_profile.md">
     DOT11EXT_IHV_CONNECTIVITY_PROFILE</a> structure that contains connectivity settings for the IHV
     profile.


### -param pIhvSecProfile 
[in, optional]
A pointer to a
     <a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_security_profile.md">
     DOT11EXT_IHV_SECURITY_PROFILE</a> structure that specifies security settings for the IHV
     profile.


## -returns



If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in
     Winerror.h.




## -remarks



The
    <b>Dot11ExtSetCurrentProfile</b> function allows the IHV to add custom
    connectivity and security profile fragments to the current network profile used for the basic service set
    (BSS) network connection. The profile fragments are IHV-specific and are applicable to connectivity or
    security extensions available to the user through the
    <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560635(v=vs.85)">Native 802.11 IHV UI Extensions
    DLL</a>.

The IHV Extensions DLL must follow these guidelines when calling the
    <b>Dot11ExtSetCurrentProfile</b> function:

<ul>
<li>
The IHV Extensions DLL must only call
      <b>Dot11ExtSetCurrentProfile</b> when performing a pre-association operation
      initiated through a call to the
      <a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_pre_associate.md">
      Dot11ExtIhvPerformPreAssociate</a> IHV Handler function. For more information about the
      pre-association operation, see
      <a href="https://docs.microsoft.com/windows-hardware/drivers/network/pre-association-operation-overview">Pre-Association Operation</a>.

</li>
<li>
The IHV Extensions DLL must not call
      <b>Dot11ExtSetCurrentProfile</b> from within the call to the
      <a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_pre_associate.md">
      Dot11ExtIhvPerformPreAssociate</a> IHV Handler function.
      <b>Dot11ExtSetCurrentProfile</b> must be called from a different thread than
      the one which is processing the call to
      <i>Dot11ExtIhvPerformPreAssociate</i>.

</li>
</ul>



## -see-also

<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



<a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_security_profile.md">DOT11EXT_IHV_SECURITY_PROFILE</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_pre_associate.md">
   Dot11ExtIhvPerformPreAssociate</a>



<a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_connectivity_profile.md">
   DOT11EXT_IHV_CONNECTIVITY_PROFILE</a>



 

 


