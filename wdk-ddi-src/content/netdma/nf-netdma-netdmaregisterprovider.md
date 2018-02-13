---
UID: NF:netdma.NetDmaRegisterProvider
title: NetDmaRegisterProvider function
author: windows-driver-content
description: The NetDmaRegisterProvider function registers a DMA provider.
old-location: netvista\netdmaregisterprovider.htm
old-project: netvista
ms.assetid: 35d70d0b-c1b9-433f-941d-6cb61ddf0b62
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netdma/NetDmaRegisterProvider, NetDmaRegisterProvider, NetDmaRegisterProvider function [Network Drivers Starting with Windows Vista], netvista.netdmaregisterprovider, netdma_ref_5267288c-9502-40f7-9af1-557babf3f840.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	netdma.h
apiname:
-	NetDmaRegisterProvider
product: Windows
targetos: Windows
req.typenames: NET_DMA_PNP_NOTIFICATION_CODE, *PNET_DMA_PNP_NOTIFICATION_CODE
---

# NetDmaRegisterProvider function


## -description


<div class="alert"><b>Note</b>  The NetDMA interface is not supported 

in Windows 8 and later.</div><div> </div>The 
  <b>NetDmaRegisterProvider</b> function registers a DMA provider.


## -syntax


````
NTSTATUS NetDmaRegisterProvider(
  _In_ PVOID                             ProviderContext,
  _In_ PVOID                             *pNetDmaProviderHandle,
  _In_ PNET_DMA_PROVIDER_CHARACTERISTICS ProviderCharacteristics
);
````


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
     <a href="..\netdma\ns-netdma-_net_dma_provider_characteristics.md">
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
    <a href="..\wdm\nf-wdm-iocreatedevice.md">IoCreateDevice</a> function to create a functional
    device object (FDO) and inserts it at the top of the device stack. The DMA provider driver then calls 
    <b>NetDmaRegisterProvider</b> to register the associated DMA provider.

The DMA provider driver supplies a 
    <a href="..\netdma\ns-netdma-_net_dma_provider_characteristics.md">
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
    <a href="..\netdma\nc-netdma-dma_channels_cpu_affinity_handler.md">
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
    <a href="..\netdma\nf-netdma-netdmaderegisterprovider.md">
    NetDmaDeregisterProvider</a> function.




## -see-also

<a href="..\wdm\nf-wdm-iocreatedevice.md">IoCreateDevice</a>



<a href="https://msdn.microsoft.com/f43dc60e-de88-4af0-ad83-3ce3a414d880">
   IRP_MN_FILTER_RESOURCE_REQUIREMENTS</a>



<a href="..\netdma\nf-netdma-netdmaderegisterprovider.md">NetDmaDeregisterProvider</a>



<a href="..\netdma\nc-netdma-dma_channels_cpu_affinity_handler.md">
   ProviderSetDmaChannelCpuAffinity</a>



<a href="..\netdma\ns-netdma-_net_dma_provider_characteristics.md">
   NET_DMA_PROVIDER_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NetDmaRegisterProvider function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

