---
UID: NC:wlanihv.DOT11EXTIHV_IS_UI_REQUEST_PENDING
title: DOT11EXTIHV_IS_UI_REQUEST_PENDING
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvisuirequestpending.htm
old-project: netvista
ms.assetid: e8747dc5-7ef7-4914-baf7-683ddfe68313
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
req.alt-api: Dot11ExtIhvIsUIRequestPending
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

# DOT11EXTIHV_IS_UI_REQUEST_PENDING callback



## -description

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
<dl>
<dt>
<a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_ui_request.md">DOT11EXT_IHV_UI_REQUEST</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11ext_send_ui_request.md">Dot11ExtSendUIRequest</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXTIHV_IS_UI_REQUEST_PENDING callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

