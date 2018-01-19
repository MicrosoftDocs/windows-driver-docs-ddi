---
UID: NS:bthioctl._BTH_SDP_ATTRIBUTE_SEARCH_REQUEST
title: _BTH_SDP_ATTRIBUTE_SEARCH_REQUEST
author: windows-driver-content
description: The BTH_SDP_ATTRIBUTE_SEARCH_REQUEST structure contains information pertinent to an SDP attribute search.
old-location: bltooth\bth_sdp_attribute_search_request.htm
old-project: bltooth
ms.assetid: 46198c94-df83-42bb-ad3e-181f252ccd99
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: _BTH_SDP_ATTRIBUTE_SEARCH_REQUEST, *PBTH_SDP_ATTRIBUTE_SEARCH_REQUEST, BTH_SDP_ATTRIBUTE_SEARCH_REQUEST
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bthioctl.h
req.include-header: Bthioctl.h
req.target-type: Windows
req.target-min-winverclnt: Versions: Supported in Windows Vista, and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BTH_SDP_ATTRIBUTE_SEARCH_REQUEST
req.alt-loc: bthioctl.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= PASSIVE_LEVEL
req.typenames: *PBTH_SDP_ATTRIBUTE_SEARCH_REQUEST, BTH_SDP_ATTRIBUTE_SEARCH_REQUEST
---

# _BTH_SDP_ATTRIBUTE_SEARCH_REQUEST structure



## -description
The BTH_SDP_ATTRIBUTE_SEARCH_REQUEST structure contains information pertinent to an SDP attribute
  search.



## -syntax

````
typedef struct _BTH_SDP_ATTRIBUTE_SEARCH_REQUEST {
  HANDLE_SDP        hConnection;
  ULONG             searchFlags;
  ULONG             recordHandle;
  SdpAttributeRange range[1];
} BTH_SDP_ATTRIBUTE_SEARCH_REQUEST, *PBTH_SDP_ATTRIBUTE_SEARCH_REQUEST;
````


## -struct-fields

### -field hConnection

A handle to the remote SDP server that is returned by the 
     <a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_connect.md">IOCTL_BTH_SDP_CONNECT</a> IOCTL.


### -field searchFlags

<dl>

### -field previous BTH_SDP_SERVICE_SEARCH_RESPONSE.


### -field recordHandle

The record handle that is returned by the remote SDP server from a previous call to the 
     <a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_service_search.md">
     IOCTL_BTH_SDP_SERVICE_SEARCH</a> IOCTL.


### -field range

A variable-length array of structures of type 
     <a href="http://go.microsoft.com/fwlink/p/?linkid=50714">SdpAttributeRange</a> that contains the
     range of SDP attributes for which to search. The range array must be in ascending numeric order.


## -remarks
This structure is passed as the input buffer to the 
    <a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_attribute_search.md">
    IOCTL_BTH_SDP_ATTRIBUTE_SEARCH</a> IOCTL.

The Bluetooth driver stack determines the number of array items in the 
    <b>range</b> member by examining the length of the IOCTL_BTH_SDP_ATTRIBUTE_SEARCH input buffer. Because of
    this, you must calculate the exact value of the
    <b>Parameters.DeviceIoControl.InputBufferLength</b> member that is passed when
    IOCTL_BTH_SDP_SERVICE_SEARCH is called.


## -see-also
<dl>
<dt>
<a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_connect.md">IOCTL_BTH_SDP_CONNECT</a>
</dt>
<dt>
<a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_service_search.md">IOCTL_BTH_SDP_SERVICE_SEARCH</a>
</dt>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=50714">SdpAttributeRange</a></dt>
<dt>
<a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_attribute_search.md">IOCTL_BTH_SDP_ATTRIBUTE_SEARCH</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20BTH_SDP_ATTRIBUTE_SEARCH_REQUEST structure%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

