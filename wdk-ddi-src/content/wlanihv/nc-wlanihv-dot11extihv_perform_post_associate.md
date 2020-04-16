---
UID: NC:wlanihv.DOT11EXTIHV_PERFORM_POST_ASSOCIATE
title: DOT11EXTIHV_PERFORM_POST_ASSOCIATE (wlanihv.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvperformpostassociate.htm
tech.root: netvista
ms.assetid: a6e9af7d-4c33-4dea-92fe-e2cd8eed6697
ms.date: 02/16/2018
keywords: ["DOT11EXTIHV_PERFORM_POST_ASSOCIATE callback"]
ms.keywords: DOT11EXTIHV_PERFORM_POST_ASSOCIATE, Dot11ExtIhvPerformPostAssociate, Dot11ExtIhvPerformPostAssociate callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_ecc5c19e-9fde-48a4-b3a7-6a1f94a20765.xml, netvista.dot11extihvperformpostassociate, wlanihv/Dot11ExtIhvPerformPostAssociate
f1_keywords:
 - "wlanihv/Dot11ExtIhvPerformPostAssociate"
req.header: wlanihv.h
req.include-header: Wlanihv.h, Windot11.h, L2cmn.h
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
- Dot11ExtIhvPerformPostAssociate
product:
- Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXTIHV_PERFORM_POST_ASSOCIATE callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The operating system calls the
  <i>Dot11ExtIhvPerformPostAssociate</i> function to request that the IHV Extensions DLL initiate a
  post-association operation with the basic service set (BSS) network.


## -prototype


```cpp
DOT11EXTIHV_PERFORM_POST_ASSOCIATE Dot11ExtIhvPerformPostAssociate;

DWORD APIENTRY Dot11ExtIhvPerformPostAssociate(
  _In_opt_ HANDLE                                   hIhvExtAdapter,
  _In_opt_ HANDLE                                   hSecuritySessionID,
  _In_     PDOT11_PORT_STATE                        pPortState,
  _In_     ULONG                                    uDot11AssocParamsBytes,
  _In_     PDOT11_ASSOCIATION_COMPLETION_PARAMETERS pDot11AssocParams
)
{ ... }
```


## -parameters




### -param hIhvExtAdapter [in, optional]

The handle used by the IHV Extensions DLL to reference the wireless LAN (WLAN) adapter. This
     handle value was specified through a previous call to the
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


### -param hSecuritySessionID [in, optional]

The handle of the security session. The IHV Extensions DLL must use this handle value when it
     calls
     <a href="..\wlanihv\nc-wlanihv-dot11ext_post_associate_completion.md">
     Dot11ExtPostAssociateCompletion</a> to asynchronously complete the post-association operation.


### -param pPortState [in]

A pointer to a
     <a href="..\wlclient\ns-wlclient-_dot11_port_state.md">DOT11_PORT_STATE</a> structure, which
     specifies the current port state of the security session.


### -param uDot11AssocParamsBytes [in]

The length, in bytes, of the data referenced through the
     <i>pDot11AssocParams</i> parameter.


### -param pDot11AssocParams [in]

A pointer to a
     <a href="..\windot11\ns-windot11-dot11_association_completion_parameters.md">
     DOT11_ASSOCIATION_COMPLETION_PARAMETERS</a> structure, which specifies the result of the association
     operation completed by the WLAN adapter. The Native 802.11 miniport driver, which manages the WLAN
     adapter, includes a DOT11_ASSOCIATION_COMPLETION_PARAMETERS structure when it makes a media-specific
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-dot11-association-completion">
     NDIS_STATUS_DOT11_ASSOCIATION_COMPLETION</a> indication.


For more information about the association operation, see
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/association-operations">Association Operations</a>.


## -returns



If the IHV Extension DLL can initiate the post-association operation, it must complete the operation
      asynchronously. In this situation, the function returns ERROR_SUCCESS.

If the IHV Extensions DLL cannot initiate the post-association operation, it returns an error code
      defined in
      <i>Winerror.h</i>.




## -remarks



The operating system calls the
    <i>Dot11ExtIhvPerformPostAssociate</i> function to initiate a post-association operation with the IHV
    Extensions DLL. The operating system initiates this operation after the WLAN adapter completes an
    association operation with an access point (AP) in an infrastructure basic service set (BSS) network.

<div class="alert"><b>Note</b>  For Windows Vista, the IHV Extensions DLL supports only infrastructure basic
    service set (BSS) networks.</div>
<div> </div>
For more information about the association operation, see
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/association-operations">Association Operations</a>.

The post-association operation must be completed asynchronously from the call to
    <i>Dot11ExtIhvPerformPostAssociate</i>. After the post-association operation completes, the DLL must call
    <a href="..\wlanihv\nc-wlanihv-dot11ext_post_associate_completion.md">
    Dot11ExtPostAssociateCompletion</a>.

If the IHV Extensions DLL can initiate the post-association operation, the
    <i>Dot11ExtIhvPerformPostAssociate</i> function must return ERROR_SUCCESS and complete the operation
    asynchronously.

For more information about the post-association operation, see
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/post-association-operations">Post-Association Operations</a>.




## -see-also

<a href="..\wlanihv\nc-wlanihv-dot11ext_post_associate_completion.md">
   Dot11ExtPostAssociateCompletion</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



<a href="..\wlclient\ns-wlclient-_dot11_port_state.md">DOT11_PORT_STATE</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_adapter_reset.md">Dot11ExtIhvAdapterReset</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-dot11-association-completion">
   NDIS_STATUS_DOT11_ASSOCIATION_COMPLETION</a>



 

 


