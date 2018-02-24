---
UID: NS:bthioctl._BTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST
title: "_BTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST"
author: windows-driver-content
description: The BTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST structure contains information pertinent to a combined SDP service and attribute search. This structure is passed as the input buffer to the IOCTL_BTH_SDP_SERVICE_ATTRIBUTE_SEARCH IOCTL.
old-location: bltooth\bth_sdp_service_attribute_search_request.htm
old-project: bltooth
ms.assetid: 28255569-57ce-44b7-9d53-9e8797b914c5
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: PBTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST structure pointer [Bluetooth Devices], PBTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST, BTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST, bthioctl/PBTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST, _BTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST, BTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST structure [Bluetooth Devices], bltooth.bth_sdp_service_attribute_search_request, *PBTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST, bthioctl/BTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST, bth_structs_0e06cbd7-0737-4786-bdc3-c9c1e980e3a3.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: "<= PASSIVE_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	bthioctl.h
apiname:
-	BTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST
product: Windows
targetos: Windows
req.typenames: "*PBTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST, BTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST"
---

# _BTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST structure


## -description


The BTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST structure contains information pertinent to a combined
  SDP service and attribute search. This structure is passed as the input buffer to the 
  <a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_service_attribute_search.md">
  IOCTL_BTH_SDP_SERVICE_ATTRIBUTE_SEARCH</a> IOCTL.


## -syntax


````
typedef struct _BTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST {
  HANDLE_SDP        hConnection;
  ULONG             searchFlags;
  SdpQueryUuid      uuids[MAX_UUIDS_IN_QUERY];
  SdpAttributeRange range[1];
} BTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST, *PBTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST;
````


## -struct-fields




### -field HANDLE_SDP_FIELD_NAME

 


### -field searchFlags



#### 


### -field uuids

An array of UUIDs that represent the services for which to query. Each entry can be a 2-byte,
     4-byte, or 16-byte type, and there can be a maximum of 12 entries. The array can be terminated before
     all 12 entries are used if a UUID entry contains all zeros.


### -field range

A variable-length array of 
     <a href="http://go.microsoft.com/fwlink/p/?linkid=50714">SdpAttributeRange</a> structures that
     contains the range of SDP attributes for which to search.


#### - hConnection

A handle to the remote SDP server that is returned by the 
     <a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_connect.md">IOCTL_BTH_SDP_CONNECT</a> IOCTL.


## -remarks



The Bluetooth driver stack determines the number of array items in the 
    <b>range</b> member by examining the length of IOCTL_BTH_SDP_SERVICE_ATTRIBUTE_SEARCH input buffer.
    Because of this, the
    <b>Parameters.DeviceIoControl.InputBufferLength</b> member passed when the IOCTL is called must be
    calculated exactly.




## -see-also

<a href="http://go.microsoft.com/fwlink/p/?linkid=50714">SdpAttributeRange</a>



<a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_connect.md">IOCTL_BTH_SDP_CONNECT</a>



<a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_service_attribute_search.md">
   IOCTL_BTH_SDP_SERVICE_ATTRIBUTE_SEARCH</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20BTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

