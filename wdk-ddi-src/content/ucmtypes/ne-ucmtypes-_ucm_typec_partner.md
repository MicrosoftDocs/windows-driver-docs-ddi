---
UID: NE:ucmtypes._UCM_TYPEC_PARTNER
title: "_UCM_TYPEC_PARTNER"
author: windows-driver-content
description: Defines the state of the Type-C connector.
old-location: buses\ucm_type_c_port_state.htm
old-project: usbref
ms.assetid: 4779E943-5C13-4DE2-AF8F-37657F0F99C0
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UCM_TYPEC_PARTNER, UCM_TYPEC_PARTNER enumeration [Buses], UcmTypeCPartnerStateAudioAccessory, UcmTypeCPartnerStateDebugAccessory, UcmTypeCPartnerStateDfp, UcmTypeCPartnerStateInvalid, UcmTypeCPartnerStatePoweredCableNoUfp, UcmTypeCPartnerStatePoweredCableWithUfp, UcmTypeCPartnerStateUfp, _UCM_TYPEC_PARTNER, buses.ucm_type_c_port_state, ucmtypes/UCM_TYPEC_PARTNER, ucmtypes/UcmTypeCPartnerStateAudioAccessory, ucmtypes/UcmTypeCPartnerStateDebugAccessory, ucmtypes/UcmTypeCPartnerStateDfp, ucmtypes/UcmTypeCPartnerStateInvalid, ucmtypes/UcmTypeCPartnerStatePoweredCableNoUfp, ucmtypes/UcmTypeCPartnerStatePoweredCableWithUfp, ucmtypes/UcmTypeCPartnerStateUfp
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ucmtypes.h
req.include-header: Ucmcx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 2.15
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
-	HeaderDef
api_location:
-	Ucmtypes.h
api_name:
-	UCM_TYPEC_PARTNER
product: Windows
targetos: Windows
req.typenames: UCM_TYPEC_PARTNER
req.product: Windows 10 or later.
---

# _UCM_TYPEC_PARTNER enumeration


## -description


Defines the state of the Type-C connector.


## -enum-fields




### -field UcmTypeCPartnerInvalid


### -field UcmTypeCPartnerUfp


### -field UcmTypeCPartnerDfp


### -field UcmTypeCPartnerPoweredCableNoUfp


### -field UcmTypeCPartnerPoweredCableWithUfp


### -field UcmTypeCPartnerAudioAccessory


### -field UcmTypeCPartnerDebugAccessory




#### - UcmTypeCPartnerStateInvalid

The partner port state is invalid.


#### - UcmTypeCPartnerStateUfp

The partner is an Upstream Facing Port (UFP).


#### - UcmTypeCPartnerStateDfp

The partner is a Downstream Facing Port (DFP).


#### - UcmTypeCPartnerStatePoweredCableNoUfp

The partner is a powered cable that requires VConn, that currently does not have a UFP attached on the other end.


#### - UcmTypeCPartnerStatePoweredCableWithUfp

The partner is a powered and upstream facing.


#### - UcmTypeCPartnerStateAudioAccessory

The partner is used as an audio accessory.


#### - UcmTypeCPartnerStateDebugAccessory

The partner is a debug accessory.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt187928">UCM_CONNECTOR_TYPEC_ATTACH_PARAMS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt187915">UcmConnectorTypeCAttach</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCM_TYPEC_PARTNER enumeration%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

