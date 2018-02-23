---
UID: NC:wlanihv.DOT11EXTIHV_PERFORM_POST_ASSOCIATE
title: DOT11EXTIHV_PERFORM_POST_ASSOCIATE
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvperformpostassociate.htm
old-project: netvista
ms.assetid: a6e9af7d-4c33-4dea-92fe-e2cd8eed6697
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.dot11extihvperformpostassociate, Dot11ExtIhvPerformPostAssociate callback function [Network Drivers Starting with Windows Vista], Dot11ExtIhvPerformPostAssociate, DOT11EXTIHV_PERFORM_POST_ASSOCIATE, DOT11EXTIHV_PERFORM_POST_ASSOCIATE, wlanihv/Dot11ExtIhvPerformPostAssociate, Native_802.11_IHV_Ext_ecc5c19e-9fde-48a4-b3a7-6a1f94a20765.xml
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
-	Dot11ExtIhvPerformPostAssociate
product: Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXTIHV_PERFORM_POST_ASSOCIATE callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The operating system calls the 
  <i>Dot11ExtIhvPerformPostAssociate</i> function to request that the IHV Extensions DLL initiate a
  post-association operation with the basic service set (BSS) network.


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
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/ndis-status-dot11-association-completion">
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

<div class="alert"><b>Note</b>  For Windows Vista, the IHV Extensions DLL supports only infrastructure basic
    service set (BSS) networks.</div>
<div> </div>
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
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/post-association-operations">Post-Association Operations</a>.




## -see-also

<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



<a href="..\wlclient\ns-wlclient-_dot11_port_state.md">DOT11_PORT_STATE</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/ndis-status-dot11-association-completion">
   NDIS_STATUS_DOT11_ASSOCIATION_COMPLETION</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_post_associate_completion.md">
   Dot11ExtPostAssociateCompletion</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_adapter_reset.md">Dot11ExtIhvAdapterReset</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXTIHV_PERFORM_POST_ASSOCIATE callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

