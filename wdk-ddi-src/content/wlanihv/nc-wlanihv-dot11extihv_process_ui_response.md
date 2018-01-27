---
UID: NC:wlanihv.DOT11EXTIHV_PROCESS_UI_RESPONSE
title: DOT11EXTIHV_PROCESS_UI_RESPONSE
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvprocessuiresponse.htm
old-project: netvista
ms.assetid: 1483be56-71c5-435b-843d-821f73dc79d7
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.dot11extihvprocessuiresponse, Dot11ExtIhvProcessUIResponse callback function [Network Drivers Starting with Windows Vista], Dot11ExtIhvProcessUIResponse, DOT11EXTIHV_PROCESS_UI_RESPONSE, DOT11EXTIHV_PROCESS_UI_RESPONSE, wlanihv/Dot11ExtIhvProcessUIResponse, Native_802.11_IHV_Ext_6bf65442-0a9a-4061-81a3-855b0ae80df4.xml
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
-	Dot11ExtIhvProcessUIResponse
product: Windows
targetos: Windows
req.typenames: *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W, DRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXTIHV_PROCESS_UI_RESPONSE callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The operating system calls the 
  <i>Dot11ExtIhvProcessUIResponse</i> function to complete a UI request initiated by the IHV Extensions DLL
  through a call to 
  <a href="..\wlanihv\nc-wlanihv-dot11ext_send_ui_request.md">Dot11ExtSendUIRequest</a>.


## -prototype


````
DOT11EXTIHV_PROCESS_UI_RESPONSE Dot11ExtIhvProcessUIResponse;

DWORD APIENTRY Dot11ExtIhvProcessUIResponse(
  _In_     GUID   guidUIRequest,
  _In_     DWORD  dwByteCount,
  _In_opt_ LPVOID pvResponseBuffer
)
{ ... }
````


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
    <mshelp:link keywords="netvista.native_802_11_ihv_ui_extensions_dll" tabindex="0">Native 802.11 IHV UI Extensions
    DLL</mshelp:link>.

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

<a href="..\wlanihv\nc-wlanihv-dot11ext_send_ui_request.md">Dot11ExtSendUIRequest</a>

<a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_ui_request.md">DOT11EXT_IHV_UI_REQUEST</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXTIHV_PROCESS_UI_RESPONSE callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

