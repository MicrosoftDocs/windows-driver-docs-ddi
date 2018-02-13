---
UID: NE:ndis.NDIS_PD_COUNTER_TYPE
title: NDIS_PD_COUNTER_TYPE
author: windows-driver-content
description: The NDIS_PD_COUNTER_TYPE enumeration defines types of PacketDirect Provider Interface (PDPI) counters. Its enumeration values are used in the Type member of the NDIS_PD_COUNTER_PARAMETERS structure.
old-location: netvista\ndis_pd_counter_type.htm
old-project: netvista
ms.assetid: 36DA5A61-2DA4-4CD1-8BA5-74444DC002F0
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NDIS_PD_COUNTER_TYPE, PDCounterTypeReceiveFilter, PDCounterTypeUnknown, PDCounterTypeTransmitQueue, ndis/PDCounterTypeTransmitQueue, ndis/NDIS_PD_COUNTER_TYPE, netvista.ndis_pd_counter_type, ndis/PDCounterTypeMax, ndis/PDCounterTypeReceiveFilter, NDIS_PD_COUNTER_TYPE enumeration [Network Drivers Starting with Windows Vista], ndis/PDCounterTypeReceiveQueue, PDCounterTypeReceiveQueue, PDCounterTypeMax, ndis/PDCounterTypeUnknown
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ndis.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	Ndis.h
apiname:
-	NDIS_PD_COUNTER_TYPE
product: Windows
targetos: Windows
req.typenames: NDIS_PD_COUNTER_TYPE
---

# NDIS_PD_COUNTER_TYPE enumeration


## -description


The <b>NDIS_PD_COUNTER_TYPE</b> enumeration defines types of PacketDirect Provider Interface (PDPI)  counters. Its enumeration values are used in the <b>Type</b> member of the <a href="..\ndis\ns-ndis-_ndis_pd_counter_parameters.md">NDIS_PD_COUNTER_PARAMETERS</a> structure.


## -syntax


````
typedef enum _NDIS_PD_COUNTER_TYPE { 
  PDCounterTypeUnknown,
  PDCounterTypeReceiveQueue,
  PDCounterTypeTransmitQueue,
  PDCounterTypeReceiveFilter,
  PDCounterTypeMax
} NDIS_PD_COUNTER_TYPE;
````


## -enum-fields




### -field PDCounterTypeUnknown

The counter type is not known.


### -field PDCounterTypeReceiveQueue

The counter is a receive queue counter.


### -field PDCounterTypeTransmitQueue

The counter is a transmit queue counter.


### -field PDCounterTypeReceiveFilter

The counter is a receive filter counter.


### -field PDCounterTypeMax

The maximum value for this enumeration. This value might change in future versions of NDIS header files and binaries.




## -see-also

<a href="..\ndis\ns-ndis-_ndis_pd_counter_parameters.md">NDIS_PD_COUNTER_PARAMETERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PD_COUNTER_TYPE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

