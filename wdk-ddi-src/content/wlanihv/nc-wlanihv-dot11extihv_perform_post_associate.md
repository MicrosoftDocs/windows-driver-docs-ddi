---
UID: NC:wlanihv.DOT11EXTIHV_PERFORM_POST_ASSOCIATE
title: DOT11EXTIHV_PERFORM_POST_ASSOCIATE
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvperformpostassociate.htm
old-project: netvista
ms.assetid: a6e9af7d-4c33-4dea-92fe-e2cd8eed6697
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DRIVER_INFO_8W, *LPDRIVER_INFO_8W, *PDRIVER_INFO_8W, DRIVER_INFO_8W, DRIVER_INFO_8
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wlanihv.h
req.include-header: Wlanihv.h, Windot11.h, L2cmn.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: Dot11ExtIhvPerformPostAssociate
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

# DOT11EXTIHV_PERFORM_POST_ASSOCIATE callback



## -description

## -prototype

````
DOT11EXTIHV_PERFORM_POST_ASSOCIATE Dot11ExtIhvPerformPostAssociate;

DWORD APIENTRY Dot11ExtIhvPerformPostAssociate(
  _In_opt_ HANDLE                                   hIhvExtAdapter,
  _In_opt_ HANDLE                                   hSecuritySessionID,
  _In_     PDOT11_PORT_STATE                        pPortState,
  _In_     ULONG                                    uDot11AssocParamsBytes,
  _In_     PDOT11_ASSOCIATION_COMPLETION_PARAMETERS pDot11AssocParams
)
{ ... }
````


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
     <a href="netvista.ndis_status_dot11_association_completion">
     NDIS_STATUS_DOT11_ASSOCIATION_COMPLETION</a> indication.
     

For more information about the association operation, see 
     <a href="https://msdn.microsoft.com/04e97ea1-fe4b-471e-a7be-b5aa3ee88edc">Association Operations</a>.


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

For more information about the association operation, see 
    <a href="https://msdn.microsoft.com/04e97ea1-fe4b-471e-a7be-b5aa3ee88edc">Association Operations</a>.

The post-association operation must be completed asynchronously from the call to 
    <i>Dot11ExtIhvPerformPostAssociate</i>. After the post-association operation completes, the DLL must call
    
    <a href="..\wlanihv\nc-wlanihv-dot11ext_post_associate_completion.md">
    Dot11ExtPostAssociateCompletion</a>.

If the IHV Extensions DLL can initiate the post-association operation, the 
    <i>Dot11ExtIhvPerformPostAssociate</i> function must return ERROR_SUCCESS and complete the operation
    asynchronously.

For more information about the post-association operation, see 
    <a href="https://msdn.microsoft.com/e4c7ea7a-53ad-41b2-bf3f-03c770e58043">Post-Association Operations</a>.


## -see-also
<dl>
<dt>
<a href="..\wlclient\ns-wlclient-_dot11_port_state.md">DOT11_PORT_STATE</a>
</dt>
<dt>
<a href="netvista.ndis_status_dot11_association_completion">
   NDIS_STATUS_DOT11_ASSOCIATION_COMPLETION</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_adapter_reset.md">Dot11ExtIhvAdapterReset</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11ext_post_associate_completion.md">
   Dot11ExtPostAssociateCompletion</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXTIHV_PERFORM_POST_ASSOCIATE callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

