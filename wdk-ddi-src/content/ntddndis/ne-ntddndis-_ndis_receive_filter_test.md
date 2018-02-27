---
UID: NE:ntddndis._NDIS_RECEIVE_FILTER_TEST
title: "_NDIS_RECEIVE_FILTER_TEST"
author: windows-driver-content
description: The NDIS_RECEIVE_FILTER_TEST enumeration identifies the type of test that the receive filter performs.
old-location: netvista\ndis_receive_filter_test.htm
old-project: netvista
ms.assetid: 064d8335-3ebf-4bc2-901e-10ce46bf7732
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PNDIS_RECEIVE_FILTER_TEST, NDIS_RECEIVE_FILTER_TEST, NDIS_RECEIVE_FILTER_TEST enumeration [Network Drivers Starting with Windows Vista], NdisReceiveFilterTestEqual, NdisReceiveFilterTestMaskEqual, NdisReceiveFilterTestMaximum, NdisReceiveFilterTestNotEqual, NdisReceiveFilterTestUndefined, PNDIS_RECEIVE_FILTER_TEST, PNDIS_RECEIVE_FILTER_TEST enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_RECEIVE_FILTER_TEST, netvista.ndis_receive_filter_test, ntddndis/NDIS_RECEIVE_FILTER_TEST, ntddndis/NdisReceiveFilterTestEqual, ntddndis/NdisReceiveFilterTestMaskEqual, ntddndis/NdisReceiveFilterTestMaximum, ntddndis/NdisReceiveFilterTestNotEqual, ntddndis/NdisReceiveFilterTestUndefined, ntddndis/PNDIS_RECEIVE_FILTER_TEST, virtual_machine_queue_ref_16206d46-2048-429b-b7cf-aa5f5d099ae1.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddndis.h
apiname:
-	NDIS_RECEIVE_FILTER_TEST
product: Windows
targetos: Windows
req.typenames: NDIS_RECEIVE_FILTER_TEST, *PNDIS_RECEIVE_FILTER_TEST
---

# _NDIS_RECEIVE_FILTER_TEST enumeration


## -description


The <b>NDIS_RECEIVE_FILTER_TEST</b> enumeration identifies the type of test that the receive filter
  performs.


## -syntax


````
typedef enum _NDIS_RECEIVE_FILTER_TEST { 
  NdisReceiveFilterTestUndefined,
  NdisReceiveFilterTestEqual,
  NdisReceiveFilterTestMaskEqual,
  NdisReceiveFilterTestNotEqual,
  NdisReceiveFilterTestMaximum
} NDIS_RECEIVE_FILTER_TEST, *PNDIS_RECEIVE_FILTER_TEST;
````


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
    <a href="..\ntddndis\ns-ntddndis-_ndis_receive_filter_field_parameters.md">
    NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</a> structure.




## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_receive_filter_field_parameters.md">
   NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_RECEIVE_FILTER_TEST enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

