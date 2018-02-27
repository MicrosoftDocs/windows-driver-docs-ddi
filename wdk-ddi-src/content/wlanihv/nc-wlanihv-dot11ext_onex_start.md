---
UID: NC:wlanihv.DOT11EXT_ONEX_START
title: DOT11EXT_ONEX_START
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extstartonex.htm
old-project: netvista
ms.assetid: d4117da4-349a-4143-b2a8-d4edf6c02e7b
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: DOT11EXT_ONEX_START, Dot11ExtStartOneX, Dot11ExtStartOneX callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_71199b82-64e0-4b96-89f0-e964dd959077.xml, netvista.dot11extstartonex, wlanihv/Dot11ExtStartOneX
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	wlanihv.h
api_name:
-	Dot11ExtStartOneX
product: Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXT_ONEX_START callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The IHV Extensions DLL calls the 
  <b>Dot11ExtStartOneX</b> function to initiate an 802.1X authentication operation
  with the access point (AP). In this situation, the authentication is managed by the 802.1X module of the
  Native 802.11 framework instead of by the IHV Extensions DLL.


## -prototype


````
DWORD WINAPI * Dot11ExtStartOneX(
  _In_opt_ HANDLE         hDot11SvcHandle,
  _In_opt_ EAP_ATTRIBUTES *pEapAttribute
);
````


## -parameters




### -param hDot11SvcHandle [in, optional]

The handle used by the operating system to reference the wireless LAN (WLAN) adapter. This handle
     value was specified through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


### -param *pEapAttributes








#### - pEapAttribute [in, optional]

A pointer to an EAP_ATTRIBUTES array structure that contains the EAP attributes returned by the
     authentication session. For more information about EAP_ATTRIBUTES, see the Microsoft Windows SDK
     documentation.


## -returns



If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in 
     Winerror.h.




## -remarks



The IHV Extensions DLL can initiate an 802.1X authentication operation by using the 802.1X module of
    the Native 802.11 framework. This allows the DLL to use the standard extensible authentication protocol
    (EAP) algorithms that are supported by the operating system.

The IHV Extensions DLL initiates the 802.1X authentication operation by calling the 
    <b>Dot11ExtStartOneX</b> function. 
    <b>Dot11ExtStartOneX</b> can only be called either during a post-association
    operation or after the operation has completed. For more information about this operation, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/post-association-operations">Post-Association Operations</a>.

When the 
    <b>Dot11ExtStartOneX</b> function is called, the operating system sends an EAP
    over LAN (EAPOL) Start packet to the AP. If the AP fails to respond after three transmissions of the
    EAPOL-Start packet, the operating system fails the 802.1X authentication operation and calls the 
    <a href="..\wlanihv\nc-wlanihv-dot11extihv_onex_indicate_result.md">
    Dot11ExtIhvOneXIndicateResult</a> IHV Handler function. For more information about the EAPOL-Start
    packet, refer to Clause 7.5 and Clause 8.4.2 of the IEEE 802.1X-1999 standard.

After the 802.1X authentication operation is initiated, the IHV Extensions DLL must follow these
    guidelines.

<ul>
<li>
The IHV Extensions must forward all EAPOL packets to the operating system for processing. When the
      DLL receives an EAPOL packet through a call to the 
      <a href="..\wlanihv\nc-wlanihv-dot11extihv_receive_packet.md">Dot11ExtIhvReceivePacket</a> IHV
      Handler function, the DLL must call 
      <a href="..\wlanihv\nc-wlanihv-dot11ext_process_onex_packet.md">Dot11ExtProcessOneXPacket</a> to
      forward the packet to the operating system.

For more information about EAPOL packets, refer to Clause 7 of the IEEE 802.1X-2001 standard.

<div class="alert"><b>Note</b>  The IHV Extensions DLL is responsible for processing EAPOL-Key packets and must
      not forward these to the operating system.</div>
<div> </div>
</li>
<li>
When the 802.1X authentication operation is completed, the operating system calls the 
      <a href="..\wlanihv\nc-wlanihv-dot11extihv_onex_indicate_result.md">
      Dot11ExtIhvOneXIndicateResult</a> IHV Handler function to indicate that authorization is in
      progress.

</li>
<li>
The IHV Extensions DLL can cancel the 802.1X authentication operation by calling 
      <a href="..\wlanihv\nc-wlanihv-dot11ext_onex_stop.md">Dot11ExtStopOneX</a>.

</li>
</ul>
For more information about using the 802.1X module for authentication, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/interface-to-the-native-802-11-802-1x-module">Interface to the Native
    802.11 802.1X Module</a>.




## -see-also

<a href="..\wlanihv\nc-wlanihv-dot11ext_post_associate_completion.md">
   Dot11ExtPostAssociateCompletion</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_receive_packet.md">Dot11ExtIhvReceivePacket</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_process_onex_packet.md">Dot11ExtProcessOneXPacket</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_onex_indicate_result.md">
   Dot11ExtIhvOneXIndicateResult</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_post_associate.md">
   Dot11ExtIhvPerformPostAssociate</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_onex_stop.md">Dot11ExtStopOneX</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_ONEX_START callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

