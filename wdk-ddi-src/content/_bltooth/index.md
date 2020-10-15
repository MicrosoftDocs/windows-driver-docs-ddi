---
UID: TP:bltooth
title: Bluetooth
ms.assetid: a24d2124-fb4a-3c14-aeb8-83c46e9ed71c
ms.date: 05/09/2018
keywords: ["Bluetooth"]
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Bluetooth

## -description

Overview of the Bluetooth technology.

To develop Bluetooth, you need these headers:

 * [bthddi.h](../bthddi/index.md)
 * [bthioctl.h](../bthioctl/index.md)
 * [bthsdpddi.h](../bthsdpddi/index.md)
 * [bthxddi.h](../bthxddi/index.md)
 * [sdplib.h](../sdplib/index.md)
 * [sdpnode.h](../sdpnode/index.md)

For the programming guide, see [Bluetooth](/windows-hardware/drivers/bluetooth).

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [PBYTESWAPUINT128](../bthsdpddi/nc-bthsdpddi-pbyteswapuint128.md) | The Bluetooth SdpByteSwapUint128 function is used to reverse the byte order of an unsigned 128-bit integer. |
| [PBYTESWAPUINT64](../bthsdpddi/nc-bthsdpddi-pbyteswapuint64.md) | The Bluetooth SdpByteSwapUint64 function is used to reverse the byte order of an unsigned 64-bit integer. |
| [PBYTESWAPUUID128](../bthsdpddi/nc-bthsdpddi-pbyteswapuuid128.md) | The Bluetooth SdpByteSwapUuid128 function is used to reverse the byte order of a 128-bit universally unique identifier (UUID). |
| [PCONVERTSTREAMTOTREE](../bthsdpddi/nc-bthsdpddi-pconvertstreamtotree.md) | The Bluetooth SdpConvertStreamToTree function is used to create a Microsoft proprietary tree-based representation of an SDP record, while leaving the original stream-based representation unmodified. |
| [PCONVERTTREETOSTREAM](../bthsdpddi/nc-bthsdpddi-pconverttreetostream.md) | The Bluetooth SdpConvertTreeToStream function is used to produce a raw bytestream representation of an SDP record from a tree representation. The raw bytestream version is suitable for publication on a local SDP server. |
| [PFNBTHPORT_INDICATION_CALLBACK](../bthddi/nc-bthddi-pfnbthport_indication_callback.md) | Profile drivers implement a L2CAP callback function to provide the Bluetooth driver stack with a mechanism to notify the profile driver about incoming L2CAP connection requests from remote devices, and any changes to the status of a currently open L2CAP connection. |
| [PFNBTHPORT_INDICATION_CALLBACK_ENHANCED](../bthddi/nc-bthddi-pfnbthport_indication_callback_enhanced.md) | Profile drivers implement an enhanced L2CAP callback function to provide the Bluetooth driver stack with a mechanism to notify the profile driver about any changes to the status of a currently open L2CAP or eL2CAP connection. |
| [PFNBTH_ALLOCATE_BRB](../bthddi/nc-bthddi-pfnbth_allocate_brb.md) | The BthAllocateBrb function allocates a Bluetooth request block (BRB) of the specified type. |
| [PFNBTH_FREE_BRB](../bthddi/nc-bthddi-pfnbth_free_brb.md) | The BthFreeBrb function frees a Bluetooth request block (BRB) that was allocated previously with BthAllocateBrb. |
| [PFNBTH_INITIALIZE_BRB](../bthddi/nc-bthddi-pfnbth_initialize_brb.md) | The BthInitializeBrb function initializes a Bluetooth request block (BRB) allocated on the local stack. |
| [PFNBTH_IS_BLUETOOTH_VERSION_AVAILABLE](../bthddi/nc-bthddi-pfnbth_is_bluetooth_version_available.md) | The IsBluetoothVersionAvailable function checks whether a given Bluetooth version is supported by the operating system. |
| [PFNBTH_REUSE_BRB](../bthddi/nc-bthddi-pfnbth_reuse_brb.md) | The BthReuseBrb function reinitializes a Bluetooth request block (BRB) to be reused. |
| [PFNSCO_INDICATION_CALLBACK](../bthddi/nc-bthddi-pfnsco_indication_callback.md) | Profile drivers implement a SCO callback function to provide the Bluetooth driver stack with a mechanism to notify the profile driver about incoming SCO connection requests from remote devices, and any changes to the status of a currently open SCO connection. |
| [PGETNEXTELEMENT](../bthsdpddi/nc-bthsdpddi-pgetnextelement.md) | The Bluetooth SdpGetNextElement function is used to iterate through the entries found in an SDP record stream. |
| [PRETRIEVEUINT64](../bthsdpddi/nc-bthsdpddi-pretrieveuint64.md) | The Bluetooth SdpRetrieveUint64 function is used to copy an unaligned 64-bit integer from an SDP stream. |
| [PRETRIEVEUUID128](../bthsdpddi/nc-bthsdpddi-pretrieveuuid128.md) | The Bluetooth SdpRetrieveUuid128 function is used to copy an unaligned 128-bit universally unique identifier (UUID) from an SDP stream. |
| [PVALIDATESTREAM](../bthsdpddi/nc-bthsdpddi-pvalidatestream.md) | The Bluetooth SdpValidateStream function is used to parse a raw SDP record and determine if it contains errors. |
