---
UID: NF:ndis.NdisRegisterProtocolDriver
title: NdisRegisterProtocolDriver function (ndis.h)
description: A protocol driver calls the NdisRegisterProtocolDriver function to register its ProtocolXxx functions with NDIS.
old-location: netvista\ndisregisterprotocoldriver.htm
tech.root: netvista
ms.assetid: b48571eb-13a2-4541-80ac-c8d31f378d37
ms.date: 05/02/2018
ms.keywords: NdisRegisterProtocolDriver, NdisRegisterProtocolDriver function [Network Drivers Starting with Windows Vista], ndis/NdisRegisterProtocolDriver, netvista.ndisregisterprotocoldriver, protocol_ndis_functions_ref_023b338a-65cf-4ccb-bce8-d1506f37f632.xml
ms.topic: function
f1_keywords:
 - "ndis/NdisRegisterProtocolDriver"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Protocol_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisRegisterProtocolDriver
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisRegisterProtocolDriver function


## -description


A protocol driver calls the
  <b>NdisRegisterProtocolDriver</b> function to register its 
  <i>ProtocolXxx</i> functions with NDIS.


## -parameters




### -param ProtocolDriverContext [in, optional]

A handle to a driver-allocated context area where the driver maintains state and configuration
     information.


### -param ProtocolCharacteristics [in]

A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_protocol_driver_characteristics">
     NDIS_PROTOCOL_DRIVER_CHARACTERISTICS</a> structure that the protocol driver created and initialized
     with its 
     <i>ProtocolXxx</i> function entry points.


### -param NdisProtocolHandle [out]

A pointer to a caller-supplied handle variable. NDIS writes a handle to this variable that
     uniquely identifies the driver that is registering. The driver must save this handle for use in
     subsequent 
     <b>Ndis<i>Xxx</i></b> function calls.


## -returns



<b>NdisRegisterProtocolDriver</b> returns one of the following status values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisregisterprotocoldriver">NdisRegisterProtocolDriver</a> returns NDIS_STATUS_SUCCESS if it registered the protocol
       driver.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_BAD_VERSION</b></dt>
</dl>
</td>
<td width="60%">
The version specified in the 
       <b>MajorNdisVersion</b> member of the structure at 
       <i>ProtocolCharacteristics</i> is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_BAD_CHARACTERISTICS</b></dt>
</dl>
</td>
<td width="60%">
Some members of the structure at the 
       <i>ProtocolCharacteristics</i> parameter are invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisregisterprotocoldriver">NdisRegisterProtocolDriver</a> failed due to insufficient resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisregisterprotocoldriver">NdisRegisterProtocolDriver</a> returns NDIS_STATUS_FAILURE if none of the preceding values
       applies.

</td>
</tr>
</table>
 




## -remarks



A protocol driver calls the 
    <b>NdisRegisterProtocolDriver</b> function from its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine. For more information about 
    <b>DriverEntry</b>, see 
    <a href="https://docs.microsoft.com/previous-versions/windows/embedded/gg156036(v=winembedded.80)">DriverEntry of NDIS
    Protocol Drivers</a>.

Drivers that call <b>
    NdisRegisterProtocolDriver</b> must be prepared for an immediate call to any of their <i>ProtocolXxx</i> functions.

Every protocol driver exports a set of 
    <i>ProtocolXxx</i> functions by setting up the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_protocol_driver_characteristics">
    NDIS_PROTOCOL_DRIVER_CHARACTERISTICS</a> structure and calling 
    <b>NdisRegisterProtocolDriver</b>. NDIS copies this structure to the NDIS library's internal storage.

To allow protocol drivers to register optional services, NDIS calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-set_options">ProtocolSetOptions</a> function within
    the context of 
    <b>NdisRegisterProtocolDriver</b>.

Protocol drivers call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisderegisterprotocoldriver">
    NdisDeregisterProtocolDriver</a> function to release resources that were previously allocated with 
    <b>NdisRegisterProtocolDriver</b>.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/embedded/gg156036(v=winembedded.80)">DriverEntry of NDIS Protocol
   Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_protocol_driver_characteristics">
   NDIS_PROTOCOL_DRIVER_CHARACTERISTICS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisderegisterprotocoldriver">NdisDeregisterProtocolDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndissetoptionalhandlers">NdisSetOptionalHandlers</a>
 

 

