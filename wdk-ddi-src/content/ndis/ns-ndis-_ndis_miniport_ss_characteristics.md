---
UID: NS:ndis._NDIS_MINIPORT_SS_CHARACTERISTICS
title: "_NDIS_MINIPORT_SS_CHARACTERISTICS"
author: windows-driver-content
description: The NDIS_MINIPORT_SS_CHARACTERISTICS structure specifies the pointers to a miniport driver's NDIS selective suspend handler functions. These functions are called by NDIS to issue idle notifications to the driver during a selective suspend operation.
old-location: netvista\ndis_miniport_ss_characteristics.htm
old-project: netvista
ms.assetid: 325E5717-6B84-45AE-85D4-BA1839DB76A2
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PNDIS_MINIPORT_SS_CHARACTERISTICS, NDIS_MINIPORT_SS_CHARACTERISTICS, NDIS_MINIPORT_SS_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNDIS_MINIPORT_SS_CHARACTERISTICS, PNDIS_MINIPORT_SS_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_MINIPORT_SS_CHARACTERISTICS, ndis/NDIS_MINIPORT_SS_CHARACTERISTICS, ndis/PNDIS_MINIPORT_SS_CHARACTERISTICS, netvista.ndis_miniport_ss_characteristics"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ndis.h
api_name:
-	NDIS_MINIPORT_SS_CHARACTERISTICS
product: Windows
targetos: Windows
req.typenames: NDIS_MINIPORT_SS_CHARACTERISTICS, *PNDIS_MINIPORT_SS_CHARACTERISTICS
---

# _NDIS_MINIPORT_SS_CHARACTERISTICS structure


## -description



The <b>NDIS_MINIPORT_SS_CHARACTERISTICS</b> structure specifies the pointers to a miniport driver's NDIS selective suspend handler functions. These functions are called by NDIS to issue idle notifications to the driver during a selective suspend operation.




## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_MINIPORT_SS_CHARACTERISTICS</b> structure. This member is formatted as an <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_MINIPORT_SS_CHARACTERISTICS. To specify the version of the <b>NDIS_MINIPORT_SS_CHARACTERISTICS</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_MINIPORT_SS_CHARACTERISTICS_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_MINIPORT_SS_CHARACTERISTICS_REVISION_1.


### -field Flags

 A <b>ULONG</b> value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.


### -field IdleNotificationHandler

A pointer to the miniport driver's <a href="https://msdn.microsoft.com/D679DEF0-1229-4731-8024-4DEDAE5B0185">MiniportIdleNotification</a> function.


### -field CancelIdleNotificationHandler

A pointer to the miniport driver's <a href="https://msdn.microsoft.com/9965E4EA-10E3-4240-9E4F-D3B49B8F9593">MiniportCancelIdleNotification</a> function.


## -remarks



To register the handler functions for NDIS selective suspend, the miniport driver follows these steps when its <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570269">MiniportSetOptions</a> function is called:

<ol>
<li>
The miniport driver initializes an <b>NDIS_MINIPORT_SS_CHARACTERISTICS</b> structure with pointers to the handler functions.

</li>
<li>
The miniport driver  then calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a> and sets the <i>OptionalHandlers</i> parameter to a pointer to the <b>NDIS_MINIPORT_SS_CHARACTERISTICS</b> structure.

</li>
</ol>
For more information on how to handle idle notifications for NDIS selective suspend, see <a href="https://msdn.microsoft.com/958A2588-A847-4699-9906-95FB47CA1CDC">NDIS Selective Suspend Idle Notifications</a>.




## -see-also




<b></b>



<a href="https://msdn.microsoft.com/9965E4EA-10E3-4240-9E4F-D3B49B8F9593">MiniportCancelIdleNotification</a>



<a href="https://msdn.microsoft.com/D679DEF0-1229-4731-8024-4DEDAE5B0185">MiniportIdleNotification</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570269">MiniportSetOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_MINIPORT_SS_CHARACTERISTICS structure%20 RELEASE:%20(3/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

