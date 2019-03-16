---
UID: NC:wlanihv.DOT11EXTIHV_CREATE_DISCOVERY_PROFILES
title: DOT11EXTIHV_CREATE_DISCOVERY_PROFILES (wlanihv.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvcreatediscoveryprofiles.htm
tech.root: netvista
ms.assetid: e741bfa7-eb97-4f94-beb4-545d7bedcea8
ms.date: 02/16/2018
ms.keywords: DOT11EXTIHV_CREATE_DISCOVERY_PROFILES, Dot11ExtIhvCreateDiscoveryProfiles, Dot11ExtIhvCreateDiscoveryProfiles callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_fadde2b4-2a9d-4c6b-8a92-e044bab5c544.xml, netvista.dot11extihvcreatediscoveryprofiles, wlanihv/Dot11ExtIhvCreateDiscoveryProfiles
ms.topic: callback
req.header: wlanihv.h
req.include-header: Wlanihv.h, Winclient.h, L2cmn.h
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
- Dot11ExtIhvCreateDiscoveryProfiles
product:
- Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXTIHV_CREATE_DISCOVERY_PROFILES callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div>

The operating system calls the
  <i>Dot11ExtIhvCreateDiscoveryProfiles</i> function to return temporary connectivity and security profile
  fragments that could be used to connect to a basic service set (BSS) network for which a network profile
  does not exist.


## -prototype


```cpp
DOT11EXTIHV_CREATE_DISCOVERY_PROFILES Dot11ExtIhvCreateDiscoveryProfiles;

DWORD APIENTRY Dot11ExtIhvCreateDiscoveryProfiles(
  _In_opt_ HANDLE                               hIhvExtAdapter,
  _In_     BOOL                                 bInsecure,
  _In_opt_ PDOT11EXT_IHV_PROFILE_PARAMS         pIhvProfileParams,
  _In_opt_ PDOT11_BSS_LIST                      pConnectableBssid,
  _Out_    PDOT11EXT_IHV_DISCOVERY_PROFILE_LIST pIhvDiscoveryProfileList,
  _Out_    PDWORD                               pdwReasonCode
)
{ ... }
```


## -parameters




### -param hIhvExtAdapter [in, optional]

The handle used by the IHV Extensions DLL to reference the wireless LAN (WLAN) adapter. This
     handle value was specified through a previous call to the
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


### -param bInsecure [in]

A Boolean value that specifies the security status of the discovery profiles. If set to <b>TRUE</b>, the
     IHV Extensions DLL can only return secure profiles, such as profiles which involve user
     authentication.


### -param pIhvProfileParams [in, optional]

A pointer to a
     <a href="..\wlanihvtypes\ns-wlanihvtypes-_dot11ext_ihv_profile_params.md">
     DOT11EXT_IHV_PROFILE_PARAMS</a> structure. This structure defines the attributes of the basic service
     set (BSS) network to which the profile extensions will be applied.


### -param pConnectableBssid [in, optional]

A pointer to a
     <a href="..\wlclient\ns-wlclient-_dot11_bss_list.md">DOT11_BSS_LIST</a> structure, which contains one
     or more 802.11 Beacon or Probe Response frames received from a BSS network. This list is derived from
     the results of the last scan operation performed by the WLAN adapter. For more information about the
     scan operation, see
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/native-802-11-scan-operations">Native 802.11 Scan Operations</a>.


<div class="alert"><b>Note</b>  For Windows Vista, the IHV Extensions DLL supports only infrastructure basic
     service set (BSS) networks.</div>

### -param pIhvDiscoveryProfileList [out]

A pointer to a
     <a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_discovery_profile_list.md">
     DOT11EXT_IHV_DISCOVERY_PROFILE_LIST</a> structure that specifies a list of IHV discovery
     profiles.


### -param pdwReasonCode [out]

A pointer to a DWORD value, which provides additional information for the return value of the
     <i>Dot11ExtIhvCreateDiscoveryProfiles</i> function. The IHV Extensions DLL must set *
     <i>pdwReasonCode</i> to an L2_REASON_CODE_xxxx value, which are defined in
     L2cmn.h.


## -returns



If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in
     Winerror.h.




## -remarks



After the WLAN adapter completes a scan operation, the operating system might call
    <i>Dot11ExtIhvCreateDiscoveryProfiles</i> to create temporary profile fragments that could be used to
    connect to a BSS network for which a network profile has not been created by the user.

When
    <i>Dot11ExtIhvCreateDiscoveryProfiles</i> is called, the IHV Extensions DLL must follow these
    guidelines.

<ul>
<li>
If the IHV Extensions DLL can return profile fragments that can be used to connect to the BSS
      network, the
      <i>Dot11ExtIhvCreateDiscoveryProfiles</i> function must return ERROR_SUCCESS. Otherwise, the function
      must return an appropriate error code from the ERROR_xxxx values defined in
      Winerror.h.

</li>
<li>
The IHV Extensions DLL provides more information regarding the return result of the
      <i>Dot11ExtIhvCreateDiscoveryProfiles</i> function. The DLL must set *
      <i>pdwReasonCode</i> to one of the following:

<ul>
<li>
L2_REASON_CODE_SUCCESS, if profile fragments can be returned for the list of BSS networks.

</li>
<li>
An appropriate L2_REASON_CODE_xxxx error value, if the profile fragments cannot be returned for
        the list of BSS networks.

</li>
<li>
An IHV-defined value in the range from L2_REASON_CODE_IHV_BASE to (L2_REASON_CODE_IHV_BASE+
        L2_REASON_CODE_GROUP_SIZE-1), regardless of whether profile fragments are returned.

</li>
</ul>
</li>
</ul>
For more information about creating discovery profiles, see
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/creating-network-profile-extensions">Creating Network Profile
    Extensions</a>.




## -see-also

<a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_discovery_profile_list.md">
   DOT11EXT_IHV_DISCOVERY_PROFILE_LIST</a>



<a href="..\wlclient\ns-wlclient-_dot11_bss_list.md">DOT11_BSS_LIST</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_free_buffer.md">Dot11ExtFreeBuffer</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_allocate_buffer.md">Dot11ExtAllocateBuffer</a>



<a href="..\wlanihvtypes\ns-wlanihvtypes-_dot11ext_ihv_profile_params.md">DOT11EXT_IHV_PROFILE_PARAMS</a>



 

 


