---
UID: NF:ndis.NdisMCmCloseAddressFamilyComplete
title: NdisMCmCloseAddressFamilyComplete macro
author: windows-driver-content
description: NdisMCmCloseAddressFamilyComplete returns the final status of a client's request, for which the MCM driver returned NDIS_STATUS_PENDING, to close the AF.
old-location: netvista\ndismcmcloseaddressfamilycomplete.htm
old-project: netvista
ms.assetid: be551557-06db-4fc9-bdcb-030e621e205a
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NdisMCmCloseAddressFamilyComplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisMCmCloseAddressFamilyComplete (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see         NdisMCmCloseAddressFamilyComplete (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisMCmCloseAddressFamilyComplete
req.alt-loc: ndis.h
req.ddi-compliance: Irql_MCM_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMCmCloseAddressFamilyComplete macro



## -description
<b>NdisMCmCloseAddressFamilyComplete</b> returns the final status of a client's request, for which the MCM
  driver returned NDIS_STATUS_PENDING, to close the AF.



## -syntax

````
VOID NdisMCmCloseAddressFamilyComplete(
  [in] NDIS_STATUS Status,
  [in] NDIS_HANDLE NdisAfHandle
);
````


## -parameters

### -param Status [in]

The caller sets this to NDIS_STATUS_SUCCESS.


### -param NdisAfHandle [in]

Specifies the NDIS-supplied handle passed to the MCM driver's 
     <a href="..\ndis\nc-ndis-protocol_cm_open_af.md">ProtocolCmOpenAf</a> function when this
     client originally opened the address family.


## -remarks
An MCM driver must call 
    <b>NdisMCmCloseAddressFamilyComplete</b> if its 
    <a href="..\ndis\nc-ndis-protocol_cm_close_af.md">ProtocolCmCloseAf</a> function previously
    returned NDIS_STATUS_PENDING for the given 
    <i>NdisAfHandle</i> . The client, which initiated the pended close-AF operation with a call to 
    <a href="..\ndis\nf-ndis-ndisclcloseaddressfamily.md">NdisClCloseAddressFamily</a>, cannot
    release the resources it allocated to track communications on the AF until the MCM driver's call to 
    <b>NdisMCmCloseAddressFamilyComplete</b>.

A call to 
    <b>NdisMCmCloseAddressFamilyComplete</b> causes NDIS to call the client's 
    <a href="..\ndis\nc-ndis-protocol_cl_close_af_complete.md">
    ProtocolClCloseAfComplete</a> function.

The MCM driver cannot subsequently use the 
    <i>NdisAfHandle</i>, which is invalid for the MCM driver when 
    <b>NdisMCmCloseAddressFamilyComplete</b> returns control.

Only connection-oriented miniport drivers that provide integrated call-management support can call 
    <b>NdisMCmCloseAddressFamilyComplete</b>. Stand-alone call managers, which register themselves with NDIS
    as protocol drivers, call 
    <b>NdisCmCloseAddressFamilyComplete</b> instead.


## -see-also
<dl>
<dt>
<a href="..\ndis\nf-ndis-ndisclcloseaddressfamily.md">NdisClCloseAddressFamily</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscmcloseaddressfamilycomplete.md">
   NdisCmCloseAddressFamilyComplete</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cl_close_af_complete.md">ProtocolClCloseAfComplete</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cm_close_af.md">ProtocolCmCloseAf</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cm_open_af.md">ProtocolCmOpenAf</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMCmCloseAddressFamilyComplete macro%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

