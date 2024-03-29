---
UID: NF:dot11wdi.NdisMRegisterWdiMiniportDriver
title: NdisMRegisterWdiMiniportDriver function (dot11wdi.h)
description: A miniport driver calls the NdisMRegisterWdiMiniportDriver function to register MiniportWdiXxx entry points with NDIS as the first step in initialization.
old-location: netvista\ndismregisterwdiminiportdriver.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisMRegisterWdiMiniportDriver function"]
ms.keywords: NdisMRegisterWdiMiniportDriver, NdisMRegisterWdiMiniportDriver function [Network Drivers Starting with Windows Vista], dot11wdi/NdisMRegisterWdiMiniportDriver, netvista.ndismregisterwdiminiportdriver
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
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisMRegisterWdiMiniportDriver
 - dot11wdi/NdisMRegisterWdiMiniportDriver
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
---

# NdisMRegisterWdiMiniportDriver function


## -description

> [!IMPORTANT]
> This topic is part of the [WDI driver model](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) released in Windows 10. The WDI driver model is in maintenance mode and will only receive high priority fixes. [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features.

A miniport driver calls the NdisMRegisterWdiMiniportDriver function to register MiniportWdiXxx entry points with NDIS as the first step in initialization.

## -parameters

### -param DriverObject [in]


A pointer to an opaque driver object that the miniport driver received in its 
     <a href="/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine at the 
     <i>Argument1</i> parameter (see 
     <a href="/windows-hardware/drivers/network/initializing-a-miniport-driver">DriverEntry of NDIS
     Miniport Drivers</a>).

### -param RegistryPath [in]


A pointer to an opaque registry path that the miniport driver received in its 
     <a href="/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine at the 
     <i>Argument2</i> parameter.

### -param NdisDriverContext [in, optional]


A handle to a driver-allocated context area where the driver maintains state and configuration
     information.

### -param MiniportDriverCharacteristics [in]


A pointer to an 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_driver_characteristics">
     NDIS_MINIPORT_DRIVER_CHARACTERISTICS</a> structure that the caller initialized.

### -param MiniportWdiCharacteristics [in]


A pointer to an <a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a> structure that the caller initialized.

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

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_driver_characteristics">NDIS_MINIPORT_DRIVER_CHARACTERISTICS</a>



<a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>
