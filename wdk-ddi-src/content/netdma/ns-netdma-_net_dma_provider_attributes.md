---
UID: NS:netdma._NET_DMA_PROVIDER_ATTRIBUTES
title: "_NET_DMA_PROVIDER_ATTRIBUTES"
author: windows-driver-content
description: The NET_DMA_PROVIDER_ATTRIBUTES structure specifies the configuration attributes for a NetDMA provider.
old-location: netvista\net_dma_provider_attributes.htm
old-project: netvista
ms.assetid: 7b5a7e9e-b10b-4c94-80b1-172cd9f0c9ca
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PNET_DMA_PROVIDER_ATTRIBUTES, NET_DMA_PROVIDER_ATTRIBUTES, NET_DMA_PROVIDER_ATTRIBUTES structure [Network Drivers Starting with Windows Vista], PNET_DMA_PROVIDER_ATTRIBUTES, PNET_DMA_PROVIDER_ATTRIBUTES structure pointer [Network Drivers Starting with Windows Vista], _NET_DMA_PROVIDER_ATTRIBUTES, netdma/NET_DMA_PROVIDER_ATTRIBUTES, netdma/PNET_DMA_PROVIDER_ATTRIBUTES, netdma_ref_a00d6e7c-6712-49c9-9c64-d200e96074c5.xml, netvista.net_dma_provider_attributes"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: netdma.h
req.include-header: Netdma.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NetDMA 2.0 drivers in Windows Server 2008. Supported for NetDMA 1.1   drivers in Windows Server 2008. Supported for NetDMA 1.0 drivers in Windows Server 2008 and Windows   Vista.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	netdma.h
apiname:
-	NET_DMA_PROVIDER_ATTRIBUTES
product: Windows
targetos: Windows
req.typenames: NET_DMA_PROVIDER_ATTRIBUTES, *PNET_DMA_PROVIDER_ATTRIBUTES
---

# _NET_DMA_PROVIDER_ATTRIBUTES structure


## -description


<div class="alert"><b>Note</b>  The NetDMA interface is not supported in Windows 8 and later.</div><div> </div>The NET_DMA_PROVIDER_ATTRIBUTES structure specifies the configuration attributes for a NetDMA
  provider.


## -syntax


````
typedef struct _NET_DMA_PROVIDER_ATTRIBUTES {
  UCHAR            MajorHwVersion;
  UCHAR            MinorHwVersion;
  USHORT           Size;
  ULONG            Flags;
  ULONG            VendorId;
  ULONG            DmaChannelCount;
  ULONG            MaximumTransferSize;
  PHYSICAL_ADDRESS MaximumAddressSpace;
} NET_DMA_PROVIDER_ATTRIBUTES, *PNET_DMA_PROVIDER_ATTRIBUTES;
````


## -struct-fields




### -field MajorHwVersion

The major version number of the DMA provider hardware.


### -field MinorHwVersion

The minor version number of the DMA provider hardware.


### -field Size

The size, in bytes, of this NET_DMA_PROVIDER_ATTRIBUTES structure. Set this member to 
     sizeof(NET_DMA_PROVIDER_ATTRIBUTES).


### -field Flags

Reserved for DMA provider attributes flags. Set this member to zero.


### -field VendorId

A vendor identifier (ID) that uniquely identifies the vendor that created the DMA engine. This
     vendor ID is specified in the device's PCI configuration space. For more information about the vendor
     ID, see 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/install/identifiers-for-pci-devices">Identifiers for PCI
     Devices</a>.


### -field DmaChannelCount

The number of DMA channels that the DMA provider supports. This number can differ from the 
     <b>MaxDmaChannelCount</b> member of the 
     <a href="..\netdma\ns-netdma-_net_dma_provider_characteristics.md">
     NET_DMA_PROVIDER_CHARACTERISTICS</a> structure that defines the maximum number of DMA channels that
     this type of DMA provider can support.


### -field MaximumTransferSize

The maximum DMA transfer size, in bytes, that the DMA provider can support. This value can must be
     4 KB or greater.


### -field MaximumAddressSpace

The largest physical address that the DMA engine can support.


## -remarks



To start a DMA provider, the DMA provider driver supplies a NET_DMA_PROVIDER_ATTRIBUTES structure at
    the 
    <i>ProviderAttributes</i> parameter of the 
    <a href="..\netdma\nf-netdma-netdmaproviderstart.md">NetDmaProviderStart</a> function.

A DMA provider driver initializes a DMA engine and starts a DMA provider while handling the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a> IRP.




## -see-also

<a href="..\netdma\nf-netdma-netdmaproviderstart.md">NetDmaProviderStart</a>



<a href="..\netdma\ns-netdma-_net_dma_provider_characteristics.md">
   NET_DMA_PROVIDER_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a>



<a href="..\netdma\nf-netdma-netdmaproviderstop.md">NetDmaProviderStop</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NET_DMA_PROVIDER_ATTRIBUTES structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

