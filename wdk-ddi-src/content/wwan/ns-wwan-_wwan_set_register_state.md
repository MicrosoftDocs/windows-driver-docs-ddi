---
UID: NS:wwan._WWAN_SET_REGISTER_STATE
title: _WWAN_SET_REGISTER_STATE (wwan.h)
description: The WWAN_SET_REGISTER_STATE structure represents the command to set the MB device's registration mode and the network provider it should register with.
old-location: netvista\wwan_set_register_state.htm
tech.root: netvista
ms.assetid: 617e80c2-2823-4393-81eb-b2cbd2b21be8
ms.date: 05/02/2018
keywords: ["_WWAN_SET_REGISTER_STATE structure"]
ms.keywords: "*PWWAN_SET_REGISTER_STATE, PWWAN_SET_REGISTER_STATE, PWWAN_SET_REGISTER_STATE structure pointer [Network Drivers Starting with Windows Vista], WWAN_SET_REGISTER_STATE, WWAN_SET_REGISTER_STATE structure [Network Drivers Starting with Windows Vista], WwanRef_17ed9aa3-5b69-4f1a-8c7e-fa39d6146615.xml, _WWAN_SET_REGISTER_STATE, netvista.wwan_set_register_state, wwan/PWWAN_SET_REGISTER_STATE, wwan/WWAN_SET_REGISTER_STATE"
f1_keywords:
 - "wwan/WWAN_SET_REGISTER_STATE"
 - "WWAN_SET_REGISTER_STATE"
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
- wwan.h
api_name:
- WWAN_SET_REGISTER_STATE
targetos: Windows
req.typenames: WWAN_SET_REGISTER_STATE, *PWWAN_SET_REGISTER_STATE
---

# _WWAN_SET_REGISTER_STATE structure


## -description


The WWAN_SET_REGISTER_STATE structure represents the command to set the MB device's registration mode
  and the network provider it should register with.


## -struct-fields




### -field ProviderId

A NULL-terminated numeric (0-9) string that represents the network provider identity.
     

For GSM-based networks, this string is a concatenation of a three-digit Mobile Country Code (MCC) and
     a two or three-digit Mobile Network Code (MNC). GSM-based carriers may have more than one MNC, and hence
     more than one 
     <b>ProviderId</b> .

For CDMA-based networks, this string is a five-digit System ID (SID). Generally, a CDMA-based carrier
     has more than one SID. Typically, the carrier has one SID for each market, which is usually divided
     geographically within a nation by regulations, such as Metropolitan Statistical Areas (MSA) in the
     United States of America. Miniport drivers of CDMA-based devices must specify
     WWAN_CDMA_DEFAULT_PROVIDER_ID if this information is not available.


### -field RegisterAction

The registration action that the miniport driver is requested to perform. If this member is set to     
     <b>WwanRegisterActionAutomatic</b>, the 
     <b>ProviderId</b> member should be ignored.


### -field WwanDataClass

A bitmap that represents the data access technologies that are preferred for a connection. For a
     detailed list of values, see the 
     <b>WwanDataClass</b> member of 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_device_caps">WWAN_DEVICE_CAPS</a>.
     

When multiple data-classes are set as preferred, miniport drivers are expected register to the
     highest available data-class technology that is currently visible. Miniport drivers should attempt to
     register the best available data-class as requested. If the device cannot register the data-class
     specified in this member, it should register the best available data-class.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndiswwan/ns-ndiswwan-_ndis_wwan_set_register_state">NDIS_WWAN_SET_REGISTER_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ne-wwan-_wwan_register_action">WWAN_REGISTER_ACTION</a>
 

 

