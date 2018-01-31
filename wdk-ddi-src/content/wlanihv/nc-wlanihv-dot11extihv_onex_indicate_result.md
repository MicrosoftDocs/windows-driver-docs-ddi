---
UID: NC:wlanihv.DOT11EXTIHV_ONEX_INDICATE_RESULT
title: DOT11EXTIHV_ONEX_INDICATE_RESULT
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvonexindicateresult.htm
old-project: netvista
ms.assetid: bf865b33-6e44-4724-868d-73150cf5b589
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.dot11extihvonexindicateresult, Dot11ExtIhvOneXIndicateResult callback function [Network Drivers Starting with Windows Vista], Dot11ExtIhvOneXIndicateResult, DOT11EXTIHV_ONEX_INDICATE_RESULT, DOT11EXTIHV_ONEX_INDICATE_RESULT, wlanihv/Dot11ExtIhvOneXIndicateResult, Native_802.11_IHV_Ext_af60ece5-6f3a-4a5b-9207-0e3cf68a012b.xml
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
-	Dot11ExtIhvOneXIndicateResult
product: Windows
targetos: Windows
req.typenames: "*PDRIVER_INFO_8W, DRIVER_INFO_8W, *LPDRIVER_INFO_8W"
req.product: Windows 10 or later.
---

# DOT11EXTIHV_ONEX_INDICATE_RESULT callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The operating system calls the 
  <i>Dot11ExtIhvOneXIndicateResult</i> IHV Handler function when it completes an 802.1X authentication
  operation with the access point (AP).


## -prototype


````
DOT11EXTIHV_ONEX_INDICATE_RESULT Dot11ExtIhvOneXIndicateResult;

DWORD APIENTRY Dot11ExtIhvOneXIndicateResult(
  _In_opt_ HANDLE                      hIhvExtAdapter,
  _In_     DOT11_MSONEX_RESULT         msOneXResult,
  _In_opt_ PDOT11_MSONEX_RESULT_PARAMS pDot11MsOneXResultParams
)
{ ... }
````


## -parameters




#### - hIhvExtAdapter [in, optional]

The handle used by the IHV Extensions DLL to reference the wireless LAN (WLAN) adapter. This
     handle value was specified through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


#### - msOneXResult [in]

The result of the 802.1X authentication operation specified through a 
     <a href="..\wlanihv\ne-wlanihv-_dot11_msonex_result.md">DOT11_MSONEX_RESULT</a> enumeration
     value.


#### - pDot11MsOneXResultParams [in, optional]

A pointer to a 
     <mshelp:link keywords="netvista.dot11_msonex_result_params" tabindex="0"><b>
     DOT11_MSONEX_RESULT_PARAMS</b></mshelp:link> structure that contains result parameters.


## -returns


If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in 
     Winerror.h.



## -remarks


The IHV Extensions DLL can initiate an 802.1X authentication operation by using the 802.1X module of
    the Native 802.11 framework. This allows the DLL to make use of the standard extensible authentication
    protocol (EAP) algorithms that are supported by the operating system.

The IHV Extensions DLL initiates the 802.1X authentication operation by calling the 
    <a href="..\wlanihv\nc-wlanihv-dot11ext_onex_start.md">Dot11ExtStartOneX</a> function. 
    <b>Dot11ExtStartOneX</b> can only be called either during a post-association operation or after the
    operation has completed. For more information about this operation, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/post-association-operations">Post-Association Operations</a>.

After the operating system has completed the 802.1X authentication operation, it calls the 
    <i>
    Dot11ExtIhvOneXIndicateResult</i> IHV Handler function.

For more information about using the 802.1X module for authentication, see 
    <mshelp:link keywords="netvista.interface_to_the_native_802_11_802_1x_module" tabindex="0">Interface to the Native
    802.11 802.1X Module</mshelp:link>




## -see-also

<a href="..\wlanihv\ns-wlanihv-_dot11_msonex_result_params.md">DOT11_MSONEX_RESULT_PARAMS</a>

<a href="..\wlanihv\ne-wlanihv-_dot11_msonex_result.md">DOT11_MSONEX_RESULT</a>

<a href="..\wlanihv\nc-wlanihv-dot11ext_onex_start.md">Dot11ExtStartOneX</a>

<a href="..\wlanihv\nc-wlanihv-dot11extihv_receive_packet.md">Dot11ExtIhvReceivePacket</a>

<mshelp:link keywords="netvista.dot11extihvonexindicateresult" tabindex="0"><i>
   Dot11ExtIhvOneXIndicateResult</i></mshelp:link>

<a href="..\wlanihv\nc-wlanihv-dot11ext_process_onex_packet.md">Dot11ExtProcessOneXPacket</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXTIHV_ONEX_INDICATE_RESULT callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

