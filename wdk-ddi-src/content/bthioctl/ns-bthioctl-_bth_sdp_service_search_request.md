---
UID: NS:bthioctl._BTH_SDP_SERVICE_SEARCH_REQUEST
title: _BTH_SDP_SERVICE_SEARCH_REQUEST
author: windows-driver-content
description: The BTH_SDP_SERVICE_SEARCH_REQUEST structure contains information pertinent to an SDP service search.
old-location: bltooth\bth_sdp_service_search_request.htm
old-project: bltooth
ms.assetid: d1ef833e-8350-499c-9a3d-408d900c9245
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: BTH_SDP_SERVICE_SEARCH_REQUEST, PBTH_SDP_SERVICE_SEARCH_REQUEST, bth_structs_c625eff6-6ec7-49a4-a141-778ebda2d563.xml, *PBTH_SDP_SERVICE_SEARCH_REQUEST, bthioctl/PBTH_SDP_SERVICE_SEARCH_REQUEST, _BTH_SDP_SERVICE_SEARCH_REQUEST, BTH_SDP_SERVICE_SEARCH_REQUEST structure [Bluetooth Devices], PBTH_SDP_SERVICE_SEARCH_REQUEST structure pointer [Bluetooth Devices], bltooth.bth_sdp_service_search_request, bthioctl/BTH_SDP_SERVICE_SEARCH_REQUEST
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	bthioctl.h
apiname: 
-	BTH_SDP_SERVICE_SEARCH_REQUEST
product: Windows
targetos: Windows
req.typenames: BTH_SDP_SERVICE_SEARCH_REQUEST, *PBTH_SDP_SERVICE_SEARCH_REQUEST
---

# _BTH_SDP_SERVICE_SEARCH_REQUEST structure


## -description


The BTH_SDP_SERVICE_SEARCH_REQUEST structure contains information pertinent to an SDP service
  search.


## -syntax


````
typedef struct _BTH_SDP_SERVICE_SEARCH_REQUEST {
  HANDLE_SDP   hConnection;
  SdpQueryUuid uuids[MAX_UUIDS_IN_QUERY];
} BTH_SDP_SERVICE_SEARCH_REQUEST, *PBTH_SDP_SERVICE_SEARCH_REQUEST;
````


## -struct-fields




### -field HANDLE_SDP_FIELD_NAME

 


### -field uuids

An array of UUIDs that represent the services for which to query. Each entry can be a 2-byte,
     4-byte, or 16-byte type, and there can be a maximum of 12 entries. The array can be terminated before
     all 12 entries are used if a UUID entry contains all zeros.


#### - hConnection

A handle to the remote SDP server that is returned by the 
     <a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_connect.md">IOCTL_BTH_SDP_CONNECT</a> IOCTL.


## -remarks


This structure is passed as the input buffer to the 
    <mshelp:link keywords="bltooth.ioctl_bth_sdp_service_search" tabindex="0"><b>
    IOCTL_BTH_SDP_SERVICE_SEARCH</b></mshelp:link> IOCTL.



## -see-also

<a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_service_search.md">IOCTL_BTH_SDP_SERVICE_SEARCH</a>

<a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_connect.md">IOCTL_BTH_SDP_CONNECT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20BTH_SDP_SERVICE_SEARCH_REQUEST structure%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

