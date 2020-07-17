---
UID: NS:ndis._NDIS_MINIPORT_SS_CHARACTERISTICS
title: _NDIS_MINIPORT_SS_CHARACTERISTICS (ndis.h)
description: The NDIS_MINIPORT_SS_CHARACTERISTICS structure specifies the pointers to a miniport driver's NDIS selective suspend handler functions. These functions are called by NDIS to issue idle notifications to the driver during a selective suspend operation.
old-location: netvista\ndis_miniport_ss_characteristics.htm
tech.root: netvista
ms.assetid: 325E5717-6B84-45AE-85D4-BA1839DB76A2
ms.date: 05/02/2018
keywords: ["_NDIS_MINIPORT_SS_CHARACTERISTICS structure"]
ms.keywords: "*PNDIS_MINIPORT_SS_CHARACTERISTICS, NDIS_MINIPORT_SS_CHARACTERISTICS, NDIS_MINIPORT_SS_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNDIS_MINIPORT_SS_CHARACTERISTICS, PNDIS_MINIPORT_SS_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_MINIPORT_SS_CHARACTERISTICS, ndis/NDIS_MINIPORT_SS_CHARACTERISTICS, ndis/PNDIS_MINIPORT_SS_CHARACTERISTICS, netvista.ndis_miniport_ss_characteristics"
f1_keywords:
 - "ndis/NDIS_MINIPORT_SS_CHARACTERISTICS"
 - "NDIS_MINIPORT_SS_CHARACTERISTICS"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ndis.h
api_name:
- NDIS_MINIPORT_SS_CHARACTERISTICS
product:
- Windows
targetos: Windows
req.typenames: NDIS_MINIPORT_SS_CHARACTERISTICS, *PNDIS_MINIPORT_SS_CHARACTERISTICS
---

# _NDIS_MINIPORT_SS_CHARACTERISTICS structure


## -description



The <b>NDIS_MINIPORT_SS_CHARACTERISTICS</b> structure specifies the pointers to a miniport driver's NDIS selective suspend handler functions. These functions are called by NDIS to issue idle notifications to the driver during a selective suspend operation.




## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_MINIPORT_SS_CHARACTERISTICS</b> structure. This member is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_MINIPORT_SS_CHARACTERISTICS. To specify the version of the <b>NDIS_MINIPORT_SS_CHARACTERISTICS</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_MINIPORT_SS_CHARACTERISTICS_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_MINIPORT_SS_CHARACTERISTICS_REVISION_1.


### -field Flags

 A <b>ULONG</b> value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.


### -field IdleNotificationHandler

A pointer to the miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_idle_notification">MiniportIdleNotification</a> function.


### -field CancelIdleNotificationHandler

A pointer to the miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_cancel_idle_notification">MiniportCancelIdleNotification</a> function.


## -remarks



To register the handler functions for NDIS selective suspend, the miniport driver follows these steps when its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-set_options">MiniportSetOptions</a> function is called:

<ol>
<li>
The miniport driver initializes an <b>NDIS_MINIPORT_SS_CHARACTERISTICS</b> structure with pointers to the handler functions.

</li>
<li>
The miniport driver  then calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissetoptionalhandlers">NdisSetOptionalHandlers</a> and sets the <i>OptionalHandlers</i> parameter to a pointer to the <b>NDIS_MINIPORT_SS_CHARACTERISTICS</b> structure.

</li>
</ol>
For more information on how to handle idle notifications for NDIS selective suspend, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-selective-suspend-idle-notifications">NDIS Selective Suspend Idle Notifications</a>.




## -see-also




<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_cancel_idle_notification">MiniportCancelIdleNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_idle_notification">MiniportIdleNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-set_options">MiniportSetOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissetoptionalhandlers">NdisSetOptionalHandlers</a>
 

 

