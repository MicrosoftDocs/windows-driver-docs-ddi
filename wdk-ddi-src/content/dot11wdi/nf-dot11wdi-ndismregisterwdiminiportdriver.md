---
UID: NF:dot11wdi.NdisMRegisterWdiMiniportDriver
title: NdisMRegisterWdiMiniportDriver function (dot11wdi.h)
description: A miniport driver calls the NdisMRegisterWdiMiniportDriver function to register MiniportWdiXxx entry points with NDIS as the first step in initialization.
old-location: netvista\ndismregisterwdiminiportdriver.htm
tech.root: netvista
ms.assetid: 60FE4E6C-38D4-438F-983B-7336926F6FE2
ms.date: 05/02/2018
ms.keywords: NdisMRegisterWdiMiniportDriver, NdisMRegisterWdiMiniportDriver function [Network Drivers Starting with Windows Vista], dot11wdi/NdisMRegisterWdiMiniportDriver, netvista.ndismregisterwdiminiportdriver
f1_keywords:
 - "dot11wdi/NdisMRegisterWdiMiniportDriver"
req.header: dot11wdi.h
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
- NdisMRegisterWdiMiniportDriver
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMRegisterWdiMiniportDriver function


## -description


A miniport driver calls the NdisMRegisterWdiMiniportDriver function to register MiniportWdiXxx entry points with NDIS as the first step in initialization.


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


### -param NdisDriverContext [in, optional]

A handle to a driver-allocated context area where the driver maintains state and configuration
     information.


### -param MiniportDriverCharacteristics [in]

A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_driver_characteristics">
     NDIS_MINIPORT_DRIVER_CHARACTERISTICS</a> structure that the caller initialized.


### -param MiniportWdiCharacteristics [in]

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a> structure that the caller initialized.


### -param NdisMiniportDriverHandle [out]

A pointer to a caller-supplied handle variable. NDIS writes a handle to this variable that
     uniquely identifies this driver. The driver must save this handle for use in subsequent 
     <b>Ndis<i>Xxx</i></b> function calls.


## -returns




            NdisMRegisterWdiMiniportDriver can return any of the following return values.

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
NdisMRegisterWdiMiniportDriver registered the WDI miniport driver successfully.

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
<tr>
<td width="40%">
<dl>
<dt><b>Other NDIS_STATUS codes</b></dt>
</dl>
</td>
<td width="60%">
An appropriate NDIS_STATUS code in the case of a failure.

</td>
</tr>
</table>
 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_driver_characteristics">NDIS_MINIPORT_DRIVER_CHARACTERISTICS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>
 

 

