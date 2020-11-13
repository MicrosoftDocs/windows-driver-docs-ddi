---
UID: TP:netvista
title: Networking drivers for Windows Vista and later
ms.assetid: 81753000-e53e-3c99-bde3-5c662c944380
ms.date: 10/29/2019
keywords: ["Networking drivers for Windows Vista and later"]
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Networking drivers for Windows Vista and later

## -description

> [!IMPORTANT]
> ### Bias-free communication
>
> Microsoft supports a diverse and inclusive environment. This article contains references to terminology that the Microsoft [style guide for bias-free communication](/style-guide/bias-free-communication) recognizes as exclusionary. The word or phrase is used in this article for consistency because it currently appears in the software. When the software is updated to remove the language, this article will be updated to be in alignment.

This section lists functions, event callbacks, macros, structures, and enumerations used in Windows networking device drivers starting with Windows Vista. The header files that contain the topics defined in this section are included in the Windows Driver Kit (WDK).

For the programming guide, see [Networking drivers for Windows Vista and later](/windows-hardware/drivers/network).

## Network driver headers

To develop Networking drivers for Windows Vista and later, you need these headers. This is a complete list of all headers in the WDK for network drivers; headers that support particular networking technologies are listed in the following sections.

- [Dot11wdi.h](../dot11wdi/index.md)
- [Checksum.h](../checksum/index.md)
- [Checksumtypes.h](../checksumtypes/index.md)
- [Extension.h](../extension/index.md)
- [Fragment.h](../fragment/index.md)
- [Fwpmk.h](../fwpmk/index.md)
- [Fwpsk.h](../fwpsk/index.md)
- [Knetpwrdepbroker.h](../knetpwrdepbroker/index.md)
- [Logicaladdress.h](../logicaladdress/index.md)
- [Logicaladdresstypes.h](../logicaladdresstypes/index.md)
- [Lso.h](../lso/index.md)
- [Lsotypes.h](../lsotypes/index.md)
- [Mbbcx.h](../mbbcx/index.md)
- [Mdl.h](../mdl/index.md)
- [Mdltypes.h](../mdltypes/index.md)
- [Nbl.h](../nbl/index.md)
- [Ndis.h](../ndis/index.md)
- [Ndischimney.h](../ndischimney/index.md)
- [Ndisndk.h](../ndisndk/index.md)
- [Ndiswwan.h](../ndiswwan/index.md)
- [Ndkpi.h](../ndkpi/index.md)
- [Netadapter.h](../netadapter/index.md)
- [Netadapteroffload.h](../netadapteroffload/index.md)
- [Netadapterpacket.h](../netadapterpacket/index.md)
- [Netconfiguration.h](../netconfiguration/index.md)
- [Netdevice.h](../netdevice/index.md)
- [Netdma.h](../netdma/index.md)
- [Netioddk.h](../netioddk/index.md)
- [Netpacketqueue.h](../netpacketqueue/index.md)
- [Netpnp.h](../netpnp/index.md)
- [Netpoweroffload.h](../netpoweroffload/index.md)
- [Netpoweroffloadlist.h](../netpoweroffload/index.md)
- [Netreceivescaling.h](../netreceivescaling/index.md)
- [Netrxqueue.h](../netrxqueue/index.md)
- [Nettxqueue.h](../nettxqueue/index.md)
- [Netwakesource.h](../netwakesource/index.md)
- [Netwakesourcelist.h](../netwakesource/index.md)
- [Ntddndis.h](../ntddndis/index.md)
- [Ntddrilapitypes.h](../ntddrilapitypes/index.md)
- [Oemrilapitypes.h](../oemrilapitypes/index.md)
- [Packet.h](../packet/index.md)
- [Returncontext.h](../returncontext/index.md)
- [Returncontexttypes.h](../returncontexttypes/index.md)
- [Rilapi.h](../rilapi/index.md)
- [Rilapitypes.h](../rilapitypes/index.md)
- [Ring.h](../ring/index.md)
- [Ringcollection.h](../ringcollection/index.md)
- [Rsc.h](../rsc/index.md)
- [Rsctypes.h](../rsctypes/index.md)
- [Virtualaddress.h](../virtualaddress/index.md)
- [Virtualaddresstypes.h](../virtualaddresstypes/index.md)
- [Vmbuskernelmodeclientlibapi.h](../vmbuskernelmodeclientlibapi/index.md)
- [Wditypes.hpp](../wditypes/index.md)
- [Windot11.h](../windot11/index.md)
- [Wlanihv.h](../wlanihv/index.md)
- [Wlanihvtypes.h](../wlanihvtypes/index.md)
- [Wlantypes.h](../wlantypes/index.md)
- [Wlclient.h](../wlclient/index.md)
- [Wsk.h](../wsk/index.md)
- [Wwan.h](../wwan/index.md)

The following sections contain information for each area of network driver technology:

## NetAdapterCx

Starting in Windows 10, version 1703, the Windows Driver Kit (WDK) includes a class extension module (NetAdapterCx) that enables you to write a KMDF-based networking (NDIS) client driver for Network Interface Cards (NICs). The client driver interacts with NetAdapterCx, which acts as a bridge to traditional NDIS. 

For more info about NetAdapterCx, see [Network Adapter WDF Class Extension (Cx)](/windows-hardware/drivers/netcx/).

Header files that support NetAdapterCx include the following:

- [Checksum.h](../checksum/index.md)
- [Checksumtypes.h](../checksumtypes/index.md)
- [Extension.h](../extension/index.md)
- [Fragment.h](../fragment/index.md)
- [Logicaladdress.h](../logicaladdress/index.md)
- [Logicaladdresstypes.h](../logicaladdresstypes/index.md)
- [Lso.h](../lso/index.md)
- [Lsotypes.h](../lsotypes/index.md)
- [Mdl.h](../mdl/index.md)
- [Mdltypes.h](../mdltypes/index.md)
- [Netadapter.h](../netadapter/index.md)
- [Netadapteroffload.h](../netadapteroffload/index.md)
- [Netadapterpacket.h](../netadapterpacket/index.md)
- [Netconfiguration.h](../netconfiguration/index.md)
- [Netdevice.h](../netdevice/index.md)
- [Netpacketqueue.h](../netpacketqueue/index.md)
- [Netpoweroffload.h](../netpoweroffload/index.md)
- [Netpoweroffloadlist.h](../netpoweroffload/index.md)
- [Netreceivescaling.h](../netreceivescaling/index.md)
- [Netrxqueue.h](../netrxqueue/index.md)
- [Nettxqueue.h](../nettxqueue/index.md)
- [Netwakesource.h](../netwakesource/index.md)
- [Netwakesourcelist.h](../netwakesource/index.md)
- [Packet.h](../packet/index.md)
- [Returncontext.h](../returncontext/index.md)
- [Returncontexttypes.h](../returncontexttypes/index.md)
- [Ring.h](../ring/index.md)
- [Ringcollection.h](../ringcollection/index.md)
- [Rsc.h](../rsc/index.md)
- [Rsctypes.h](../rsctypes/index.md)
- [Virtualaddress.h](../virtualaddress/index.md)
- [Virtualaddresstypes.h](../virtualaddresstypes/index.md)

## NDIS Core Functionality

The foundation for all kernel mode Windows network technologies is the Network Driver Interface Specification, or NDIS. NDIS forms the network driver platform that bridges the gap between the NIC and upper layers in the network stack.

For more info about NDIS Core Functionality, see [NDIS Core Functionality](/windows-hardware/drivers/network/ndis-core-functionality2).

Header files that support NDIS core functionality include the following:

- [Ndis.h](../ndis/index.md)
- [Ntddndis.h](../ntddndis/index.md)

## Scalable Networking

Windows includes technologies for scalable networking such as Header-Data Split, NetDMA, PacketDirect Provider Interface, Network Virtualization using Generic Routing Encapsulation (NVGRE) Task Offload, Receive Segment Coalescing (RSC), Receive Side Scaling (RSS), and TCP/IP offload.

For more info about scalable networking, see [Scalable Networking](/windows-hardware/drivers/network/scalable-networking2).

Header files that support scalable networking include the following:

- [Ndis.h](../ndis/index.md)
- [Ndischimney.h](../ndischimney/index.md)
- [Ndisndk.h](../ndisndk/index.md)
- [Ndkpi.h](../ndkpi/index.md)
- [Netdma.h](../netdma/index.md)
- [Ntddndis.h](../ntddndis/index.md)

## Virtualized Networking

NDIS supports technologies for packet transfer and management within a Hyper-V virtual environment such as Single Root I/O Virtualization (SR-IOV), Virtual Machine Queue (VMQ), and Hyper-V Extensible Switch.

For more info about virtualized networking, see [Virtualized Networking](/windows-hardware/drivers/network/virtualized-networking).

Header files that support virtualized networking include the following:

- [Ndis.h](../ndis/index.md)
- [Ntddndis.h](../ntddndis/index.md)
- [VmbusKernelModeClientLibApi.h](../vmbuskernelmodeclientlibapi/index.md)

## Wireless Networking

Windows network drivers support both Wi-Fi and Mobile Broadband. For Windows Vista, Windows 7, Windows 8, and Windows 8.1, Wi-Fi drivers use the Native 802.11 Wireless LAN model. For Windows 10 and later, Wi-Fi drivers use the WLAN Universal Windows driver model, or WDI.

For more info about wireless networking, see [Wireless Networking](/windows-hardware/drivers/network/wireless-networking2).

Header files that support wireless networking include the following:

- [Dot11Wdi.h](../dot11wdi/index.md)
- [Ndis.h](../ndis/index.md)
- [Ndiswwan.h](../ndiswwan/index.md)
- [Ntddndis.h](../ntddndis/index.md)
- [Wditypes.hpp](../wditypes/index.md)
- [Windot11.h](../windot11/index.md)
- [Wlanihv.h](../wlanihv/index.md)
- [Wlantypes.h](../wlantypes/index.md)
- [Wlclient.h](../wlclient/index.md)
- [Wwan.h](../wwan/index.md)

## MBBCx

Starting in Windows 10, version 1809, the Windows Driver Kit (WDK) includes a class extension module (MBBCx) that enables you to write a KMDF-based mobile broadband (MBB) client driver for MBB devices. The client driver interacts with MBBCx for mobile broadband media-specific functionality in addition to being based on [NetAdapterCx](#netadaptercx) and WDF.

For more info about MBBCx, see [Mobile Broadband (MBB) WDF class extension](/windows-hardware/drivers/netcx/mobile-broadband-mbb-wdf-class-extension-mbbcx).

Header files that support MBBCx include the following:

- [Mbbcx.h](../mbbcx/index.md)

## Network Module Registrar

The Network Module Registrar (NMR) is an operating system module that facilitates the attachment of network modules to each other.

For more info about the NMR, see [Network Module Registrar](/windows-hardware/drivers/network/network-module-registrar2).

Header files that support the NMR include the following:

- [Netioddk.h](../netioddk/index.md)
- [Wsk.h](../wsk/index.md)

## Winsock Kernel (WSK)

Winsock Kernel (WSK) is the kernel mode component of Windows Sockets. 

For more info about WSK, see [Winsock Kernel](/windows-hardware/drivers/network/winsock-kernel4).

Header files that support WSK include the following:

- [Wsk.h](../wsk/index.md)

## Windows Filtering Platform Callout Drivers

Windows Filtering Platform Callout Drivers are network drivers that implement one or more callouts, which enable them to process TCP/IP-based network data in ways that are beyond simple filtering.

For more info about Windows Filtering Platform Callout Drivers, see [Windows Filtering Platform Callout Drivers](/windows-hardware/drivers/network/windows-filtering-platform-callout-drivers2).

Header files that support Windows Filtering Platform Callout Drivers include the following:

- [Fwpmk.h](../fwpmk/index.md)
- [Fwpsk.h](../fwpsk/index.md)