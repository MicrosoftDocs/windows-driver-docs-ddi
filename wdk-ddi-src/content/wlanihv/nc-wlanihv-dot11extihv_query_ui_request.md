---
UID: NC:wlanihv.DOT11EXTIHV_QUERY_UI_REQUEST
title: DOT11EXTIHV_QUERY_UI_REQUEST (wlanihv.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvqueryuirequest.htm
tech.root: netvista
ms.assetid: 37c01180-0742-4764-88c3-9ceb807a0086
ms.date: 02/16/2018
keywords: ["DOT11EXTIHV_QUERY_UI_REQUEST callback"]
ms.keywords: DOT11EXTIHV_QUERY_UI_REQUEST, Dot11ExtIhvQueryUIRequest, Dot11ExtIhvQueryUIRequest callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_b820a678-9e05-4f96-87bd-ed1154317091.xml, netvista.dot11extihvqueryuirequest, wlanihv/Dot11ExtIhvQueryUIRequest
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
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
f1_keywords:
 - DOT11EXTIHV_QUERY_UI_REQUEST
 - wlanihv/DOT11EXTIHV_QUERY_UI_REQUEST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - wlanihv.h
api_name:
 - Dot11ExtIhvQueryUIRequest
---

# DOT11EXTIHV_QUERY_UI_REQUEST callback


## -description

<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The operating system calls the
  <i>Dot11ExtIhvQueryUIRequest</i> function whenever the connection status changes. When this function is
  called, the IHV Extensions DLL returns a
  <a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_ui_request.md">DOT11EXT_IHV_UI_REQUEST</a> structure that
  the operating system can use for a UI request.

## -parameters

### -param hIhvExtAdapter 

[in, optional]
The handle used by the IHV Extensions DLL to reference the wireless LAN (WLAN) adapter. This
     handle value was specified through a previous call to the
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.

### -param connectionPhase 

[in]
The current connection phase. The data type for this member is the
     <b>DOT11EXT_IHV_CONNECTION_PHASE</b> enumeration:






#### connection_phase_any

Specifies any connection phase.



#### connection_phase_initial_connection

Specifies the connection phase before the IHV Extensions DLL initiates a pre-association
       operation. For more information about the pre-association operation, see
       <a href="https://docs.microsoft.com/windows-hardware/drivers/network/pre-association-operation-overview">Pre-Association
       Operations</a>.



#### connection_phase_post_l3_connection

Specifies the connection phase after the IHV Extensions DLL completes a post-association
       operation. For more information about the post-association operation, see
       <a href="https://docs.microsoft.com/windows-hardware/drivers/network/post-association-operations">Post-Association
       Operations</a>.

### -param ppIhvUIRequest 

[out]
The address of a pointer to a
     <a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_ui_request.md">DOT11EXT_IHV_UI_REQUEST</a> structure.
     The IHV Extensions DLL must allocate a buffer for the DOT11EXT_IHV_UI_REQUEST structure by calling
     <a href="..\wlanihv\nc-wlanihv-dot11ext_allocate_buffer.md">Dot11ExtAllocateBuffer</a>.

## -returns

If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in
     Winerror.h.

## -prototype

```cpp
DOT11EXTIHV_QUERY_UI_REQUEST Dot11ExtIhvQueryUIRequest;

DWORD APIENTRY Dot11ExtIhvQueryUIRequest(
  _In_opt_ HANDLE                        hIhvExtAdapter,
  _In_     DOT11EXT_IHV_CONNECTION_PHASE connectionPhase,
  _Out_    PDOT11EXT_IHV_UI_REQUEST      *ppIhvUIRequest
)
{ ... }
```

## -remarks

When
    <i>Dot11ExtIhvQueryUIRequest</i> is called, the IHV Extensions DLL must allocate and return a buffer
    formatted as a
    <a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_ui_request.md">DOT11EXT_IHV_UI_REQUEST</a> structure.
    In this situation, the DLL must follow these guidelines:

<ul>
<li>
The IHV Extensions DLL must call
      <a href="..\wlanihv\nc-wlanihv-dot11ext_allocate_buffer.md">Dot11ExtAllocateBuffer</a> to
      allocate the buffer. After the DLL returns from
      <i>Dot11ExtIhvQueryUIRequest</i>, the operating system is responsible for calling
      <a href="..\wlanihv\nc-wlanihv-dot11ext_free_buffer.md">Dot11ExtFreeBuffer</a> to free the
      buffer.

</li>
<li>
The IHV Extensions DLL formats the
      <a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_ui_request.md">DOT11EXT_IHV_UI_REQUEST</a> structure
      for a UI request appropriate for the change in connection status.

For example, if
      <i>connectionPhase</i> is set to
      <b>connection_phase_initial_connection</b>, the IHV Extensions DLL could set the members of the
      DOT11EXT_IHV_UI_REQUEST structure to reference a user interface page that notifies the user of the
      start of the connection operation.

</li>
</ul>

## -see-also

<a href="..\wlanihv\nc-wlanihv-dot11ext_allocate_buffer.md">Dot11ExtAllocateBuffer</a>



<a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_ui_request.md">DOT11EXT_IHV_UI_REQUEST</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_free_buffer.md">Dot11ExtFreeBuffer</a>

