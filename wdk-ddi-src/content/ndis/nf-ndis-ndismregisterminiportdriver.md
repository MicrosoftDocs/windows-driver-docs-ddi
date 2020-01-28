---
UID: NF:ndis.NdisMRegisterMiniportDriver
title: NdisMRegisterMiniportDriver function (ndis.h)
description: A miniport driver calls the NdisMRegisterMiniportDriver function to register MiniportXxx entry points with NDIS as the first step in initialization.
old-location: netvista\ndismregisterminiportdriver.htm
tech.root: netvista
ms.assetid: bed68aa8-499d-41fd-997b-a46316913cc8
ms.date: 05/02/2018
ms.keywords: NdisMRegisterMiniportDriver, NdisMRegisterMiniportDriver function [Network Drivers Starting with Windows Vista], miniport_ndis_functions_ref_d6406d6d-f738-4f65-90af-38038b188cc7.xml, ndis/NdisMRegisterMiniportDriver, netvista.ndismregisterminiportdriver
f1_keywords:
 - "ndis/NdisMRegisterMiniportDriver"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miniport_Driver_Function
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
- NdisMRegisterMiniportDriver
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMRegisterMiniportDriver function


## -description


A miniport driver calls the 
  <b>NdisMRegisterMiniportDriver</b> function to register 
  <i>MiniportXxx</i> entry points with NDIS as the first step in initialization.


## -parameters




### -param DriverObject [in]

A pointer to an opaque driver object that the miniport driver received in its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine at the 
     <i>Argument1</i> parameter (see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/initializing-a-miniport-driver">DriverEntry of NDIS
     Miniport Drivers</a>).


### -param RegistryPath [in]

A pointer to an opaque registry path that the miniport driver received in its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine at the 
     <i>Argument2</i> parameter.


### -param MiniportDriverContext [in, optional]

A handle to a driver-allocated context area where the driver maintains state and configuration
     information.


### -param MiniportDriverCharacteristics [in]

A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_driver_characteristics">
     NDIS_MINIPORT_DRIVER_CHARACTERISTICS</a> structure that the caller initialized.


### -param NdisMiniportDriverHandle [out]

A pointer to a caller-supplied handle variable. NDIS writes a handle to this variable that
     uniquely identifies this driver. The driver must save this handle for use in subsequent 
     <b>Ndis<i>Xxx</i></b> function calls.


## -returns



<b>NdisMRegisterMiniportDriver</b> returns one of the following status values:

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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">NdisMRegisterMiniportDriver</a> registered the miniport driver successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_BAD_CHARACTERISTICS</b></dt>
</dl>
</td>
<td width="60%">
The 
       <i>CharacteristicsLength</i> parameter is incorrect for the NDIS version that is specified at the 
       <b>MajorNdisVersion</b> member in the structure at 
       <i>MiniportDriverCharacteristics</i> .

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_BAD_VERSION</b></dt>
</dl>
</td>
<td width="60%">
The 
       <b>MajorNdisVersion</b> or 
       <b>MinorNdisVersion</b> specified in the characteristics structure is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
A shortage of resources, possibly memory, prevented NDIS from registering the caller.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
This is a default error status, returned when none of the preceding errors caused the
       registration to fail.

</td>
</tr>
</table>
 




## -remarks



An NDIS driver calls 
    <b>NdisMRegisterMiniportDriver</b> from its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine. For more information, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/initializing-a-miniport-driver">DriverEntry of NDIS
    Miniport Drivers</a>.

Every miniport driver exports a set of standard 
    <i>MiniportXxx</i> functions by setting up the characteristics structure and calling 
    <b>NdisMRegisterMiniportDriver</b>. NDIS copies the characteristics structure to NDIS internal storage.
    Therefore, after it has registered, a driver cannot change its 
    <i>MiniportXxx</i> entry points.

To register its virtual miniport interface, an NDIS intermediate drivers must call 
    <b>NdisMRegisterMiniportDriver</b> with the NDIS_INTERMEDIATE_DRIVER flag set in the structure at 
    <i>MiniportDriverCharacteristics</i> . NDIS drivers that have a WDM lower edge must call 
    <b>NdisMRegisterMiniportDriver</b> with the NDIS_WDM_DRIVER flag set in the structure at 
    <i>MiniportDriverCharacteristics</i> .

Drivers can register as a combined miniport driver and intermediate driver. To register its physical
    miniport driver, a miniport-intermediate driver calls 
    <b>NdisMRegisterMiniportDriver</b> with appropriate parameters just as for any miniport driver. To
    register its virtual miniport interface, the driver calls 
    <b>NdisMRegisterMiniportDriver</b> again, but with the NDIS_INTERMEDIATE_DRIVER flag set in the 
    <i>MiniportDriverCharacteristics</i> parameter.

To enable miniport drivers to register optional services, NDIS calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-set_options">MiniportSetOptions</a> function within
    the context of 
    <b>NdisMRegisterMiniportDriver</b>.

After a driver calls 
    <b>NdisMRegisterMiniportDriver</b>, the driver should be prepared to be called back at the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function that
    is specified in the 
    <i>MiniportDriverCharacteristics</i> parameter any time after DriverEntry returns.

If an error occurs in 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> after 
    <b>NdisMRegisterMiniportDriver</b> returns successfully, the driver must call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismderegisterminiportdriver">
    NdisMDeregisterMiniportDriver</a> function before 
    <b>DriverEntry</b> returns. If 
    <b>DriverEntry</b> succeeds, the driver must call 
    <b>NdisMDeregisterMiniportDriver</b> from its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_unload">MiniportDriverUnload</a> function.




## -see-also

[Initializing a Miniport Driver](https://docs.microsoft.com/windows-hardware/drivers/network/initializing-a-miniport-driver)


<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_unload">MiniportDriverUnload</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-set_options">MiniportSetOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_driver_characteristics">
   NDIS_MINIPORT_DRIVER_CHARACTERISTICS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismderegisterminiportdriver">
   NdisMDeregisterMiniportDriver</a>
 

 

