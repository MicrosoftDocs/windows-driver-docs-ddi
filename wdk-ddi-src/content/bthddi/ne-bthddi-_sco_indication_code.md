---
UID: NE:bthddi._SCO_INDICATION_CODE
title: _SCO_INDICATION_CODE (bthddi.h)
description: The SCO_INDICATION_CODE enumeration type describes the type of an incoming SCO connection or bonding state change. The Bluetooth driver stack passes a value from this enumeration in the Indication argument of a profile driver's SCO Callback Function.
old-location: bltooth\sco_indication_code.htm
tech.root: bltooth
ms.assetid: 4223dd79-cac7-41bd-8c94-12baf8e8367a
ms.date: 04/27/2018
ms.keywords: "*PSCO_INDICATION_CODE, PSCO_INDICATION_CODE, PSCO_INDICATION_CODE enumeration pointer [Bluetooth Devices], SCO_INDICATION_CODE, SCO_INDICATION_CODE enumeration [Bluetooth Devices], ScoIndicationAddReference, ScoIndicationReleaseReference, ScoIndicationRemoteConnect, ScoIndicationRemoteDisconnect, _SCO_INDICATION_CODE, bltooth.sco_indication_code, bth_enums_e7290768-826f-4240-904c-07222b05d377.xml, bthddi/PSCO_INDICATION_CODE, bthddi/SCO_INDICATION_CODE, bthddi/ScoIndicationAddReference, bthddi/ScoIndicationReleaseReference, bthddi/ScoIndicationRemoteConnect, bthddi/ScoIndicationRemoteDisconnect"
f1_keywords:
 - "bthddi/SCO_INDICATION_CODE"
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
- bthddi.h
api_name:
- SCO_INDICATION_CODE
product:
- Windows
targetos: Windows
req.typenames: SCO_INDICATION_CODE, *PSCO_INDICATION_CODE
---

# _SCO_INDICATION_CODE enumeration


## -description


The SCO_INDICATION_CODE enumeration type describes the type of an incoming SCO connection or bonding
  state change. The Bluetooth driver stack passes a value from this enumeration in the 
  <i>Indication</i> argument of a profile driver's 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/nc-bthddi-pfnsco_indication_callback">SCO Callback Function</a>.


## -enum-fields




### -field ScoIndicationAddReference

This value indicates that the profile driver should add one reference to its device object.


### -field ScoIndicationReleaseReference

This value indicates that the profile driver can release one reference to its device
     object.


### -field ScoIndicationRemoteConnect

This value indicates to a profile driver that a remote device is trying to connect to the local
     radio. Profile drivers accept or reject this request by 
     <a href="https://docs.microsoft.com/previous-versions/ff536657(v=vs.85)">building and sending</a> a 
     <a href="https://social.msdn.microsoft.com/Forums/0a9a4323-d046-4d27-9d22-4974dbab30a4/home?forum=windows-bluetooth-sco-brbscoopenchannelresponse">
     BRB_SCO_OPEN_CHANNEL_RESPONSE</a> request.


### -field ScoIndicationRemoteDisconnect

This value indicates to a profile driver that a remote device is disconnecting from the local
     radio.


## -see-also




<a href="https://docs.microsoft.com/previous-versions/ff536628(v=vs.85)">BRB_SCO_REGISTER_SERVER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ni-bthioctl-ioctl_internal_bth_submit_brb">IOCTL_INTERNAL_BTH_SUBMIT_BRB</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/nc-bthddi-pfnsco_indication_callback">SCO Callback Function</a>
 

 

