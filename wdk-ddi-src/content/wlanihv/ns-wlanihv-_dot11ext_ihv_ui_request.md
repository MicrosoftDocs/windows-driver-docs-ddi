---
UID: NS:wlanihv._DOT11EXT_IHV_UI_REQUEST
title: "_DOT11EXT_IHV_UI_REQUEST"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11ext_ihv_ui_request.htm
old-project: netvista
ms.assetid: 028e3445-320a-41c8-9577-219f9fbabe40
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: DOT11EXT_IHV_UI_REQUEST structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_2d145576-2a7d-4fff-ae75-a99e27ebbb18.xml, DOT11EXT_IHV_UI_REQUEST, PDOT11EXT_IHV_UI_REQUEST, _DOT11EXT_IHV_UI_REQUEST, wlanihv/PDOT11EXT_IHV_UI_REQUEST, *PDOT11EXT_IHV_UI_REQUEST, PDOT11EXT_IHV_UI_REQUEST structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11ext_ihv_ui_request, wlanihv/DOT11EXT_IHV_UI_REQUEST
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wlanihv.h
apiname:
-	DOT11EXT_IHV_UI_REQUEST
product: Windows
targetos: Windows
req.typenames: DOT11EXT_IHV_UI_REQUEST, *PDOT11EXT_IHV_UI_REQUEST
req.product: Windows 10 or later.
---

# _DOT11EXT_IHV_UI_REQUEST structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11EXT_IHV_UI_REQUEST structure specifies a request made by the IHV Extensions DLL to the IHV
  UI extensions DLL.


## -syntax


````
typedef struct _DOT11EXT_IHV_UI_REQUEST {
  DWORD dwSessionId;
  GUID  guidUIRequest;
  CLSID UIPageClsid;
  DWORD dwByteCount;
  BYTE  *pvUIRequest;
} DOT11EXT_IHV_UI_REQUEST, *PDOT11EXT_IHV_UI_REQUEST;
````


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
     <a href="http://go.microsoft.com/fwlink/p/?linkid=56607">IWizardExtension COM Interface</a>.


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



<a href="..\wlanihv\nc-wlanihv-dot11extihv_query_ui_request.md">Dot11ExtIhvQueryUIRequest</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_send_ui_request.md">Dot11ExtSendUIRequest</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_IHV_UI_REQUEST structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

