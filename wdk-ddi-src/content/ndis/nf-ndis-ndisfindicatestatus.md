---
UID: NF:ndis.NdisFIndicateStatus
title: NdisFIndicateStatus function (ndis.h)
description: The NdisFIndicateStatus function passes on a filtered status indication from an underlying driver or originates a status indication.
old-location: netvista\ndisfindicatestatus.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisFIndicateStatus function"]
ms.keywords: NdisFIndicateStatus, NdisFIndicateStatus function [Network Drivers Starting with Windows Vista], ndis/NdisFIndicateStatus, ndis_status_ref_e649b130-878b-4019-b377-dd099de6eb8e.xml, netvista.ndisfindicatestatus
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_StatusIndication_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisFIndicateStatus
 - ndis/NdisFIndicateStatus
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisFIndicateStatus
---

# NdisFIndicateStatus function


## -description

The 
  <b>NdisFIndicateStatus</b> function passes on a filtered status indication from an underlying driver or
  originates a status indication.

## -parameters

### -param NdisFilterHandle [in]


The NDIS handle that identifies this filter module. NDIS passed the handle to the filter driver in
     a call to the 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a> function.

### -param StatusIndication [in]


A pointer to an 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_status_indication">NDIS_STATUS_INDICATION</a> structure
     that contains the status information.

## -remarks

Filter drivers can call 
    <b>NdisFIndicateStatus</b> from the 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_status">FilterStatus</a> function, to pass on a
    filtered status indication to overlying drivers.

To originate status indications, filter drivers call 
    <b>NdisFIndicateStatus</b> without a prior NDIS call to 
    <i>FilterStatus</i>.

A filter driver can call 
    <b>NdisFIndicateStatus</b> after setting its registration attributes and the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfsetattributes">NdisFSetAttributes</a> function returns.
    The driver must not call 
    <b>NdisFIndicateStatus</b> after it returns from the 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_detach">FilterDetach</a> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_detach">FilterDetach</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_status">FilterStatus</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_status_indication">NDIS_STATUS_INDICATION</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfsetattributes">NdisFSetAttributes</a>
