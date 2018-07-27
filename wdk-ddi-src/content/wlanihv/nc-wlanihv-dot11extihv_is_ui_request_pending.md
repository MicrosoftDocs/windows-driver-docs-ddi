---
UID: NC:wlanihv.DOT11EXTIHV_IS_UI_REQUEST_PENDING
title: DOT11EXTIHV_IS_UI_REQUEST_PENDING
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvisuirequestpending.htm
tech.root: netvista
ms.assetid: e8747dc5-7ef7-4914-baf7-683ddfe68313
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: DOT11EXTIHV_IS_UI_REQUEST_PENDING, Dot11ExtIhvIsUIRequestPending, Dot11ExtIhvIsUIRequestPending callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_88488999-ecad-4845-a4b3-051b96c506dd.xml, netvista.dot11extihvisuirequestpending, wlanihv/Dot11ExtIhvIsUIRequestPending
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	wlanihv.h
api_name:
-	Dot11ExtIhvIsUIRequestPending
product:
- Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXTIHV_IS_UI_REQUEST_PENDING callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The operating system calls the
  <i>Dot11ExtIhvIsUIRequestPending</i> function to query the status of a UI request initiated by the IHV
  Extensions DLL.


## -prototype


````
DOT11EXTIHV_IS_UI_REQUEST_PENDING Dot11ExtIhvIsUIRequestPending;

DWORD APIENTRY Dot11ExtIhvIsUIRequestPending(
  _In_  GUID  guidUIRequest,
  _Out_ PBOOL pbIsRequestPending
)
{ ... }
````


## -parameters




### -param guidUIRequest [in]

The GUID that identifies the request. This GUID value was created by the IHV Extensions DLL and
     passed through the
     <i>pIhvUIRequest</i> parameter of the call to
     <a href="..\wlanihv\nc-wlanihv-dot11ext_send_ui_request.md">Dot11ExtSendUIRequest</a>.


### -param pbIsRequestPending [out]

A pointer to a Boolean value. If the UI request, identified by the
     <i>guidUIRequest</i> parameter, is pending, the IHV Extensions DLL must set *
     <i>pbIsRequestPending</i> to <b>TRUE</b>.


## -returns



If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in
     Winerror.h.




## -remarks



The IHV Extensions DLL can issue requests to the IHV UI Extensions DLL to interact with the user.
    Examples of such requests are thedisplay of notifications during the pre-association operation or the
    input of credentials for the post-association operation. For more information about the IHV UI Extensions
    DLL, see
    <a href="https://msdn.microsoft.com/82f24545-75cb-4fbc-a98a-04dfac231c10">Native 802.11 IHV UI Extensions
    DLL</a>.

The IHV Extensions DLL initiates these requests for user interaction through calls to the
    <a href="..\wlanihv\nc-wlanihv-dot11ext_send_ui_request.md">Dot11ExtSendUIRequest</a> function. For
    each UI request, the DLL must format a
    <a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_ui_request.md">DOT11EXT_IHV_UI_REQUEST</a> structure to
    define the request, and must set the
    <b>guidUIRequest</b> member of this structure to a GUID value that uniquely identifies the UI request. The
    IHV Extensions DLL passes the address of the
    <b>DOT11EXT_IHV_UI_REQUEST</b> structure through the
    <i>pIhvUIRequest</i> parameter of the
    <b>Dot11ExtSendUIRequest</b> function.

The operating system can periodically call the
    <i>Dot11ExtIhvIsUIRequestPending</i> function to query the status of the UI request as identified by the
    <i>guidUIRequest</i> parameter. If the UI request is still pending, the IHV Extensions DLL must set *
    <i>pbIsRequestPending</i> to <b>TRUE</b>. Otherwise, the DLL must set *
    <i>pbIsRequestPending</i> to <b>FALSE</b>.




## -see-also

<a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_ui_request.md">DOT11EXT_IHV_UI_REQUEST</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_send_ui_request.md">Dot11ExtSendUIRequest</a>



 

 


