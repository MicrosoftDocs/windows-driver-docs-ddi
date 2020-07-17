---
UID: NE:ntddndis._NDIS_RECEIVE_FILTER_TEST
title: _NDIS_RECEIVE_FILTER_TEST (ntddndis.h)
description: The NDIS_RECEIVE_FILTER_TEST enumeration identifies the type of test that the receive filter performs.
old-location: netvista\ndis_receive_filter_test.htm
tech.root: netvista
ms.assetid: 064d8335-3ebf-4bc2-901e-10ce46bf7732
ms.date: 05/02/2018
keywords: ["_NDIS_RECEIVE_FILTER_TEST enumeration"]
ms.keywords: "*PNDIS_RECEIVE_FILTER_TEST, NDIS_RECEIVE_FILTER_TEST, NDIS_RECEIVE_FILTER_TEST enumeration [Network Drivers Starting with Windows Vista], NdisReceiveFilterTestEqual, NdisReceiveFilterTestMaskEqual, NdisReceiveFilterTestMaximum, NdisReceiveFilterTestNotEqual, NdisReceiveFilterTestUndefined, PNDIS_RECEIVE_FILTER_TEST, PNDIS_RECEIVE_FILTER_TEST enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_RECEIVE_FILTER_TEST, netvista.ndis_receive_filter_test, ntddndis/NDIS_RECEIVE_FILTER_TEST, ntddndis/NdisReceiveFilterTestEqual, ntddndis/NdisReceiveFilterTestMaskEqual, ntddndis/NdisReceiveFilterTestMaximum, ntddndis/NdisReceiveFilterTestNotEqual, ntddndis/NdisReceiveFilterTestUndefined, ntddndis/PNDIS_RECEIVE_FILTER_TEST, virtual_machine_queue_ref_16206d46-2048-429b-b7cf-aa5f5d099ae1.xml"
f1_keywords:
 - "ntddndis/NDIS_RECEIVE_FILTER_TEST"
 - "NDIS_RECEIVE_FILTER_TEST"
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
- Ntddndis.h
api_name:
- NDIS_RECEIVE_FILTER_TEST
product:
- Windows
targetos: Windows
req.typenames: NDIS_RECEIVE_FILTER_TEST, *PNDIS_RECEIVE_FILTER_TEST
---

# _NDIS_RECEIVE_FILTER_TEST enumeration


## -description


The <b>NDIS_RECEIVE_FILTER_TEST</b> enumeration identifies the type of test that the receive filter
  performs.


## -enum-fields




### -field NdisReceiveFilterTestUndefined

The type of test is not specified.


### -field NdisReceiveFilterTestEqual

The network adapter tests the selected header field to determine whether it is equal to a specific
     value.


### -field NdisReceiveFilterTestMaskEqual

The network adapter supports masking (that is, a bitwise AND) of the selected header field to
     determine whether the result is equal to a specific value.


### -field NdisReceiveFilterTestNotEqual

The network adapter tests the selected header field to determine whether it is not equal to a specific
     value.


### -field NdisReceiveFilterTestMaximum

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -remarks



The NDIS_RECEIVE_FILTER_TEST enumeration is used in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_filter_field_parameters">
    NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_filter_field_parameters">
   NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</a>
 

 

