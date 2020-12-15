---
UID: NE:bthddi._INDICATION_CODE
title: _INDICATION_CODE (bthddi.h)
description: The INDICATION_CODE enumeration type indicates to a profile driver what type of L2CAP event has occurred.
old-location: bltooth\indication_code.htm
tech.root: bltooth
ms.date: 04/27/2018
keywords: ["INDICATION_CODE enumeration"]
ms.keywords: "*PINDICATION_CODE, INDICATION_CODE, INDICATION_CODE enumeration [Bluetooth Devices], IndicationAddReference, IndicationFreeExtraOptions, IndicationPairDevice, IndicationRecvPacket, IndicationReleaseReference, IndicationRemoteConfigRequest, IndicationRemoteConfigResponse, IndicationRemoteConnect, IndicationRemoteConnectLE, IndicationRemoteDisconnect, IndicationUnpairDevice, IndicationUnpersonalizeDevice, PINDICATION_CODE, PINDICATION_CODE enumeration pointer [Bluetooth Devices], _INDICATION_CODE, bltooth.indication_code, bth_enums_89c3fcea-8183-4227-b3fb-4e18c3612326.xml, bthddi/INDICATION_CODE, bthddi/IndicationAddReference, bthddi/IndicationFreeExtraOptions, bthddi/IndicationPairDevice, bthddi/IndicationRecvPacket, bthddi/IndicationReleaseReference, bthddi/IndicationRemoteConfigRequest, bthddi/IndicationRemoteConfigResponse, bthddi/IndicationRemoteConnect, bthddi/IndicationRemoteConnectLE, bthddi/IndicationRemoteDisconnect, bthddi/IndicationUnpairDevice, bthddi/IndicationUnpersonalizeDevice, bthddi/PINDICATION_CODE"
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
targetos: Windows
req.typenames: INDICATION_CODE, *PINDICATION_CODE
f1_keywords:
 - _INDICATION_CODE
 - bthddi/_INDICATION_CODE
 - PINDICATION_CODE
 - bthddi/PINDICATION_CODE
 - INDICATION_CODE
 - bthddi/INDICATION_CODE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - bthddi.h
api_name:
 - INDICATION_CODE
---

# _INDICATION_CODE enumeration


## -description

The INDICATION_CODE enumeration type indicates to a profile driver what type of L2CAP event has
  occurred.

## -enum-fields

### -field IndicationAddReference

Indicates to a profile driver to add a reference to its device object because it may be called at
     any time.

### -field IndicationReleaseReference

Indicates to a profile driver to release a reference to its device object and that it will no
     longer be called.

### -field IndicationRemoteConnect

Indicates to a server profile driver that a remote device is connecting to the PSM that the
     profile driver registered earlier. Profile drivers accept or reject this request by 
     <a href="/previous-versions/ff536657(v=vs.85)">building and sending</a> a 
     <a href="/previous-versions/ff536616(v=vs.85)">
     BRB_L2CA_OPEN_CHANNEL_RESPONSE</a> request. When this indication code is passed, the profile driver
     should use the parameters that are passed to it in the 
     <b>Connect</b> member of the 
     <a href="/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_indication_parameters">
     INDICATION_PARAMETERS</a> structure.

### -field IndicationRemoteDisconnect

Indicates to a registered profile driver that a remote device disconnecting from the local radio.
     When this indication code is passed, the profile driver should use the parameters that are passed to it
     in the 
     <b>Disconnect</b> member of the INDICATION_PARAMETERS structure.

### -field IndicationRemoteConfigRequest

Indicates to a client profile driver that a remote device is performing a configuration request.
     When this indication code is passed, the profile driver should use the parameters that are passed to it
     in the 
     <b>ConfigRequest</b> member of the INDICATION_PARAMETERS structure.

### -field IndicationRemoteConfigResponse

Indicates to a client profile driver that a remote device is responding to a configuration
     request. When this indication code is passed, the profile driver should use the parameters that are
     passed to it in the 
     <b>ConfigResponse</b> member of the INDICATION_PARAMETERS structure.

### -field IndicationFreeExtraOptions

Reserved for future use. Do not use.

### -field IndicationRecvPacket

Indicates to a registered profile driver that a packet has been received on the specified PSM. The
     profile driver can use this event to determine when it is necessary to issue a read
     BRB_L2CA_ACL_TRANSFTER BRB. Profile drivers that need to read from the remote device can also ignore
     this notification and keep a read BRB pending at all times. When this indication code is passed, the
     profile driver should use the parameters that are passed to it in the 
     <b>RecvPacket</b> member of the 
     <a href="/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_indication_parameters">
     INDICATION_PARAMETERS</a> structure.

### -field IndicationPairDevice

Indicates to a registered driver that the local radio has bonded to a specific remote
     radio.

### -field IndicationUnpairDevice

Indicates to a registered driver that the local radio is no longer bonded to a specific remote
     radio.

### -field IndicationUnpersonalizeDevice

Indicates to a registered driver that the specified remote radio has been removed from the list of
     personal devices.

### -field IndicationRemoteConnectLE

Indicates to a server profile driver that a low energy (LE) remote device is connecting to the PSM that the
     profile driver registered earlier. Profile drivers accept or reject this request by 
     <a href="/previous-versions/ff536657(v=vs.85)">building and sending</a> a 
     <a href="/previous-versions/ff536616(v=vs.85)">
     BRB_L2CA_OPEN_CHANNEL_RESPONSE</a> request. When this indication code is passed, the profile driver
     should use the parameters that are passed to it in the 
     <b>Connect</b> member of the 
     <a href="/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_indication_parameters">
     INDICATION_PARAMETERS</a> structure. This value is present in Windows 8 and later versions of Windows.

## -remarks

A value from this enumeration is passed to a profile driver's 
    <a href="/windows-hardware/drivers/ddi/bthddi/nc-bthddi-pfnbthport_indication_callback">L2CAP Callback Function</a> to notify
    it of an event.

## -see-also

<a href="/previous-versions/ff536618(v=vs.85)">BRB_L2CA_REGISTER_SERVER</a>



<a href="/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_indication_parameters">INDICATION_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/bthioctl/ni-bthioctl-ioctl_internal_bth_submit_brb">IOCTL_INTERNAL_BTH_SUBMIT_BRB</a>



<a href="/windows-hardware/drivers/ddi/bthddi/nc-bthddi-pfnbthport_indication_callback">L2CAP Callback Function</a>
