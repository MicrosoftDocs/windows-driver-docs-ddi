---
UID: NC:wlanihv.DOT11EXT_SET_AUTH_ALGORITHM
title: DOT11EXT_SET_AUTH_ALGORITHM
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extsetauthalgorithm.htm
old-project: netvista
ms.assetid: 49fbdd9d-4352-48b5-81bc-3092eef2e255
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.dot11extsetauthalgorithm, Dot11ExtSetAuthAlgorithm callback function [Network Drivers Starting with Windows Vista], Dot11ExtSetAuthAlgorithm, DOT11EXT_SET_AUTH_ALGORITHM, DOT11EXT_SET_AUTH_ALGORITHM, wlanihv/Dot11ExtSetAuthAlgorithm, Native_802.11_IHV_Ext_85806dab-a810-4b45-9c94-7b0b7e40a6a2.xml
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
-	Dot11ExtSetAuthAlgorithm
product: Windows
targetos: Windows
req.typenames: "*LPDRIVER_INFO_8W, DRIVER_INFO_8W, *PDRIVER_INFO_8W"
req.product: Windows 10 or later.
---

# DOT11EXT_SET_AUTH_ALGORITHM callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The IHV Extensions DLL calls the 
  <b>Dot11ExtSetAuthAlgorithm</b> function to enable an authentication algorithm on
  the wireless LAN (WLAN) adapter.


## -prototype


````
DWORD WINAPI * Dot11ExtSetAuthAlgorithm(
  _In_opt_ HANDLE hDot11SvcHandle,
  _In_     DWORD  dwAuthAlgo
);
````


## -parameters




### -param hDot11SvcHandle [in, optional]

The handle used by the operating system to reference the WLAN adapter. This handle value was
     specified through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


### -param dwAuthAlgo [in]

A 
     <a href="..\wlantypes\ne-wlantypes-_dot11_auth_algorithm.md">DOT11_AUTH_ALGORITHM</a> enumerator value
     that identifies the authentication algorithm. 
     

If the value is within the range of <b>DOT11_AUTH_ALGO_IHV_START</b> through DOT11_AUTH_ALGO_IHV_END, the
     IHV Extensions DLL enables a proprietary authentication algorithm supported by the WLAN adapter.

Otherwise, the DLL is responsible for the processing of a standard authentication algorithm supported
     by the operating system. In this situation, the operating system is not involved with the authentication
     processing over a basic service set (BSS) network connection through the WLAN adapter.


<div class="alert"><b>Note</b>  The value of 
      <i>dwAuthAlgo</i> must match the value of an authentication algorithm returned by the Native 802.11
      miniport driver through setting the appropriate <i>xxx</i><b>AlgoPairs</b> members of the  <a href="..\windot11\ns-windot11-dot11_extsta_attributes.md">DOT11_EXTSTA_ATTRIBUTES</a> structure, which must match the values that would be returned by queries of <a href="https://msdn.microsoft.com/en-us/library/gg157261.aspx">OID_DOT11_SUPPORTED_UNICAST_ALGORITHM_PAIR</a> or <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-supported-multicast-algorithm-pair">OID_DOT11_SUPPORTED_MULTICAST_ALGORITHM_PAIR</a>.</div>
<div> </div>



## -returns



If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in 
     Winerror.h.




## -see-also

<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



<a href="..\wlantypes\ne-wlantypes-_dot11_auth_algorithm.md">DOT11_AUTH_ALGORITHM</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_pre_associate_completion.md">
   Dot11ExtPreAssociateCompletion</a>



<a href="https://msdn.microsoft.com/en-us/library/gg157261.aspx">
   OID_DOT11_SUPPORTED_UNICAST_ALGORITHM_PAIR</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-supported-multicast-algorithm-pair">
   OID_DOT11_SUPPORTED_MULTICAST_ALGORITHM_PAIR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_SET_AUTH_ALGORITHM callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

