---
UID: NC:wlanihv.DOT11EXT_SET_CURRENT_PROFILE
title: DOT11EXT_SET_CURRENT_PROFILE
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extsetcurrentprofile.htm
old-project: netvista
ms.assetid: 2fcf4f93-8d50-44e1-a657-d98b7b00bcfc
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DRIVER_INFO_8W, *LPDRIVER_INFO_8W, *PDRIVER_INFO_8W, DRIVER_INFO_8W, DRIVER_INFO_8
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wlanihv.h
req.include-header: Wlanihv.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: Dot11ExtSetCurrentProfile
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

# DOT11EXT_SET_CURRENT_PROFILE callback



## -description

## -prototype

````
DWORD WINAPI * Dot11ExtSetCurrentProfile(
  _In_opt_ HANDLE                             hDot11SvcHandle,
  _In_opt_ HANDLE                             hConnectSession,
  _In_opt_ PDOT11EXT_IHV_CONNECTIVITY_PROFILE pIhvConnProfile,
  _In_opt_ PDOT11EXT_IHV_SECURITY_PROFILE     pIhvSecProfile
);
````


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


### -param pIhvConnProfile [in, optional]

A pointer to a 
     <a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_connectivity_profile.md">
     DOT11EXT_IHV_CONNECTIVITY_PROFILE</a> structure that contains connectivity settings for the IHV
     profile.


### -param pIhvSecProfile [in, optional]

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
    <a href="https://msdn.microsoft.com/82f24545-75cb-4fbc-a98a-04dfac231c10">Native 802.11 IHV UI Extensions
    DLL</a>.

The IHV Extensions DLL must follow these guidelines when calling the 
    <b>Dot11ExtSetCurrentProfile</b> function:

The IHV Extensions DLL must only call 
      <b>Dot11ExtSetCurrentProfile</b> when performing a pre-association operation
      initiated through a call to the 
      <a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_pre_associate.md">
      Dot11ExtIhvPerformPreAssociate</a> IHV Handler function. For more information about the
      pre-association operation, see 
      <a href="netvista.pre_association_operations">Pre-Association Operation</a>.

The IHV Extensions DLL must not call 
      <b>Dot11ExtSetCurrentProfile</b> from within the call to the 
      <a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_pre_associate.md">
      Dot11ExtIhvPerformPreAssociate</a> IHV Handler function. 
      <b>Dot11ExtSetCurrentProfile</b> must be called from a different thread than
      the one which is processing the call to 
      <i>Dot11ExtIhvPerformPreAssociate</i>.


## -see-also
<dl>
<dt>
<a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_connectivity_profile.md">
   DOT11EXT_IHV_CONNECTIVITY_PROFILE</a>
</dt>
<dt>
<a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_security_profile.md">DOT11EXT_IHV_SECURITY_PROFILE</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_pre_associate.md">
   Dot11ExtIhvPerformPreAssociate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_SET_CURRENT_PROFILE callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

