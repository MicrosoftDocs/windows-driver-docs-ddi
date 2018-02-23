---
UID: NC:wlanihv.DOT11EXT_GET_PROFILE_CUSTOM_USER_DATA
title: DOT11EXT_GET_PROFILE_CUSTOM_USER_DATA
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extgetprofilecustomuserdata.htm
old-project: netvista
ms.assetid: 1a88138f-aada-410a-a985-249de793aa51
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.dot11extgetprofilecustomuserdata, Dot11ExtGetProfileCustomUserData callback function [Network Drivers Starting with Windows Vista], Dot11ExtGetProfileCustomUserData, DOT11EXT_GET_PROFILE_CUSTOM_USER_DATA, DOT11EXT_GET_PROFILE_CUSTOM_USER_DATA, wlanihv/Dot11ExtGetProfileCustomUserData, Native_802.11_IHV_Ext_ee7fad1d-d3c2-400d-bf87-b2bdccd61f58.xml
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
-	Dot11ExtGetProfileCustomUserData
product: Windows
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


````
DWORD WINAPI * Dot11ExtGetProfileCustomUserData(
  _In_opt_ HANDLE hDot11SvcHandle,
  _In_opt_ HANDLE hConnectSession,
  _In_     DWORD  dwSessionID,
  _Out_    DWORD  *pdwDataSize,
  _Out_    LPVOID *ppvData
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

<a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_pre_associate.md">
   Dot11ExtIhvPerformPreAssociate</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_set_profile_custom_user_data.md">
   Dot11ExtSetProfileCustomUserData</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_set_current_profile.md">Dot11ExtSetCurrentProfile</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_free_buffer.md">Dot11ExtFreeBuffer</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_GET_PROFILE_CUSTOM_USER_DATA callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

