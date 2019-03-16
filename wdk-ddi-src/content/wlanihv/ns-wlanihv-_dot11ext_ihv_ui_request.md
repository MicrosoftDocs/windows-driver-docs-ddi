---
UID: NS:wlanihv._DOT11EXT_IHV_UI_REQUEST
title: _DOT11EXT_IHV_UI_REQUEST (wlanihv.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11ext_ihv_ui_request.htm
tech.root: netvista
ms.assetid: 028e3445-320a-41c8-9577-219f9fbabe40
ms.date: 02/16/2018
ms.keywords: "*PDOT11EXT_IHV_UI_REQUEST, DOT11EXT_IHV_UI_REQUEST, DOT11EXT_IHV_UI_REQUEST structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_2d145576-2a7d-4fff-ae75-a99e27ebbb18.xml, PDOT11EXT_IHV_UI_REQUEST, PDOT11EXT_IHV_UI_REQUEST structure pointer [Network Drivers Starting with Windows Vista], _DOT11EXT_IHV_UI_REQUEST, netvista.dot11ext_ihv_ui_request, wlanihv/DOT11EXT_IHV_UI_REQUEST, wlanihv/PDOT11EXT_IHV_UI_REQUEST"
ms.topic: struct
req.header: wlanihv.h
req.include-header: Wlanihv.h
req.target-type: Windows
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
- HeaderDef
api_location:
- wlanihv.h
api_name:
- DOT11EXT_IHV_UI_REQUEST
product:
- Windows
targetos: Windows
req.typenames: DOT11EXT_IHV_UI_REQUEST, *PDOT11EXT_IHV_UI_REQUEST
req.product: Windows 10 or later.
---

# _DOT11EXT_IHV_UI_REQUEST structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11EXT_IHV_UI_REQUEST structure specifies a request made by the IHV Extensions DLL to the IHV
  UI extensions DLL.


## -syntax


```cpp
typedef struct _DOT11EXT_IHV_UI_REQUEST {
  DWORD dwSessionId;
  GUID  guidUIRequest;
  CLSID UIPageClsid;
  DWORD dwByteCount;
  BYTE  *pvUIRequest;
} DOT11EXT_IHV_UI_REQUEST, *PDOT11EXT_IHV_UI_REQUEST;
```


## -struct-fields




### -field dwSessionId

The session identifier (ID) of the current user.


### -field guidUIRequest

A globally unique ID (GUID) which identifies the UI request.


### -field UIPageClsid

The
     <b>IWizardExtension</b> COM class ID (CLSID) of the target UI page that will handle this request. For
     more information about the
     <b>IWizardExtension</b> COM interface, see
     <a href="https://go.microsoft.com/fwlink/p/?linkid=56607">IWizardExtension COM Interface</a>.


### -field dwByteCount

The length, in bytes, within the buffer referenced through the
     <b>pvUIRequest</b> member.


### -field pvUIRequest

A pointer to a buffer that contains the request data in a format defined by the independent
     hardware vendor (IHV).


## -remarks



The IHV Extensions DLL can issue requests to the IHV UI extensions DLL to interact with the user for
    input to network UI extensions defined by the IHV. The IHV Extensions DLL initiates these requests
    through calls to the
    <a href="..\wlanihv\nc-wlanihv-dot11ext_send_ui_request.md">Dot11ExtSendUIRequest</a> or
    <a href="..\wlanihv\nc-wlanihv-dot11extihv_query_ui_request.md">
    Dot11ExtIhvQueryUIRequest</a> functions.

For each UI request, the DLL must format a DOT11EXT_IHV_UI_REQUEST structure to define the request,
    and must set the
    <b>guidUIRequest</b> member of this structure to a GUID value that uniquely identifies the UI request.




## -see-also

<a href="..\wlanihv\nc-wlanihv-dot11extihv_is_ui_request_pending.md">
   Dot11ExtIhvIsUIRequestPending</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_send_ui_request.md">Dot11ExtSendUIRequest</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_query_ui_request.md">Dot11ExtIhvQueryUIRequest</a>



 

 


