---
UID: NC:wlanihv.DOT11EXTIHV_PERFORM_CAPABILITY_MATCH
title: DOT11EXTIHV_PERFORM_CAPABILITY_MATCH (wlanihv.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvperformcapabilitymatch.htm
tech.root: netvista
ms.assetid: c49b23c0-4707-4626-8035-a83ccf7638eb
ms.date: 02/16/2018
keywords: ["DOT11EXTIHV_PERFORM_CAPABILITY_MATCH callback"]
ms.keywords: DOT11EXTIHV_PERFORM_CAPABILITY_MATCH, Dot11ExtIhvPerformCapabilityMatch, Dot11ExtIhvPerformCapabilityMatch callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_98cf7a9a-aaf4-45d0-8b1d-3142e947e415.xml, netvista.dot11extihvperformcapabilitymatch, wlanihv/Dot11ExtIhvPerformCapabilityMatch
f1_keywords:
 - "wlanihv/Dot11ExtIhvPerformCapabilityMatch"
 - "Dot11ExtIhvPerformCapabilityMatch"
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
- Dot11ExtIhvPerformCapabilityMatch
product:
- Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXTIHV_PERFORM_CAPABILITY_MATCH callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div>

The operating system calls the
  <i>Dot11ExtIhvPerformCapabilityMatch</i> function to request that the IHV Extensions DLL determine whether a
  detected basic service set (BSS) network matches the connectivity and security profile extensions defined
  by the IHV.


## -prototype


```cpp
DOT11EXTIHV_PERFORM_CAPABILITY_MATCH Dot11ExtIhvPerformCapabilityMatch;

DWORD APIENTRY Dot11ExtIhvPerformCapabilityMatch(
  _In_opt_ HANDLE                             hIhvExtAdapter,
  _In_opt_ PDOT11EXT_IHV_PROFILE_PARAMS       pIhvProfileParams,
  _In_     PDOT11EXT_IHV_CONNECTIVITY_PROFILE pIhvConnProfile,
  _In_     PDOT11EXT_IHV_SECURITY_PROFILE     pIhvSecProfile,
  _In_opt_ PDOT11_BSS_LIST                    pConnectableBssid,
  _Out_    PDWORD                             pdwReasonCode
)
{ ... }
```


## -parameters




### -param hIhvExtAdapter [in, optional]

The handle used by the IHV Extensions DLL to reference the wireless LAN (WLAN) adapter. This
     handle value was specified through a previous call to the
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


### -param pIhvProfileParams [in, optional]

A pointer to a
     <a href="..\wlanihvtypes\ns-wlanihvtypes-_dot11ext_ihv_profile_params.md">
     DOT11EXT_IHV_PROFILE_PARAMS</a> structure. This structure defines the attributes of the basic service
     set (BSS) network to which the profile extensions will be applied.


### -param pIhvConnProfile [in]

A pointer to a
     <a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_connectivity_profile.md">
     DOT11EXT_IHV_CONNECTIVITY_PROFILE</a> structure that contains connectivity settings for the IHV
     profile.


### -param pIhvSecProfile [in]

A pointer to a
     <a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_security_profile.md">
     DOT11EXT_IHV_SECURITY_PROFILE</a> structure that contains security settings for the IHV
     profile.


### -param pConnectableBssid [in, optional]

A pointer to a
     <a href="..\wlclient\ns-wlclient-_dot11_bss_list.md">DOT11_BSS_LIST</a> structure, which contains one
     or more 802.11 Beacon or Probe Response frames received from a BSS network. This list is derived from
     the results of the last scan operation performed by the WLAN adapter. For more information about the
     scan operation, see
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/native-802-11-scan-operations">Native 802.11 Scan Operations</a>.


<div class="alert"><b>Note</b>  For Windows Vista, the IHV Extensions DLL supports only infrastructure basic
     service set (BSS) networks.</div>

### -param pdwReasonCode [out]

A pointer to a DWORD value, which provides additional information for the return value of the
     <i>Dot11ExtIhvPerformCapabilityMatch</i> function. The IHV Extensions DLL must set *
     <i>pdwReasonCode</i> to an L2_REASON_CODE_xxxx value, which are defined in
     L2cmn.h.


## -returns



If all of the entries in the list of 802.11 Beacon and Probe Response frames support the
     connectivity and security attributes defined in the profile fragments, the function returns
     ERROR_SUCCESS. Otherwise, it returns an error code defined in
     Winerror.h.




## -remarks



After the WLAN adapter has completed a scan operation to detect the BSS networks within range, the
    operating system might call the
    <i>Dot11ExtIhvPerformCapabilityMatch</i> function to determine whether any of the detected BSS networks
    matches the connectivity or security profile extensions defined by the IHV.

When the
    <i>Dot11ExtIhvPerformCapabilityMatch</i> function is called, the IHV Extensions DLL must follow these
    guidelines.

<ul>
<li>
If the IHV Extensions DLL finds at least one IEEE 802.11 Beacon or Probe Response frame that matches
      the profile fragments, it must set *
      <i>pdwReasonCode</i> to one of the following:

<ul>
<li>
L2_REASON_CODE_SUCCESS.

</li>
<li>
An IHV-defined value in the range from L2_REASON_CODE_IHV_BASE to (L2_REASON_CODE_IHV_BASE+
        L2_REASON_CODE_GROUP_SIZE-1).

</li>
</ul>
In this situation, the
      <i>Dot11ExtIhvPerformCapabilityMatch</i> function must return ERROR_SUCCESS.

</li>
<li>
If the IHV Extensions DLL does not find an IEEE 802.11 Beacon or Probe Response frame that matches
      the profile fragments, it must not set
      <i>*pdwReasonCode</i> to L2_REASON_CODE_SUCCESS. Instead, the DLL must set *
      <i>pdwReasonCode</i> to one of the following:

<ul>
<li>
An appropriate L2_REASON_CODE_xxxx error value.

</li>
<li>
An IHV-defined value in the range from L2_REASON_CODE_IHV_BASE to (L2_REASON_CODE_IHV_BASE+
        L2_REASON_CODE_GROUP_SIZE-1).

</li>
</ul>
In this situation, the
      <i>Dot11ExtIhvPerformCapabilityMatch</i> function must not return ERROR_SUCCESS.

</li>
</ul>
For more information about the Native 802.11 XML schema, refer to the Microsoft Windows SDK
    documentation.




## -see-also

<a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_connectivity_profile.md">
   DOT11EXT_IHV_CONNECTIVITY_PROFILE</a>



<a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_security_profile.md">DOT11EXT_IHV_SECURITY_PROFILE</a>



<a href="..\wlclient\ns-wlclient-_dot11_bss_list.md">DOT11_BSS_LIST</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



<a href="..\wlanihvtypes\ns-wlanihvtypes-_dot11ext_ihv_profile_params.md">DOT11EXT_IHV_PROFILE_PARAMS</a>



 

 


