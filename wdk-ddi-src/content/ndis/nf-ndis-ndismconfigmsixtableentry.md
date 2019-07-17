---
UID: NF:ndis.NdisMConfigMSIXTableEntry
title: NdisMConfigMSIXTableEntry function (ndis.h)
description: The NdisMConfigMSIXTableEntry function performs configuration operations for MSI-X table entries for device-assigned MSI-X messages.
old-location: netvista\ndismconfigmsixtableentry.htm
tech.root: netvista
ms.assetid: 93f94a42-bffb-4e4d-a560-b0da5d7d0019
ms.date: 05/02/2018
ms.keywords: NdisMConfigMSIXTableEntry, NdisMConfigMSIXTableEntry function [Network Drivers Starting with Windows Vista], ndis/NdisMConfigMSIXTableEntry, ndis_msix_ref_421b54e0-bc38-45d0-9eb8-cbc4e4570836.xml, netvista.ndismconfigmsixtableentry
ms.topic: function
f1_keywords:
 - "ndis/NdisMConfigMSIXTableEntry"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.1 and later.
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
req.lib: Ndis.lib
req.dll: 
req.irql: See Remarks section
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisMConfigMSIXTableEntry
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMConfigMSIXTableEntry function


## -description


The 
  <b>NdisMConfigMSIXTableEntry</b> function performs configuration operations for MSI-X table entries for
  device-assigned MSI-X messages.


## -parameters




### -param NdisMiniportHandle [in]

An NDIS miniport adapter handle that NDIS supplied to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_initialize">
     MiniportInitializeEx</a> function.


### -param MSIXConfigParameters [in]

A pointer to a caller-allocated 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_msix_config_parameters">
     NDIS_MSIX_CONFIG_PARAMETERS</a> structure that defines the requested configuration operation and
     specifies the parameters that are required for that particular operation.


## -returns



<b>NdisMConfigMSIXTableEntry</b> returns an appropriate failure code from the underlying PCI bus driver
     or one of the following status values:

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
The MSI-X table entry was reconfigured successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisMConfigMSIXTableEntry</b> failed because one or more members in the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_msix_config_parameters">
       NDIS_MSIX_CONFIG_PARAMETERS</a> structure were invalid.

</td>
</tr>
</table>
 




## -remarks



NDIS miniport drivers that support MSI-X call the 
    <b>NdisMConfigMSIXTableEntry</b> function to mask, unmask, or map MSI-X table entries to device-assigned
    MSI-X messages. Miniport drivers that support RSS use 
    <b>NdisMConfigMSIXTableEntry</b> to change the CPU affinity of MSI-X table entries at run time.

<b>NdisMConfigMSIXTableEntry</b> is a wrapper around the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_pci_msix_table_config_interface">
    GUID_MSIX_TABLE_CONFIG_INTERFACE</a> query. Miniport drivers can call 
    <b>NdisMConfigMSIXTableEntry</b> after NDIS calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function and
    before the driver returns from the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a> function.

The miniport driver can set the CPU affinity of MSI-X interrupt resources so that the device has at
    least one MSI-X message for each RSS processor. Note that the PCI bus driver initially maps the 
    <i>n</i> MSI-X table entries (where 
    <i>n</i> is the number of MSI-X table entries that the NIC hadware reported to the bus) to the first 
    <i>n</i> MSI-X messages in modified resources. After NDIS calls 
    <i>MiniportInitializeEx</i>, when the miniport driver changes the target processor of a particular MSI-X
    table entry, the driver calls 
    <b>NdisMConfigMSIXTableEntry</b> to map that table entry to an MSI-X message that already has the affinity
    set to the desired processor.

For the 
    <b>NdisMSIXTableConfigSetTableEntry</b> operation, callers of 
    <b>NdisMConfigMSIXTableEntry</b> must run at IRQL <= DISPATCH_LEVEL.

For the 
    <b>NdisMSIXTableConfigMaskTableEntry</b> or 
    <b>NdisMSIXTableConfigUnmaskTableEntry</b> operations, callers of 
    <b>NdisMConfigMSIXTableEntry</b> can be running at any IRQL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_msix_config_parameters">NDIS_MSIX_CONFIG_PARAMETERS</a>
 

 

