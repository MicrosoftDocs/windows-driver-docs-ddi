---
UID: NC:wlanihv.DOT11EXT_SEND_UI_REQUEST
title: DOT11EXT_SEND_UI_REQUEST
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extsenduirequest.htm
tech.root: netvista
ms.assetid: c8d2ff26-d233-4683-9811-c23896203bd5
ms.date: 2/16/2018
ms.keywords: DOT11EXT_SEND_UI_REQUEST, Dot11ExtSendUIRequest, Dot11ExtSendUIRequest callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_1adad832-45d5-4691-85d9-0acc0534cdc0.xml, netvista.dot11extsenduirequest, wlanihv/Dot11ExtSendUIRequest
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
-	Dot11ExtSendUIRequest
product:
- Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXT_SEND_UI_REQUEST callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The IHV Extensions DLL calls the
  <b>Dot11ExtSendUIRequest</b> function to request user notification or input
  through the
  <a href="https://msdn.microsoft.com/82f24545-75cb-4fbc-a98a-04dfac231c10">Native 802.11 IHV UI Extensions
  DLL</a>.


## -prototype


```cpp
DWORD WINAPI * Dot11ExtSendUIRequest(
  _In_opt_ HANDLE                   hDot11SvcHandle,
  _In_     PDOT11EXT_IHV_UI_REQUEST pIhvUIRequest
);
```


## -parameters




### -param hDot11SvcHandle [in, optional]

The handle used by the operating system to reference the wireless LAN (WLAN) adapter. This handle
     value was specified through a previous call to the
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


### -param pIhvUIRequest [in]

A pointer to a caller-allocated buffer, formatted as a
     <a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_ui_request.md">
     DOT11EXT_IHV_UI_REQUEST</a> structure.


## -returns



If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in
     Winerror.h.




## -remarks



The IHV Extensions DLL must follow these guidelines when calling the
    <b>Dot11ExtSendUIRequest</b> function.

<ul>
<li>
Requests for event notification by the
      <a href="https://msdn.microsoft.com/82f24545-75cb-4fbc-a98a-04dfac231c10">Native 802.11 IHV UI Extensions
      DLL</a> are completed through a call to the
      <a href="..\wlanihv\nc-wlanihv-dot11extihv_process_ui_response.md">
      Dot11ExtIhvProcessUIResponse</a> IHV Handler function. The IHV Extensions DLL must not free the
      memory referenced by the
      <i>pIhvUIRequest</i> parameter until the request is completed.

</li>
<li>
If the operating system calls the
      <a href="..\wlanihv\nc-wlanihv-dot11extihv_adapter_reset.md">Dot11ExtIhvAdapterReset</a> or
      <a href="..\wlanihv\nc-wlanihv-dot11extihv_deinit_adapter.md">Dot11ExtIhvDeinitAdapter</a> IHV
      handler functions, the IHV Extensions DLL can assume that the UI request has been canceled. In this
      situation, the DLL must free the memory referenced by the
      <i>pIhvUIRequest</i> parameter.

</li>
<li>
The operating system can query the completion status of the request through a call to the
      <a href="..\wlanihv\nc-wlanihv-dot11extihv_is_ui_request_pending.md">
      Dot11ExtIhvIsUIRequestPending</a> IHV Handler function.

</li>
</ul>



## -see-also

<a href="..\wlanihv\nc-wlanihv-dot11extihv_adapter_reset.md">Dot11ExtIhvAdapterReset</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_deinit_adapter.md">Dot11ExtIhvDeinitAdapter</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_process_ui_response.md">
   Dot11ExtIhvProcessUIResponse</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_is_ui_request_pending.md">
   Dot11ExtIhvIsUIRequestPending</a>



 

 


