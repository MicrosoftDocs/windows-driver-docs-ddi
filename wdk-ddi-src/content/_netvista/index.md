---
UID: TP:netvista
ms.assetid: 81753000-e53e-3c99-bde3-5c662c944380
ms.author: windowsdriverdev
ms.date: 04/03/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Networking drivers for Windows Vista and later

## -description

Overview of the Networking drivers for Windows Vista and later technology.

To develop Networking drivers for Windows Vista and later, you need these headers:

 * [arrayofelements.hpp](..\arrayofelements\index.md)
 * [atm.h](..\atm\index.md)
 * [backpack.h](..\backpack\index.md)
 * [dot11wdi.h](..\dot11wdi\index.md)
 * [fwpmk.h](..\fwpmk\index.md)
 * [fwpsk.h](..\fwpsk\index.md)
 * [knetpwrdepbroker.h](..\knetpwrdepbroker\index.md)
 * [mf.h](..\mf\index.md)
 * [ndis.h](..\ndis\index.md)
 * [ndischimney.h](..\ndischimney\index.md)
 * [ndisndk.h](..\ndisndk\index.md)
 * [ndiswwan.h](..\ndiswwan\index.md)
 * [ndkpi.h](..\ndkpi\index.md)
 * [ndkrss.h](..\ndkrss\index.md)
 * [netadapter.h](..\netadapter\index.md)
 * [netadaptercxtypes.h](..\netadaptercxtypes\index.md)
 * [netadapterpacket.h](..\netadapterpacket\index.md)
 * [netconfiguration.h](..\netconfiguration\index.md)
 * [netdatapathdescriptor.h](..\netdatapathdescriptor\index.md)
 * [netdma.h](..\netdma\index.md)
 * [netioddk.h](..\netioddk\index.md)
 * [netpacket.h](..\netpacket\index.md)
 * [netpnp.h](..\netpnp\index.md)
 * [netpowersettings.h](..\netpowersettings\index.md)
 * [netreceivescaling.h](..\netreceivescaling\index.md)
 * [netrequest.h](..\netrequest\index.md)
 * [netrequestqueue.h](..\netrequestqueue\index.md)
 * [netringbuffer.h](..\netringbuffer\index.md)
 * [netrxqueue.h](..\netrxqueue\index.md)
 * [nettxqueue.h](..\nettxqueue\index.md)
 * [ntddndis.h](..\ntddndis\index.md)
 * [ntddnlb.h](..\ntddnlb\index.md)
 * [ntddrilapitypes.h](..\ntddrilapitypes\index.md)
 * [oemrilapitypes.h](..\oemrilapitypes\index.md)
 * [rilapi.h](..\rilapi\index.md)
 * [rilapitypes.h](..\rilapitypes\index.md)
 * [tlvgenerated_.hpp](..\tlvgenerated_\index.md)
 * [tlvgeneratorparser.hpp](..\tlvgeneratorparser\index.md)
 * [vmbuskernelmodeclientlibapi.h](..\vmbuskernelmodeclientlibapi\index.md)
 * [wditypes.hpp](..\wditypes\index.md)
 * [windot11.h](..\windot11\index.md)
 * [wlanihv.h](..\wlanihv\index.md)
 * [wlanihvtypes.h](..\wlanihvtypes\index.md)
 * [wlantypes.h](..\wlantypes\index.md)
 * [wlclient.h](..\wlclient\index.md)
 * [wsk.h](..\wsk\index.md)
 * [wskndk.h](..\wskndk\index.md)
 * [wwan.h](..\wwan\index.md)
 * [xfilter.h](..\xfilter\index.md)

For the programming guide, see [Networking drivers for Windows Vista and later](===404===https://docs.microsoft.com/en-us/windows-hardware/drivers/netvista).

This section lists functions, callbacks, macros, structures, and enumerations used in Windows networking device drivers starting with Windows Vista. The header files that contain the topics defined in this section are included in the Windows Driver Kit (WDK).

The following sections contain information for each area of network driver technology:

## NetAdapterCx

Starting in Windows 10, version 1703, the Windows Driver Kit (WDK) includes a class extension module (NetAdapterCx) that enables you to write a KMDF-based networking (NDIS) client driver for Network Interface Cards (NICs).  The client driver interacts with NetAdapterCx, which acts as a bridge to traditional NDIS. 

For more info, see [Network Adapter WDF Class Extension (Cx)](https://docs.microsoft.com/windows-hardware/drivers/netcx/).

Header files that support NetAdapterCx include the following:

- [Netadapter.h](../netadapter/index.md)
- [Netadaptercxtypes.h](../netadaptercxtypes/index.md)
- [Netadapterpacket.h](../netadapterpacket/index.md)
- [Netconfiguration.h](../netconfiguration/index.md)
- [Netdatapathdescriptor.h](../netdatapathdescriptor/index.md)
- [Netpacket.h](../netpacket/index.md)
- [Netpnp.h](../netpnp/index.md)
- [Netpowersettings.h](../netpowersettings/index.md)
- [Netreceivescaling.h](../netreceivescaling/index.md)
- [Netrequest.h](../netrequest/index.md)
- [Netrequestqueue.h](../netrequestqueue/index.md)
- [Netringbuffer.h](../netringbuffer/index.md)
- [Netrxqueue.h](../netrxqueue/index.md)
- [Nettxqueue.h](../nettxqueue/index.md)

## NDIS Core Functionality

The foundation for all Windows network technologies is the Network Driver Interface Specification, or NDIS. NDIS forms the network driver platform that bridges the gap between the NIC and upper layers in the network stack.

For more info about NDIS Core Functionality, see [NDIS Core Functionality](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-core-functionality2).

Header files that support NDIS core functionality include the following:

- [Ndis.h](../ndis/index.md)
- [Ntddndis.h](../ntddndis/index.md)

## Scalable Networking

Windows includes technologies for scalable networking such as Header-Data Split, NetDMA, PacketDirect Provider Interface, Network Virtualization using Generic Routing Encapsulation (NVGRE) Task Offload, Receive Segment Coalescing (RSC), Receive Side Scaling (RSS), and TCP/IP offload.

For more info about scalable networking, see [Scalable Networking](https://docs.microsoft.com/windows-hardware/drivers/network/scalable-networking2).

Header files that support scalable networking include the following:

- [Ndis.h](../ndis/index.md)
- [Ndischimney.h](../ndischimney/index.md)
- [Ndisndk.h](../ndisndk/index.md)
- [Ndkpi.h](../ndkpi/index.md)
- [Netdma.h](../netdma/index.md)
- [Ntddndis.h](../ntddndis/index.md)

## Virtualized Networking

NDIS supports technologies for packet transfer and management within a Hyper-V virtual environment such as Single Root I/O Virtualization (SR-IOV), Virtual Machine Queue (VMQ), and Hyper-V Extensible Switch.

For more info about virtualized networking, see [Virtualized Networking](https://docs.microsoft.com/windows-hardware/drivers/network/virtualized-networking).

Header files that support virtualized networking include the following:

- [Ndis.h](../ndis/index.md)
- [Ntddndis.h](../ntddndis/index.md)
- [VmbusKernelModeClientLibApi.h](../vmbuskernelmodeclientlibapi/index.md)

## Wireless Networking

Windows network drivers support both Wi-Fi and Mobile Broadband. For Windows Vista, Windows 7, Windows 8, and Windows 8.1, Wi-Fi drivers use the Native 802.11 Wireless LAN model. For Windows 10, Wi-Fi drivers use the WLAN Universal Windows driver model, or WDI.

For more info about wireless networking, see [Wireless Networking](https://docs.microsoft.com/windows-hardware/drivers/network/wireless-networking2).

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

## Network Module Registrar

The Network Module Registrar (NMR) is an operating system module that facilitates the attachment of network modules to each other.

For more info about the NMR, see [Network Module Registrar](https://docs.microsoft.com/windows-hardware/drivers/network/network-module-registrar2).

Header files that support the NMR include the following:

- [Netioddk.h](../netioddk/index.md)
- [Wsk.h](../wsk/index.md)

## Winsock Kernel (WSK)

Winsock Kernel (WSK) is the kernel mode component of Windows Sockets. 

For more info about WSK, see [Winsock Kernel](https://docs.microsoft.com/windows-hardware/drivers/network/winsock-kernel4).

Header files that support WSK include the following:

- [Wsk.h](../wsk/index.md)

## Windows Filtering Platform Callout Drivers

Windows Filtering Platform Callout Drivers are network drivers that implement one or more callouts, which enable them to process TCP/IP-based network data in ways that are beyond simple filtering.

For more info about Windows Filtering Platform Callout Drivers, see [Windows Filtering Platform Callout Drivers](https://docs.microsoft.com/windows-hardware/drivers/network/windows-filtering-platform-callout-drivers2).

Header files that support Windows Filtering Platform Callout Drivers include the following:

- [Fwpmk.h](../fwpmk/index.md)
- [Fwpsk.h](../fwpsk/index.md)

