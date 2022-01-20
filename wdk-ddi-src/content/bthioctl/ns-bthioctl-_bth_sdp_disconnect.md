---
UID: NS:bthioctl._BTH_SDP_DISCONNECT
title: _BTH_SDP_DISCONNECT (bthioctl.h)
description: The BTH_SDP_DISCONNECT structure contains input information about a connection handle to the remote SDP connection to terminate. This structure is passed as the input buffer of IOCTL_BTH_SDP_DISCONNECT.
old-location: bltooth\bth_sdp_disconnect.htm
tech.root: bltooth
ms.date: 12/01/2021
keywords: ["BTH_SDP_DISCONNECT structure"]
ms.keywords: "*PBTH_SDP_DISCONNECT, BTH_SDP_DISCONNECT, BTH_SDP_DISCONNECT structure [Bluetooth Devices], PBTH_SDP_DISCONNECT, PBTH_SDP_DISCONNECT structure pointer [Bluetooth Devices], _BTH_SDP_DISCONNECT, bltooth.bth_sdp_disconnect, bth_structs_049df802-3bad-49b0-b80e-f3b0a1579b72.xml, bthioctl/BTH_SDP_DISCONNECT, bthioctl/PBTH_SDP_DISCONNECT"
req.header: bthioctl.h
req.include-header: Bthioctl.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.typenames: BTH_SDP_DISCONNECT, *PBTH_SDP_DISCONNECT
f1_keywords:
 - _BTH_SDP_DISCONNECT
 - bthioctl/_BTH_SDP_DISCONNECT
 - PBTH_SDP_DISCONNECT
 - bthioctl/PBTH_SDP_DISCONNECT
 - BTH_SDP_DISCONNECT
 - bthioctl/BTH_SDP_DISCONNECT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - bthioctl.h
api_name:
 - _BTH_SDP_DISCONNECT
 - PBTH_SDP_DISCONNECT
 - BTH_SDP_DISCONNECT
---

# _BTH_SDP_DISCONNECT structure

## -description

The BTH_SDP_DISCONNECT structure contains input information about a connection handle to the remote SDP connection to terminate. This structure is passed as the input buffer of [IOCTL_BTH_SDP_DISCONNECT](./ni-bthioctl-ioctl_bth_sdp_disconnect.md).

## -struct-fields

### -field HANDLE_SDP_FIELD_NAME

When the connect request returns, this specifies the handle to the SDP connection to the remote server.

## -see-also

- [BTH_SDP_CONNECT](./ns-bthioctl-_bth_sdp_connect.md)
- [IOCTL_BTH_SDP_CONNECT](./ni-bthioctl-ioctl_bth_sdp_connect.md)
- [IOCTL_BTH_SDP_DISCONNECT](./ni-bthioctl-ioctl_bth_sdp_disconnect.md)