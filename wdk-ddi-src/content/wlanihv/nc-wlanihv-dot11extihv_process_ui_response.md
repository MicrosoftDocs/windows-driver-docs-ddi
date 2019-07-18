---
UID: NC:wlanihv.DOT11EXTIHV_PROCESS_UI_RESPONSE
title: DOT11EXTIHV_PROCESS_UI_RESPONSE (wlanihv.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvprocessuiresponse.htm
tech.root: netvista
ms.assetid: 1483be56-71c5-435b-843d-821f73dc79d7
ms.date: 02/16/2018
ms.keywords: DOT11EXTIHV_PROCESS_UI_RESPONSE, Dot11ExtIhvProcessUIResponse, Dot11ExtIhvProcessUIResponse callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_6bf65442-0a9a-4061-81a3-855b0ae80df4.xml, netvista.dot11extihvprocessuiresponse, wlanihv/Dot11ExtIhvProcessUIResponse
ms.topic: callback
f1_keywords:
 - "wlanihv/Dot11ExtIhvProcessUIResponse"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- wlanihv.h
api_name:
- Dot11ExtIhvProcessUIResponse
product:
- Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXTIHV_PROCESS_UI_RESPONSE callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The operating system calls the
  <i>Dot11ExtIhvProcessUIResponse</i> function to complete a UI request initiated by the IHV Extensions DLL
  through a call to
  <a href="..\wlanihv\nc-wlanihv-dot11ext_send_ui_request.md">Dot11ExtSendUIRequest</a>.


## -prototype


```cpp
DOT11EXTIHV_PROCESS_UI_RESPONSE Dot11ExtIhvProcessUIResponse;

DWORD APIENTRY Dot11ExtIhvProcessUIResponse(
  _In_     GUID   guidUIRequest,
  _In_     DWORD  dwByteCount,
  _In_opt_ LPVOID pvResponseBuffer
)
{ ... }
```


## -parameters




### -param guidUIRequest [in]

The GUID that identifies the request. This GUID value was created by the IHV Extensions DLL and
     passed through the
     <i>pIhvUIRequest</i> parameter of the call to
     <a href="..\wlanihv\nc-wlanihv-dot11ext_send_ui_request.md">Dot11ExtSendUIRequest</a>.


### -param dwByteCount [in]

The length, in bytes, of the data referenced through the
     <i>pvResponseBuffer</i> parameter.


### -param pvResponseBuffer [in, optional]

A pointer to the buffer that contains the user data.


## -returns



If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in
     Winerror.h.




## -remarks



The IHV Extensions DLL can issue requests to the IHV UI Extensions DLL for interaction with the user,
    such as the display of notifications during the pre-association operation or the input of credential for
    the post-association operation. For more information about the IHV UI Extensions DLL, see
    <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560635(v=vs.85)">Native 802.11 IHV UI Extensions
    DLL</a>.

The IHV Extensions DLL initiates these requests for user interaction through calls to the
    <a href="..\wlanihv\nc-wlanihv-dot11ext_send_ui_request.md">Dot11ExtSendUIRequest</a> function. For
    each UI request, the DLL must format a
    <a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_ui_request.md">DOT11EXT_IHV_UI_REQUEST</a> structure to
    define the request, and must set the
    <b>guidUIRequest</b> member of this structure to a GUID value that uniquely identifies the UI request. The
    DLL passes the address of the
    <b>DOT11EXT_IHV_UI_REQUEST</b> structure through the
    <i>pIhvUIRequest</i> parameter of the
    <b>Dot11ExtSendUIRequest</b> function.

After receiving this data from the IHV Extensions DLL, the operating system calls the
    <i>Dot11ExtIhvProcessUIResponse</i> function to process the user response, which is referenced through the
    <i>pvResponseBuffer</i> parameter. The response data is in a format defined by the IHV and has been validated by the IHV UI
    Extensions DLL.




## -see-also

<a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_ui_request.md">DOT11EXT_IHV_UI_REQUEST</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_send_ui_request.md">Dot11ExtSendUIRequest</a>



 

 


