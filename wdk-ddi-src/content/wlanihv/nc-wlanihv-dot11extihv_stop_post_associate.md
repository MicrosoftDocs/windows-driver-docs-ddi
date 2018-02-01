---
UID: NC:wlanihv.DOT11EXTIHV_STOP_POST_ASSOCIATE
title: DOT11EXTIHV_STOP_POST_ASSOCIATE
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvstoppostassociate.htm
old-project: netvista
ms.assetid: bd924049-3932-4e85-908e-c3fb488b3a8c
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.dot11extihvstoppostassociate, Dot11ExtIhvStopPostAssociate callback function [Network Drivers Starting with Windows Vista], Dot11ExtIhvStopPostAssociate, DOT11EXTIHV_STOP_POST_ASSOCIATE, DOT11EXTIHV_STOP_POST_ASSOCIATE, wlanihv/Dot11ExtIhvStopPostAssociate, Native_802.11_IHV_Ext_674652ff-a01d-493b-9b11-bff378f25f2a.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wlanihv.h
req.include-header: Wlanihv.h, Windot11.h
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
-	Dot11ExtIhvStopPostAssociate
product: Windows
targetos: Windows
req.typenames: "*PDRIVER_INFO_8W, DRIVER_INFO_8W, *LPDRIVER_INFO_8W"
req.product: Windows 10 or later.
---

# DOT11EXTIHV_STOP_POST_ASSOCIATE callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The operating system calls the 
  <i>Dot11ExtIhvStopPostAssociate</i> function to cancel the post-association operation initiated through a
  call to the 
  <a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_post_associate.md">
  Dot11ExtIhvPerformPostAssociate</a> IHV Handler function.


## -prototype


````
DOT11EXTIHV_STOP_POST_ASSOCIATE Dot11ExtIhvStopPostAssociate;

DWORD APIENTRY Dot11ExtIhvStopPostAssociate(
  _In_opt_ HANDLE             hIhvExtAdapter,
  _In_     PDOT11_MAC_ADDRESS pPeer,
  _In_     DOT11_ASSOC_STATUS dot11AssocStatus
)
{ ... }
````


## -parameters




### -param hIhvExtAdapter [in, optional]

The handle used by the IHV Extensions DLL to reference the wireless LAN (WLAN) adapter. This
     handle value was specified through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


### -param pPeer [in]

A pointer to a 
     <a href="..\windot11\ns-windot11-_dot11_mac_address.md">DOT11_MAC_ADDRESS</a> structure, which
     contains the media access control (MAC) of the access point (AP) with which the IHV Extensions DLL
     initiated a post-association operation.
     
<div class="alert"><b>Note</b>  For Windows Vista, the IHV Extensions DLL supports only infrastructure basic
     service set (BSS) networks.</div><div> </div>

### -param dot11AssocStatus [in]

A 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff547652">DOT11_ASSOC_STATUS</a> type that specifies the
     association status of the 802.11 station to the network.


## -returns


If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in 
     Winerror.h.



## -remarks


The operating system calls the 
    <i>Dot11ExtIhvStopPostAssociate</i> function to cancel the post-association operation whenever one of the
    following occurs.
<ul>
<li>
The WLAN adapter completes a disassociation operation with the AP. In this situation, the Native
      802.11 miniport driver, which manages the adapter, makes a media-specific 
      <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/ndis-status-dot11-disassociation">
      NDIS_STATUS_DOT11_DISASSOCIATION</a> indication. For more information about the disassociation
      operation, see 
      <a href="https://msdn.microsoft.com/3589a694-a69a-481f-8479-ea918287736d">Disassociation Operations</a>.

</li>
<li>
The WLAN adapter is disabled or removed. In this situation, the operating system calls the 
      <i>Dot11ExtIhvStopPostAssociate</i> function before it calls the 
      <a href="..\wlanihv\nc-wlanihv-dot11extihv_deinit_adapter.md">
      Dot11ExtIhvDeinitAdapter</a> function.

</li>
</ul>The operating system calls the 
    <i>Dot11ExtIhvStopPostAssociate</i> function to notify the IHV Extensions DLL that the data port created
    for the association is down. The operating system calls this function regardless of whether the DLL has
    completed the post-association operation through a call to 
    <a href="..\wlanihv\nc-wlanihv-dot11ext_post_associate_completion.md">
    Dot11ExtPostAssociateCompletion</a>.

For more information about the post-association operation, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/post-association-operations">Post-Association Operations</a>.



## -see-also

<a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_post_associate.md">
   Dot11ExtIhvPerformPostAssociate</a>

<a href="..\wlanihv\nc-wlanihv-dot11extihv_deinit_adapter.md">Dot11ExtIhvDeinitAdapter</a>

<a href="..\windot11\ns-windot11-_dot11_mac_address.md">DOT11_MAC_ADDRESS</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/ndis-status-dot11-disassociation">
   NDIS_STATUS_DOT11_DISASSOCIATION</a>

<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547652">DOT11_ASSOC_STATUS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXTIHV_STOP_POST_ASSOCIATE callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

