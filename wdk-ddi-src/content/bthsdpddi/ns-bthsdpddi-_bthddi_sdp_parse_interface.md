---
UID: NS:bthsdpddi._BTHDDI_SDP_PARSE_INTERFACE
title: _BTHDDI_SDP_PARSE_INTERFACE (bthsdpddi.h)
description: The BTHDDI_SDP_PARSE_INTERFACE structure provides functions for parsing SDP records.
old-location: bltooth\bthddi_sdp_parse_interface.htm
tech.root: bltooth
ms.assetid: bb8a1dd5-8207-4034-993e-eed49dc0f9c4
ms.date: 04/27/2018
keywords: ["_BTHDDI_SDP_PARSE_INTERFACE structure"]
ms.keywords: "*PBTHDDI_SDP_PARSE_INTERFACE, BTHDDI_SDP_PARSE_INTERFACE, BTHDDI_SDP_PARSE_INTERFACE structure [Bluetooth Devices], PBTHDDI_SDP_PARSE_INTERFACE, PBTHDDI_SDP_PARSE_INTERFACE structure pointer [Bluetooth Devices], _BTHDDI_SDP_PARSE_INTERFACE, bltooth.bthddi_sdp_parse_interface, bth_structs_9c26fcf9-b84e-4b8d-a6bd-f897428cb921.xml, bthsdpddi/BTHDDI_SDP_PARSE_INTERFACE, bthsdpddi/PBTHDDI_SDP_PARSE_INTERFACE"
f1_keywords:
 - "bthsdpddi/BTHDDI_SDP_PARSE_INTERFACE"
req.header: bthsdpddi.h
req.include-header: BthSdpddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- bthsdpddi.h
api_name:
- BTHDDI_SDP_PARSE_INTERFACE
product:
- Windows
targetos: Windows
req.typenames: BTHDDI_SDP_PARSE_INTERFACE, *PBTHDDI_SDP_PARSE_INTERFACE
---

# _BTHDDI_SDP_PARSE_INTERFACE structure


## -description


The BTHDDI_SDP_PARSE_INTERFACE structure provides functions for parsing SDP records.


## -struct-fields




### -field Interface

A structure that describes the 
     <b>BTHDDI_SDP_NODE_INTERFACE</b> interface for use by profile drivers. For more information about this
     structure, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a>.


### -field SdpValidateStream

A pointer to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/nc-bthsdpddi-pvalidatestream">SdpValidateStream</a> function.


### -field SdpConvertStreamToTree

A pointer to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/nc-bthsdpddi-pconvertstreamtotree">
     SdpConvertStreamToTree</a> function.


### -field SdpConvertTreeToStream

A pointer to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/nc-bthsdpddi-pconverttreetostream">
     SdpConvertTreeToStream</a> function.


### -field SdpFreeTree

A pointer to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sdplib/nf-sdplib-sdpfreetree">SdpFreeTree</a> function.


### -field SdpByteSwapUuid128

A pointer to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/nc-bthsdpddi-pbyteswapuuid128">SdpByteSwapUuid128</a> function.


### -field SdpByteSwapUint128

A pointer to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/nc-bthsdpddi-pbyteswapuint128">SdpByteSwapUint128</a> function.


### -field SdpByteSwapUint64

A pointer to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/nc-bthsdpddi-pbyteswapuint64">SdpByteSwapUint64</a> function.


### -field SdpRetrieveUuid128

A pointer to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/nc-bthsdpddi-pretrieveuuid128">SdpRetrieveUuid128</a> function.


### -field SdpRetrieveUint128

A pointer to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/nc-bthsdpddi-pretrieveuint64">SdpRetrieveUint128</a> function.


### -field SdpRetrieveUint64

A pointer to the 
     <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff536845(v=vs.85)">SdpRetrieveUint64</a> function.


### -field SdpFindAttributeInTree

A pointer to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sdplib/nf-sdplib-sdpfindattributeintree">
     SdpFindAttributeInTree</a> function.


### -field SdpGetNextElement

A pointer to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/nc-bthsdpddi-pgetnextelement">SdpGetNextElement</a> function.


### -field Reserved1

Reserved for future use. Do not use.


### -field Reserved2

Reserved for future use. Do not use.


### -field Reserved3

Reserved for future use. Do not use.


### -field Reserved4

Reserved for future use. Do not use.


## -remarks



Profile drivers should specify the 
    <b>GUID_BTHDDI_SDP_PARSE_INTERFACE</b> GUID to query for an instance of the BTHDDI_SDP_PARSE_INTERFACE
    structure from the Bluetooth driver stack.

All the members of this structure, other than the 
    <b>Interface</b> member, are function pointers.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/nc-bthsdpddi-pbyteswapuint128">SdpByteSwapUint128</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/nc-bthsdpddi-pbyteswapuint64">SdpByteSwapUint64</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/nc-bthsdpddi-pbyteswapuuid128">SdpByteSwapUuid128</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/nc-bthsdpddi-pconvertstreamtotree">SdpConvertStreamToTree</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/nc-bthsdpddi-pconverttreetostream">SdpConvertTreeToStream</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sdplib/nf-sdplib-sdpfindattributeintree">SdpFindAttributeInTree</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sdplib/nf-sdplib-sdpfreetree">SdpFreeTree</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/nc-bthsdpddi-pgetnextelement">SdpGetNextElement</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/nc-bthsdpddi-pretrieveuint64">SdpRetrieveUint128</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff536845(v=vs.85)">SdpRetrieveUint64</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/nc-bthsdpddi-pretrieveuuid128">SdpRetrieveUuid128</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/nc-bthsdpddi-pvalidatestream">SdpValidateStream</a>
 

 

