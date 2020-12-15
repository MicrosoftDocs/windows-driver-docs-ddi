---
UID: NS:bthioctl._BTH_SDP_ATTRIBUTE_SEARCH_REQUEST
title: _BTH_SDP_ATTRIBUTE_SEARCH_REQUEST (bthioctl.h)
description: The BTH_SDP_ATTRIBUTE_SEARCH_REQUEST structure contains information pertinent to an SDP attribute search.
old-location: bltooth\bth_sdp_attribute_search_request.htm
tech.root: bltooth
ms.date: 04/27/2018
keywords: ["BTH_SDP_ATTRIBUTE_SEARCH_REQUEST structure"]
ms.keywords: "*PBTH_SDP_ATTRIBUTE_SEARCH_REQUEST, BTH_SDP_ATTRIBUTE_SEARCH_REQUEST, BTH_SDP_ATTRIBUTE_SEARCH_REQUEST structure [Bluetooth Devices], PBTH_SDP_ATTRIBUTE_SEARCH_REQUEST, PBTH_SDP_ATTRIBUTE_SEARCH_REQUEST structure pointer [Bluetooth Devices], _BTH_SDP_ATTRIBUTE_SEARCH_REQUEST, bltooth.bth_sdp_attribute_search_request, bth_structs_7856642e-a720-490e-9240-d61ac6f257b4.xml, bthioctl/BTH_SDP_ATTRIBUTE_SEARCH_REQUEST, bthioctl/PBTH_SDP_ATTRIBUTE_SEARCH_REQUEST"
req.header: bthioctl.h
req.include-header: Bthioctl.h
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
req.typenames: BTH_SDP_ATTRIBUTE_SEARCH_REQUEST, *PBTH_SDP_ATTRIBUTE_SEARCH_REQUEST
f1_keywords:
 - _BTH_SDP_ATTRIBUTE_SEARCH_REQUEST
 - bthioctl/_BTH_SDP_ATTRIBUTE_SEARCH_REQUEST
 - PBTH_SDP_ATTRIBUTE_SEARCH_REQUEST
 - bthioctl/PBTH_SDP_ATTRIBUTE_SEARCH_REQUEST
 - BTH_SDP_ATTRIBUTE_SEARCH_REQUEST
 - bthioctl/BTH_SDP_ATTRIBUTE_SEARCH_REQUEST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - bthioctl.h
api_name:
 - BTH_SDP_ATTRIBUTE_SEARCH_REQUEST
---

# _BTH_SDP_ATTRIBUTE_SEARCH_REQUEST structure


## -description

The BTH_SDP_ATTRIBUTE_SEARCH_REQUEST structure contains information pertinent to an SDP attribute
  search.

## -struct-fields

### -field HANDLE_SDP_FIELD_NAME

### -field searchFlags

#### 



#####

### -field recordHandle

The record handle that is returned by the remote SDP server from a previous call to the 
     <a href="/windows-hardware/drivers/ddi/bthioctl/ni-bthioctl-ioctl_bth_sdp_service_search">
     IOCTL_BTH_SDP_SERVICE_SEARCH</a> IOCTL.

### -field range

A variable-length array of structures of type 
     <a href="/windows/win32/api/bthsdpdef/ns-bthsdpdef-sdpattributerange">SdpAttributeRange</a> that contains the
     range of SDP attributes for which to search. The range array must be in ascending numeric order.


#### - hConnection

A handle to the remote SDP server that is returned by the 
     <a href="/windows-hardware/drivers/ddi/bthioctl/ni-bthioctl-ioctl_bth_sdp_connect">IOCTL_BTH_SDP_CONNECT</a> IOCTL.

## -remarks

This structure is passed as the input buffer to the 
    <a href="/windows-hardware/drivers/ddi/bthioctl/ni-bthioctl-ioctl_bth_sdp_attribute_search">
    IOCTL_BTH_SDP_ATTRIBUTE_SEARCH</a> IOCTL.

The Bluetooth driver stack determines the number of array items in the 
    <b>range</b> member by examining the length of the IOCTL_BTH_SDP_ATTRIBUTE_SEARCH input buffer. Because of
    this, you must calculate the exact value of the
    <b>Parameters.DeviceIoControl.InputBufferLength</b> member that is passed when
    IOCTL_BTH_SDP_SERVICE_SEARCH is called.

## -see-also

<a href="/windows-hardware/drivers/ddi/bthioctl/ni-bthioctl-ioctl_bth_sdp_attribute_search">IOCTL_BTH_SDP_ATTRIBUTE_SEARCH</a>



<a href="/windows-hardware/drivers/ddi/bthioctl/ni-bthioctl-ioctl_bth_sdp_connect">IOCTL_BTH_SDP_CONNECT</a>



<a href="/windows-hardware/drivers/ddi/bthioctl/ni-bthioctl-ioctl_bth_sdp_service_search">IOCTL_BTH_SDP_SERVICE_SEARCH</a>



<a href="/windows/win32/api/bthsdpdef/ns-bthsdpdef-sdpattributerange">SdpAttributeRange</a>
