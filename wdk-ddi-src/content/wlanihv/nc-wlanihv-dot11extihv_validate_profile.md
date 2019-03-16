---
UID: NC:wlanihv.DOT11EXTIHV_VALIDATE_PROFILE
title: DOT11EXTIHV_VALIDATE_PROFILE (wlanihv.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvvalidateprofile.htm
tech.root: netvista
ms.assetid: 724a6c17-e020-44e1-9d00-332daa5dbdfb
ms.date: 02/16/2018
ms.keywords: DOT11EXTIHV_VALIDATE_PROFILE, Dot11ExtIhvValidateProfile, Dot11ExtIhvValidateProfile callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_14df716f-4572-424e-8bee-a19b5b3d6e68.xml, netvista.dot11extihvvalidateprofile, wlanihv/Dot11ExtIhvValidateProfile
ms.topic: callback
req.header: wlanihv.h
req.include-header: Wlanihv.h, L2cmn.h
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
- Dot11ExtIhvValidateProfile
product:
- Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXTIHV_VALIDATE_PROFILE callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The operating system calls the
  <i>Dot11ExtIhvValidateProfile</i> function to validate user data entered for a network profile. The IHV
  Extensions DLL is only responsible for verifying the data for the fragments of the connectivity and
  security profile defined by the IHV.


## -prototype


```cpp
DOT11EXTIHV_VALIDATE_PROFILE Dot11ExtIhvValidateProfile;

DWORD APIENTRY Dot11ExtIhvValidateProfile(
  _In_opt_ HANDLE                             hIhvExtAdapter,
  _In_opt_ PDOT11EXT_IHV_PROFILE_PARAMS       pIhvProfileParams,
  _In_     PDOT11EXT_IHV_CONNECTIVITY_PROFILE pIhvConnProfile,
  _In_     PDOT11EXT_IHV_SECURITY_PROFILE     pIhvSecProfile,
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


### -param pdwReasonCode [out]

A pointer to a DWORD value, which provides additional information for the return value of the
     <i>Dot11ExtIhvValidateProfile</i> function. The IHV Extensions DLL must set *
     <i>pdwReasonCode</i> to an L2_REASON_CODE_xxxx value, which are defined in
     L2cmn.h.


## -returns



If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in
     Winerror.h.




## -remarks



The operating system calls the
    <i>Dot11ExtIhvValidateProfile</i> function to verify the user-specified settings for a network profile
    before the profile is processed or saved.

When the
    <i>Dot11ExtIhvValidateProfile</i> function is called, the IHV Extensions DLL follows these guidelines:

<ul>
<li>
The IHV Extensions DLL verifies that the user-specified profile settings are valid for the general
      attributes of the basic service set (BSS) network to which the profile will be applied. The BSS network
      attributes are referenced through the
      <i>pIhvProfileParams</i> parameter.

</li>
<li>
If the user data is valid for the network profile extensions,
      <i>Dot11ExtIhvValidateProfile</i> must return ERROR_SUCCESS. Otherwise, the function must return an
      appropriate error code from the ERROR_xxxx values defined in
      Winerror.h.

</li>
<li>
The IHV Extensions DLL provides more information regarding the results of the validation of the user
      data. The DLL must set *
      <i>pdwReasonCode</i> to one of the following:

<ul>
<li>
L2_REASON_CODE_SUCCESS, if the user data is valid.

</li>
<li>
An appropriate L2_REASON_CODE_xxxx error value, if the user data is not valid.

</li>
<li>
An IHV-defined value in the range from L2_REASON_CODE_IHV_BASE to (L2_REASON_CODE_IHV_BASE+
        L2_REASON_CODE_GROUP_SIZE-1), regardless of the validity of the user data.

</li>
</ul>
</li>
</ul>
For more information about the Native 802.11 XML schema, refer to the Microsoft Windows SDK
    documentation.




## -see-also

<a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_connectivity_profile.md">
   DOT11EXT_IHV_CONNECTIVITY_PROFILE</a>



<a href="..\wlanihvtypes\ns-wlanihvtypes-_dot11ext_ihv_profile_params.md">DOT11EXT_IHV_PROFILE_PARAMS</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



<a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_security_profile.md">DOT11EXT_IHV_SECURITY_PROFILE</a>



 

 


