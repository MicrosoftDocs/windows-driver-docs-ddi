---
UID: NF:ndis.NdisMSetMiniportAttributes
title: NdisMSetMiniportAttributes function
author: windows-driver-content
description: A miniport driver must call the NdisMSetMiniportAttributes function from its MiniportInitializeEx function to identify a context area for miniport adapter to NDIS, and to provide NDIS with information about the miniport adapter.
old-location: netvista\ndismsetminiportattributes.htm
old-project: netvista
ms.assetid: 861626af-23ea-40dc-a91a-7da42d4b0a1c
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NdisMSetMiniportAttributes function [Network Drivers Starting with Windows Vista], NdisMSetMiniportAttributes, miniport_ndis_functions_ref_2fc47304-466b-4ae0-8450-44c636cecf64.xml, ndis/NdisMSetMiniportAttributes, netvista.ndismsetminiportattributes
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miniport_Driver_Function, NdisMRegisterIoPortRange
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	LibDef
apilocation: 
-	ndis.lib
-	ndis.dll
apiname: 
-	NdisMSetMiniportAttributes
product: Windows
targetos: Windows
req.typenames: *PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE
---

# NdisMSetMiniportAttributes function


## -description


A miniport driver must call the 
  <b>NdisMSetMiniportAttributes</b> function from its 
  <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function to
  identify a context area for miniport adapter to NDIS, and to provide NDIS with information about the
  miniport adapter.


## -syntax


````
NDIS_STATUS NdisMSetMiniportAttributes(
  _In_ NDIS_HANDLE                       NdisMiniportAdapterHandle,
  _In_ PNDIS_MINIPORT_ADAPTER_ATTRIBUTES MiniportAttributes
);
````


## -parameters




### -param NdisMiniportHandle

TBD


### -param MiniportAttributes [in]

A pointer to an 
     <mshelp:link keywords="netvista.ndis_miniport_adapter_attributes" tabindex="0"><b>
     NDIS_MINIPORT_ADAPTER_ATTRIBUTES</b></mshelp:link> union which contains a driver-allocated attributes structure. The
     structure defines the attributes of the miniport adapter instance that 
     <i>MiniportAdapterHandle</i> specifies.


#### - NdisMiniportAdapterHandle [in]

The miniport adapter handle that NDIS passed to the 
     <i>MiniportAdapterHandle</i> parameter of 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>.


## -returns


<b>NdisMSetMiniportAttributes</b> returns one of the following status values:
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

<a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">NdisMSetMiniportAttributes</a> registered the miniport adapter attributes successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_BAD_VERSION</b></dt>
</dl>
</td>
<td width="60%">
Indicates that NDIS does not support the version that is specified in the 
       <b>Revision</b> member of the structure specified in the 
       <b>Header</b> member at 
       <i>MiniportAttributes</i> .

</td>
</tr>
</table> 



## -remarks


A miniport driver must call 
    <b>NdisMSetMiniportAttributes</b> from its 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function
    before the driver calls any other 
    <b>Ndis<i>Xxx</i></b> function that depends on the information supplied to 
    <b>NdisMSetMiniportAttributes</b>.

The 
    <mshelp:link keywords="netvista.ndis_miniport_adapter_attributes" tabindex="0"><b>
    NDIS_MINIPORT_ADAPTER_ATTRIBUTES</b></mshelp:link> union is a placeholder for various attributes structures. A
    miniport driver calls 
    <b>NdisMSetMiniportAttributes</b> multiple times with different attributes structures. A miniport driver
    must provide an initialized 
    <mshelp:link keywords="netvista.ndis_miniport_adapter_registration_attributes" tabindex="0"><b>
    NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</b></mshelp:link> structure from 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>. The miniport driver must provide these registration attributes before it
    calls any other 
    <b>Ndis<i>Xxx</i></b> function that depends on these attributes or that claims hardware resources.

The driver provides a 
    <b>MiniportAdapterContext</b> member to NDIS in the <a href="..\ndis\ns-ndis-_ndis_miniport_adapter_registration_attributes.md">NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</a>
    structure. The 
    <b>MiniportAdapterContext</b> member identifies a caller-supplied context area that NDIS passes as an
    input parameter to the driver's 
    <i>MiniportXxx</i> functions. This context area contains miniport-adapter-specific state information.

Miniport drivers must set the attributes in the 
    <mshelp:link keywords="netvista.ndis_miniport_adapter_general_attributes" tabindex="0"><b>
    NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES</b></mshelp:link> structure after they set the registration attributes in
    the <a href="..\ndis\ns-ndis-_ndis_miniport_adapter_registration_attributes.md">NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</a> structure and before they set any additional
    attributes.

A miniport driver can also call <b>NdisMSetMiniportAttributes</b> from its <a href="..\ndis\nc-ndis-miniport_add_device.md">MiniportAddDevice</a> function. In this case, the <a href="..\ndis\ns-ndis-_ndis_miniport_add_device_registration_attributes.md">NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES</a> structure is used to specify the context area.



## -see-also

<mshelp:link keywords="netvista.ndis_miniport_adapter_registration_attributes" tabindex="0"><b>
   NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</b></mshelp:link>

<a href="..\ndis\ns-ndis-_ndis_miniport_adapter_offload_attributes.md">NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</a>

<a href="https://msdn.microsoft.com/76d4bda0-c3e3-4abe-b16b-d2b5392c3db4">Setting the NDIS 6.0 Miniport Adapter Attributes</a>

<a href="https://msdn.microsoft.com/6d7a23dc-cc09-46d3-89d3-34e8e8f17a51">Initializing a Miniport Adapter</a>

<a href="..\ndis\ns-ndis-_ndis_miniport_add_device_registration_attributes.md">NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES</a>

<mshelp:link keywords="netvista.ndis_miniport_adapter_attributes" tabindex="0"><b>
   NDIS_MINIPORT_ADAPTER_ATTRIBUTES</b></mshelp:link>

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>

<a href="..\ndis\ns-ndis-_ndis_miniport_adapter_ndk_attributes.md">NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES</a>

<mshelp:link keywords="netvista.ndis_miniport_adapter_general_attributes" tabindex="0"><b>
   NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES</b></mshelp:link>

<a href="..\ndis\ns-ndis-_ndis_miniport_adapter_native_802_11_attributes.md">NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES</a>

<a href="..\ndis\ns-ndis-_ndis_miniport_adapter_hardware_assist_attributes.md">NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMSetMiniportAttributes function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

