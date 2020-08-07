---
UID: NS:bthioctl._BTH_SDP_DISCONNECT
title: _BTH_SDP_DISCONNECT (bthioctl.h)
description: The BTH_SDP_DISCONNECT structure contains input information about a connection handle to the remote SDP connection to terminate. This structure is passed as the input buffer of IOCTL_BTH_SDP_DISCONNECT.
old-location: bltooth\bth_sdp_disconnect.htm
tech.root: bltooth
ms.assetid: d0466569-7c9d-40d2-8794-b1d877a52458
ms.date: 04/27/2018
keywords: ["BTH_SDP_DISCONNECT structure"]
ms.keywords: "*PBTH_SDP_DISCONNECT, BTH_SDP_DISCONNECT, BTH_SDP_DISCONNECT structure [Bluetooth Devices], PBTH_SDP_DISCONNECT, PBTH_SDP_DISCONNECT structure pointer [Bluetooth Devices], _BTH_SDP_DISCONNECT, bltooth.bth_sdp_disconnect, bth_structs_049df802-3bad-49b0-b80e-f3b0a1579b72.xml, bthioctl/BTH_SDP_DISCONNECT, bthioctl/PBTH_SDP_DISCONNECT"
f1_keywords:
 - "bthioctl/BTH_SDP_DISCONNECT"
 - "BTH_SDP_DISCONNECT"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- bthioctl.h
api_name:
- BTH_SDP_DISCONNECT
targetos: Windows
req.typenames: BTH_SDP_DISCONNECT, *PBTH_SDP_DISCONNECT
---

# _BTH_SDP_DISCONNECT structure


## -description


The BTH_SDP_DISCONNECT structure contains input information about a connection handle to the remote
  SDP connection to terminate. This structure is passed as the input buffer of 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ni-bthioctl-ioctl_bth_sdp_disconnect">IOCTL_BTH_SDP_DISCONNECT</a>.


## -struct-fields




### -field HANDLE_SDP_FIELD_NAME

 




#### - hConnection

A handle for the SDP connection on the remote server to terminate. This should be a value returned
     in the 
     <b>hConnection</b> member of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_sdp_connect">BTH_SDP_CONNECT</a> structure of a previous call
     to 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ni-bthioctl-ioctl_bth_sdp_connect">IOCTL_BTH_SDP_CONNECT</a>.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_sdp_connect">BTH_SDP_CONNECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ni-bthioctl-ioctl_bth_sdp_connect">IOCTL_BTH_SDP_CONNECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ni-bthioctl-ioctl_bth_sdp_disconnect">IOCTL_BTH_SDP_DISCONNECT</a>
 

 

