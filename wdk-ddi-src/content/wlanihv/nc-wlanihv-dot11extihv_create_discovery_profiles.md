---
UID: NC:wlanihv.DOT11EXTIHV_CREATE_DISCOVERY_PROFILES
title: DOT11EXTIHV_CREATE_DISCOVERY_PROFILES
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvcreatediscoveryprofiles.htm
old-project: netvista
ms.assetid: e741bfa7-eb97-4f94-beb4-545d7bedcea8
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DRIVER_INFO_8W, *LPDRIVER_INFO_8W, *PDRIVER_INFO_8W, DRIVER_INFO_8W, DRIVER_INFO_8
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wlanihv.h
req.include-header: Wlanihv.h, Winclient.h, L2cmn.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: Dot11ExtIhvCreateDiscoveryProfiles
req.alt-loc: wlanihv.h
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
req.typenames: *LPDRIVER_INFO_8W, *PDRIVER_INFO_8W, DRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXTIHV_CREATE_DISCOVERY_PROFILES callback



## -description

## -prototype

````
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
````


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
     <a href="https://msdn.microsoft.com/f670ea71-be96-44f1-b827-a026e91640bd">Native 802.11 Scan Operations</a>.
     

<div class="alert"><b>Note</b>  For Windows Vista, the IHV Extensions DLL supports only infrastructure basic
     service set (BSS) networks.</div>
<div> </div>

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

If the IHV Extensions DLL can return profile fragments that can be used to connect to the BSS
      network, the 
      <i>Dot11ExtIhvCreateDiscoveryProfiles</i> function must return ERROR_SUCCESS. Otherwise, the function
      must return an appropriate error code from the ERROR_xxxx values defined in 
      Winerror.h.

The IHV Extensions DLL provides more information regarding the return result of the 
      <i>Dot11ExtIhvCreateDiscoveryProfiles</i> function. The DLL must set *
      <i>pdwReasonCode</i> to one of the following:

L2_REASON_CODE_SUCCESS, if profile fragments can be returned for the list of BSS networks.

An appropriate L2_REASON_CODE_xxxx error value, if the profile fragments cannot be returned for
        the list of BSS networks.

An IHV-defined value in the range from L2_REASON_CODE_IHV_BASE to (L2_REASON_CODE_IHV_BASE+
        L2_REASON_CODE_GROUP_SIZE-1), regardless of whether profile fragments are returned.

For more information about creating discovery profiles, see 
    <a href="netvista.creating_network_profile_extensions">Creating Network Profile
    Extensions</a>.


## -see-also
<dl>
<dt>
<a href="..\wlclient\ns-wlclient-_dot11_bss_list.md">DOT11_BSS_LIST</a>
</dt>
<dt>
<a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_discovery_profile_list.md">
   DOT11EXT_IHV_DISCOVERY_PROFILE_LIST</a>
</dt>
<dt>
<a href="..\wlanihvtypes\ns-wlanihvtypes-_dot11ext_ihv_profile_params.md">DOT11EXT_IHV_PROFILE_PARAMS</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11ext_allocate_buffer.md">Dot11ExtAllocateBuffer</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11ext_free_buffer.md">Dot11ExtFreeBuffer</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXTIHV_CREATE_DISCOVERY_PROFILES callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

