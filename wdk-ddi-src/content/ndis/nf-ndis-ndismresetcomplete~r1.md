---
UID: NF:ndis.NdisMResetComplete~r1
title: NdisMResetComplete macro (NDIS 6.x)
ms.date: 03/02/2021
tech.root: netvista
targetos: Windows
description: "Learn more about: NdisMResetComplete function (NDIS 6.x)"
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ndis.h
req.idl: 
req.include-header: 
req.irql: <= DISPATCH_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows Vista and later
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NdisMResetComplete
f1_keywords:
 - ndis/NdisMResetComplete
dev_langs:
 - c++
---

# NdisMResetComplete function (NDIS 6.x)

## -description

The **NdisMResetComplete** function returns the final status of a reset request for which the miniport driver previously returned NDIS_STATUS_PENDING.

## -parameters

### -param MiniportAdapterHandle

The miniport adapter handle that NDIS originally passed to the 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function.

### -param Status

The final status of the reset operation just completed. The return values are the same as those listed for the [MINIPORT_RESET callback function](./nc-ndis-miniport_reset.md).

### -param AddressingReset

A Boolean value that is <b>TRUE</b> if NDIS is responsible for restoring the settings for multicast
     addresses, packet filters, and task offload information. In this case, the miniport driver is
     responsible for restoring the rest of the configuration settings for the network interface card (NIC)
     referenced by 
     <i>MiniportAdapterHandle</i> . 
     

If 
     <i>AddressingReset</i> is <b>FALSE</b>, the miniport driver is responsible for restoring all of the
     configuration settings for the NIC.

For more information, see 
     <a href="/windows-hardware/drivers/network/hardware-reset">Hardware Reset</a>.

## -remarks

If the 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_reset">MiniportResetEx</a> function returns
    NDIS_STATUS_PENDING, the miniport driver must call 
    <b>NdisMResetComplete</b> when it completes the reset operation.

Protocol drivers cannot initiate a reset operation in NDIS 6.0 and later versions.

Some NICs lose all multicast address, packet filter, or functional address information when a soft
    reset is issued. The driver of such a NIC sets 
    <i>AddressingReset</i> to <b>TRUE</b> when it calls 
    <b>NdisMResetComplete</b>, causing NDIS to call its 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_oid_request">MiniportOidRequest</a> function to
    restore the addressing state. For more information, see 
    <a href="/windows-hardware/drivers/network/hardware-reset">Hardware Reset</a>.

A miniport driver must release any spin lock that it is holding before calling 
    <b>NdisMResetComplete</b>.

In NDIS 6.0 and later, callers of 
    <b>NdisMResetComplete</b> must run at IRQL <= DISPATCH_LEVEL. Otherwise, callers of 
    <b>NdisMResetComplete</b> must run at IRQL = DISPATCH_LEVEL.

## -see-also

[NdisMResetComplete macro (NDIS 5.x)](./nf-ndis-ndismresetcomplete.md)
