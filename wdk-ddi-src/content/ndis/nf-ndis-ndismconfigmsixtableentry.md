---
UID: NF:ndis.NdisMConfigMSIXTableEntry
title: NdisMConfigMSIXTableEntry function
author: windows-driver-content
description: The NdisMConfigMSIXTableEntry function performs configuration operations for MSI-X table entries for device-assigned MSI-X messages.
old-location: netvista\ndismconfigmsixtableentry.htm
old-project: netvista
ms.assetid: 93f94a42-bffb-4e4d-a560-b0da5d7d0019
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , C, E, I, M, N, NdisMConfigMSIXTableEntry, NdisMConfigMSIXTableEntry function [Network Drivers Starting with Windows Vista], S, T, X, a, b, d, e, f, g, i, l, n, ndis/NdisMConfigMSIXTableEntry, ndis_msix_ref_421b54e0-bc38-45d0-9eb8-cbc4e4570836.xml, netvista.ndismconfigmsixtableentry, o, r, s, t, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisMConfigMSIXTableEntry
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMConfigMSIXTableEntry function


## -description


The 
  <b>NdisMConfigMSIXTableEntry</b> function performs configuration operations for MSI-X table entries for
  device-assigned MSI-X messages.


## -syntax


````
NDIS_STATUS NdisMConfigMSIXTableEntry(
  _In_ NDIS_HANDLE                  NdisMiniportHandle,
  _In_ PNDIS_MSIX_CONFIG_PARAMETERS MSIXConfigParameters
);
````


## -parameters




### -param NdisMiniportHandle [in]

An NDIS miniport adapter handle that NDIS supplied to the 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">
     MiniportInitializeEx</a> function.


### -param MSIXConfigParameters [in]

A pointer to a caller-allocated 
     <a href="..\ndis\ns-ndis-_ndis_msix_config_parameters.md">
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
       <a href="..\ndis\ns-ndis-_ndis_msix_config_parameters.md">
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
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff558787">
    GUID_MSIX_TABLE_CONFIG_INTERFACE</a> query. Miniport drivers can call 
    <b>NdisMConfigMSIXTableEntry</b> after NDIS calls the 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function and
    before the driver returns from the 
    <a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a> function.

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
    <b>NdisMConfigMSIXTableEntry</b> must run at IRQL &lt;= DISPATCH_LEVEL.

For the 
    <b>NdisMSIXTableConfigMaskTableEntry</b> or 
    <b>NdisMSIXTableConfigUnmaskTableEntry</b> operations, callers of 
    <b>NdisMConfigMSIXTableEntry</b> can be running at any IRQL.




## -see-also

<a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\ns-ndis-_ndis_msix_config_parameters.md">NDIS_MSIX_CONFIG_PARAMETERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMConfigMSIXTableEntry function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

