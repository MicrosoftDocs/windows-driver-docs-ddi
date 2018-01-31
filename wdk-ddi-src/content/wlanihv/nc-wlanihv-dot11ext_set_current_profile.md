---
UID: NC:wlanihv.DOT11EXT_SET_CURRENT_PROFILE
title: DOT11EXT_SET_CURRENT_PROFILE
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extsetcurrentprofile.htm
old-project: netvista
ms.assetid: 2fcf4f93-8d50-44e1-a657-d98b7b00bcfc
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.dot11extsetcurrentprofile, Dot11ExtSetCurrentProfile callback function [Network Drivers Starting with Windows Vista], Dot11ExtSetCurrentProfile, DOT11EXT_SET_CURRENT_PROFILE, DOT11EXT_SET_CURRENT_PROFILE, wlanihv/Dot11ExtSetCurrentProfile, Native_802.11_IHV_Ext_0a4afb35-a806-47f0-8f52-76c88ba5ffac.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	wlanihv.h
apiname:
-	Dot11ExtSetCurrentProfile
product: Windows
targetos: Windows
req.typenames: "*PDRIVER_INFO_8W, DRIVER_INFO_8W, *LPDRIVER_INFO_8W"
req.product: Windows 10 or later.
---

# DOT11EXT_SET_CURRENT_PROFILE callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The IHV Extensions DLL calls the 
  <b>Dot11ExtSetCurrentProfile</b> function to specify the settings for the
  IHV-defined connectivity and security profile fragments. These fragments will be applied to the current
  network profile.


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




#### - hDot11SvcHandle [in, optional]

The handle used by the operating system to reference the wireless LAN (WLAN) adapter. This handle
     value was specified through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


#### - hConnectSession [in, optional]

The handle used by the operating system to reference the connection session with the basic service
     set (BSS) network. This handle value was specified through a previous call to the 
     <mshelp:link keywords="netvista.dot11extihvperformpreassociate" tabindex="0"><i>
     Dot11ExtIhvPerformPreAssociate</i></mshelp:link> IHV Handler function.


#### - pIhvConnProfile [in, optional]

A pointer to a 
     <mshelp:link keywords="netvista.dot11ext_ihv_connectivity_profile" tabindex="0"><b>
     DOT11EXT_IHV_CONNECTIVITY_PROFILE</b></mshelp:link> structure that contains connectivity settings for the IHV
     profile.


#### - pIhvSecProfile [in, optional]

A pointer to a 
     <mshelp:link keywords="netvista.dot11ext_ihv_security_profile" tabindex="0"><b>
     DOT11EXT_IHV_SECURITY_PROFILE</b></mshelp:link> structure that specifies security settings for the IHV
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
    <mshelp:link keywords="netvista.native_802_11_ihv_ui_extensions_dll" tabindex="0">Native 802.11 IHV UI Extensions
    DLL</mshelp:link>.

The IHV Extensions DLL must follow these guidelines when calling the 
    <b>Dot11ExtSetCurrentProfile</b> function:
<ul>
<li>
The IHV Extensions DLL must only call 
      <b>Dot11ExtSetCurrentProfile</b> when performing a pre-association operation
      initiated through a call to the 
      <mshelp:link keywords="netvista.dot11extihvperformpreassociate" tabindex="0"><i>
      Dot11ExtIhvPerformPreAssociate</i></mshelp:link> IHV Handler function. For more information about the
      pre-association operation, see 
      <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/pre-association-operation-overview">Pre-Association Operation</a>.

</li>
<li>
The IHV Extensions DLL must not call 
      <b>Dot11ExtSetCurrentProfile</b> from within the call to the 
      <mshelp:link keywords="netvista.dot11extihvperformpreassociate" tabindex="0"><i>
      Dot11ExtIhvPerformPreAssociate</i></mshelp:link> IHV Handler function. 
      <b>Dot11ExtSetCurrentProfile</b> must be called from a different thread than
      the one which is processing the call to 
      <i>Dot11ExtIhvPerformPreAssociate</i>.

</li>
</ul>


## -see-also

<mshelp:link keywords="netvista.dot11extihvperformpreassociate" tabindex="0"><i>
   Dot11ExtIhvPerformPreAssociate</i></mshelp:link>

<mshelp:link keywords="netvista.dot11ext_ihv_connectivity_profile" tabindex="0"><b>
   DOT11EXT_IHV_CONNECTIVITY_PROFILE</b></mshelp:link>

<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>

<a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_security_profile.md">DOT11EXT_IHV_SECURITY_PROFILE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_SET_CURRENT_PROFILE callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

