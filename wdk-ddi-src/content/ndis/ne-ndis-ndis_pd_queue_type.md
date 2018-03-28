---
UID: NE:ndis.NDIS_PD_QUEUE_TYPE
title: NDIS_PD_QUEUE_TYPE
author: windows-driver-content
description: The NDIS_PD_QUEUE_TYPE enumeration defines types of PacketDirect Provider Interface (PDPI) queues. Its enumeration values are used in the QueueType member of the NDIS_PD_QUEUE_PARAMETERS structure.
old-location: netvista\ndis_pd_queue_type.htm
old-project: netvista
ms.assetid: 4536B3AB-6170-4819-975A-47D9A6223EAE
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NDIS_PD_QUEUE_TYPE, NDIS_PD_QUEUE_TYPE enumeration [Network Drivers Starting with Windows Vista], PDQueueTypeMax, PDQueueTypeReceive, PDQueueTypeTransmit, PDQueueTypeUnknown, ndis/NDIS_PD_QUEUE_TYPE, ndis/PDQueueTypeMax, ndis/PDQueueTypeReceive, ndis/PDQueueTypeTransmit, ndis/PDQueueTypeUnknown, netvista.ndis_pd_queue_type
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ndis.h
api_name:
-	NDIS_PD_QUEUE_TYPE
product: Windows
targetos: Windows
req.typenames: NDIS_PD_QUEUE_TYPE
---

# NDIS_PD_QUEUE_TYPE enumeration


## -description


The <b>NDIS_PD_QUEUE_TYPE</b> enumeration defines types of PacketDirect Provider Interface (PDPI)  queues. Its enumeration values are used in the <b>QueueType</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn931846">NDIS_PD_QUEUE_PARAMETERS</a> structure.


## -enum-fields




### -field PDQueueTypeUnknown

The queue type is not known.


### -field PDQueueTypeReceive

The queue is a receive queue.


### -field PDQueueTypeTransmit

The queue is a transmit queue.


### -field PDQueueTypeMax

The maximum value for this enumeration. This value might change in future versions of NDIS header files and binaries.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn931846">NDIS_PD_QUEUE_PARAMETERS</a>



<a href="https://msdn.microsoft.com/E9091C69-0E21-40CC-B3D3-1F770ABA0D47">NdisPDAllocateQueue</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PD_QUEUE_TYPE enumeration%20 RELEASE:%20(3/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

