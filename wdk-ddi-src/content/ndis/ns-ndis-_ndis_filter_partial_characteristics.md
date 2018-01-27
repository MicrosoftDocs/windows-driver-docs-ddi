---
UID: NS:ndis._NDIS_FILTER_PARTIAL_CHARACTERISTICS
title: _NDIS_FILTER_PARTIAL_CHARACTERISTICS
author: windows-driver-content
description: To specify optional entry points for a filter module, a filter driver initializes an NDIS_FILTER_PARTIAL_CHARACTERISTICS structure and passes it to the NdisSetOptionalHandlers function.
old-location: netvista\ndis_filter_partial_characteristics.htm
old-project: netvista
ms.assetid: 4a7f365c-a252-4d8e-bddf-684b3298db5c
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: *PNDIS_FILTER_PARTIAL_CHARACTERISTICS, netvista.ndis_filter_partial_characteristics, PNDIS_FILTER_PARTIAL_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], ndis/NDIS_FILTER_PARTIAL_CHARACTERISTICS, PNDIS_FILTER_PARTIAL_CHARACTERISTICS, ndis/PNDIS_FILTER_PARTIAL_CHARACTERISTICS, _NDIS_FILTER_PARTIAL_CHARACTERISTICS, NDIS_FILTER_PARTIAL_CHARACTERISTICS, NDIS_FILTER_PARTIAL_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], filter_structures_ref_34b4c497-9a4c-4d15-9d25-672a7580456b.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
req.irql: See Remarks section
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	ndis.h
apiname: 
-	NDIS_FILTER_PARTIAL_CHARACTERISTICS
product: Windows
targetos: Windows
req.typenames: NDIS_FILTER_PARTIAL_CHARACTERISTICS, *PNDIS_FILTER_PARTIAL_CHARACTERISTICS
---

# _NDIS_FILTER_PARTIAL_CHARACTERISTICS structure


## -description


To specify optional entry points for a filter module, a filter driver initializes an
  NDIS_FILTER_PARTIAL_CHARACTERISTICS structure and passes it to the 
  <mshelp:link keywords="netvista.ndissetoptionalhandlers" tabindex="0"><b>
  NdisSetOptionalHandlers</b></mshelp:link> function.


## -syntax


````
typedef struct _NDIS_FILTER_PARTIAL_CHARACTERISTICS {
  NDIS_OBJECT_HEADER                            Header;
  ULONG                                         Flags;
  FILTER_SEND_NET_BUFFER_LISTS_HANDLER          SendNetBufferListsHandler;
  FILTER_SEND_NET_BUFFER_LISTS_COMPLETE_HANDLER SendNetBufferListsCompleteHandler;
  FILTER_CANCEL_SEND_HANDLER                    CancelSendNetBufferListsHandler;
  FILTER_RECEIVE_NET_BUFFER_LISTS_HANDLER       ReceiveNetBufferListsHandler;
  FILTER_RETURN_NET_BUFFER_LISTS_HANDLER        ReturnNetBufferListsHandler;
} NDIS_FILTER_PARTIAL_CHARACTERISTICS, *PNDIS_FILTER_PARTIAL_CHARACTERISTICS;
````


## -struct-fields




### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     filter driver partial characteristics structure (NDIS_FILTER_PARTIAL_CHARACTERISTICS). Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_FILTER_PARTIAL_CHARACTERISTICS, the 
     <b>Revision</b> member to NDIS_FILTER_PARTIAL_CHARACTERISTICS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_FILTER_PARTIAL_CHARACTERISTICS_REVISION_1.


### -field Flags

Reserved for NDIS.


### -field SendNetBufferListsHandler

The entry point of the caller's 
     <mshelp:link keywords="netvista.filtersendnetbufferlists" tabindex="0"><i>
     FilterSendNetBufferLists</i></mshelp:link> function. To bypass this function, set this member to <b>NULL</b>.


### -field SendNetBufferListsCompleteHandler

The entry point of the caller's 
     <mshelp:link keywords="netvista.filtersendnetbufferlistscomplete" tabindex="0"><i>
     FilterSendNetBufferListsComplete</i></mshelp:link> function. To bypass this function, set this member to
     <b>NULL</b>.


### -field CancelSendNetBufferListsHandler

The entry point of the caller's 
     <mshelp:link keywords="netvista.filtercancelsendnetbufferlists" tabindex="0"><i>
     FilterCancelSendNetBufferLists</i></mshelp:link> function. To bypass this function, set this member to <b>NULL</b>.


### -field ReceiveNetBufferListsHandler

The entry point of the caller's 
     <mshelp:link keywords="netvista.filterreceivenetbufferlists" tabindex="0"><i>
     FilterReceiveNetBufferLists</i></mshelp:link> function. To bypass this function, set this member to <b>NULL</b>.


### -field ReturnNetBufferListsHandler

The entry point of the caller's 
     <mshelp:link keywords="netvista.filterreturnnetbufferlists" tabindex="0"><i>
     FilterReturnNetBufferLists</i></mshelp:link> function. To bypass this function, set this member to <b>NULL</b>.


## -remarks


This structure specifies optional 
    <i>FilterXxx</i> functions and other characteristics for a filter module. These characteristics override
    the default values that the driver set in the 
    <mshelp:link keywords="netvista.ndis_filter_driver_characteristics" tabindex="0"><b>
    NDIS_FILTER_DRIVER_CHARACTERISTICS</b></mshelp:link> structure that the driver passed to the 
    <mshelp:link keywords="netvista.ndisfregisterfilterdriver" tabindex="0"><b>
    NdisFRegisterFilterDriver</b></mshelp:link> function.



## -see-also

<mshelp:link keywords="netvista.filtersendnetbufferlistscomplete" tabindex="0"><i>
   FilterSendNetBufferListsComplete</i></mshelp:link>

<a href="..\ndis\nc-ndis-filter_send_net_buffer_lists.md">FilterSendNetBufferLists</a>

<a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a>

<a href="..\ndis\nf-ndis-ndisfregisterfilterdriver.md">NdisFRegisterFilterDriver</a>

<a href="..\ndis\nc-ndis-filter_return_net_buffer_lists.md">FilterReturnNetBufferLists</a>

<a href="..\ndis\nc-ndis-filter_receive_net_buffer_lists.md">FilterReceiveNetBufferLists</a>

<mshelp:link keywords="netvista.filtercancelsendnetbufferlists" tabindex="0"><i>
   FilterCancelSendNetBufferLists</i></mshelp:link>

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

<mshelp:link keywords="netvista.ndis_filter_driver_characteristics" tabindex="0"><b>
   NDIS_FILTER_DRIVER_CHARACTERISTICS</b></mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_FILTER_PARTIAL_CHARACTERISTICS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

