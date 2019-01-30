---
UID: NF:netdma.NetDmaRegisterProvider
title: NetDmaRegisterProvider function (netdma.h)
description: The NetDmaRegisterProvider function registers a DMA provider.
old-location: netvista\netdmaregisterprovider.htm
tech.root: netvista
ms.assetid: 35d70d0b-c1b9-433f-941d-6cb61ddf0b62
ms.date: 05/02/2018
ms.keywords: NetDmaRegisterProvider, NetDmaRegisterProvider function [Network Drivers Starting with Windows Vista], netdma/NetDmaRegisterProvider, netdma_ref_5267288c-9502-40f7-9af1-557babf3f840.xml, netvista.netdmaregisterprovider
ms.topic: function
req.header: netdma.h
req.include-header: Netdma.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NetDMA 1.0 drivers in Windows Vista.
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	netdma.h
api_name:
-	NetDmaRegisterProvider
product:
- Windows
targetos: Windows
req.typenames: 
---

# NetDmaRegisterProvider function


## -description


<div class="alert"><b>Note</b>  The NetDMA interface is not supported 

in Windows 8 and later.</div><div> </div>The 
  <b>NetDmaRegisterProvider</b> function registers a DMA provider.


## -parameters




### -param ProviderContext [in]

A pointer to a block of driver-allocated context information that stores information about the DMA
     provider. NetDMA passes the context information in subsequent calls to 
     <i>Provider</i>Xxx functions that required a DMA provider context.


### -param pNetDmaProviderHandle [in]

A pointer to a value that is a handle that 
     <b>NetDmaRegisterProvider</b> supplies to identify the DMA provider. The DMA provider driver passes this
     handle to 
     <b>NetDma<i>Xxx</i></b> functions that require a provider handle.


### -param ProviderCharacteristics [in]

A pointer to a 
     <a href="https://msdn.microsoft.com/7ec6d449-fdc2-44d8-976b-5a1d23c76e7b">
     NET_DMA_PROVIDER_CHARACTERISTICS</a> structure that defines the characteristics of the DMA
     provider.


## -returns



<b>NetDmaRegisterProvider</b> can return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The operation failed because of insufficient resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The operation failed for unspecified reasons.

</td>
</tr>
</table>
 




## -remarks



DMA provider drivers call the 
    <b>NetDmaRegisterProvider</b> function to register a DMA provider. DMA provider drivers call 
    <b>NetDmaRegisterProvider</b> in their 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a> routine.

In the 
    <b>AddDevice</b> routine, the DMA provider driver calls the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff548397">IoCreateDevice</a> function to create a functional
    device object (FDO) and inserts it at the top of the device stack. The DMA provider driver then calls 
    <b>NetDmaRegisterProvider</b> to register the associated DMA provider.

The DMA provider driver supplies a 
    <a href="https://msdn.microsoft.com/7ec6d449-fdc2-44d8-976b-5a1d23c76e7b">
    NET_DMA_PROVIDER_CHARACTERISTICS</a> structure at the 
    <i>ProviderCharacteristics</i> parameter of 
    <b>NetDmaRegisterProvider</b>. The NET_DMA_PROVIDER_CHARACTERISTICS structure specifies the
    characteristics for a NetDMA provider, including the entry points for the 
    <i>ProviderXxx</i> functions.

The DMA provider driver provides a pointer to a block of driver-allocated context information at the 
    <i>ProviderContext</i> parameter of 
    <b>NetDmaRegisterProvider</b>. This context area stores information about the DMA provider. The NetDMA
    interface passes the context information in subsequent calls to 
    <i>ProviderXxx</i> functions that require a DMA provider context.

When 
    <b>NetDmaRegisterProvider</b> returns, it provides a handle at the location that the 
    <i>pNetDmaProviderHandle</i> parameter specifies. The NetDMA interface assigns this handle to identify the
    DMA provider. The DMA provider driver uses this handle in all subsequent calls to 
    <b>NetDma<i>Xxx</i></b> functions that are associated with the DMA provider.

If a computer supports MSI-X, the NetDMA interface, while in the context of the 
    <b>NetDmaRegisterProvider</b> function, calls the DMA provider driver's 
    <a href="https://msdn.microsoft.com/a53d8798-63fa-4b16-bda2-880ca3521d03">
    ProviderSetDmaChannelCpuAffinity</a> function to specify the CPU affinity of the interrupt for each DMA
    channel.

If a computer supports MSI-X, the DMA provider driver can specify interrupt affinities while handling
    the 
    <a href="https://msdn.microsoft.com/f43dc60e-de88-4af0-ad83-3ce3a414d880">
    IRP_MN_FILTER_RESOURCE_REQUIREMENTS</a> IRP. After the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a> routine successfully returns, the Plug
    and Play (PnP) manager sends the IRP_MN_FILTER_RESOURCE_REQUIREMENTS IRP for the DMA provider. The DMA
    provider driver must attempt to allocate MSI-X interrupt resources according to affinity parameters that
    the NetDMA interface passed to 
    <i>ProviderSetDmaChannelCpuAffinity</i>.

To deregister a DMA provider, a DMA provider driver calls the 
    <a href="https://msdn.microsoft.com/8832adbc-c2ab-4742-94a0-4e33d03eaaf1">
    NetDmaDeregisterProvider</a> function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a>



<a href="https://msdn.microsoft.com/f43dc60e-de88-4af0-ad83-3ce3a414d880">
   IRP_MN_FILTER_RESOURCE_REQUIREMENTS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548397">IoCreateDevice</a>



<a href="https://msdn.microsoft.com/7ec6d449-fdc2-44d8-976b-5a1d23c76e7b">
   NET_DMA_PROVIDER_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568328">NetDmaDeregisterProvider</a>



<a href="https://msdn.microsoft.com/a53d8798-63fa-4b16-bda2-880ca3521d03">
   ProviderSetDmaChannelCpuAffinity</a>
 

 

