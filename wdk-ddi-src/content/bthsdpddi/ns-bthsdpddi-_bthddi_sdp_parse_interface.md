---
UID: NS:bthsdpddi._BTHDDI_SDP_PARSE_INTERFACE
title: "_BTHDDI_SDP_PARSE_INTERFACE"
author: windows-driver-content
description: The BTHDDI_SDP_PARSE_INTERFACE structure provides functions for parsing SDP records.
old-location: bltooth\bthddi_sdp_parse_interface.htm
old-project: bltooth
ms.assetid: bb8a1dd5-8207-4034-993e-eed49dc0f9c4
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PBTHDDI_SDP_PARSE_INTERFACE, BTHDDI_SDP_PARSE_INTERFACE, BTHDDI_SDP_PARSE_INTERFACE structure [Bluetooth Devices], PBTHDDI_SDP_PARSE_INTERFACE, PBTHDDI_SDP_PARSE_INTERFACE structure pointer [Bluetooth Devices], _BTHDDI_SDP_PARSE_INTERFACE, bltooth.bthddi_sdp_parse_interface, bth_structs_9c26fcf9-b84e-4b8d-a6bd-f897428cb921.xml, bthsdpddi/BTHDDI_SDP_PARSE_INTERFACE, bthsdpddi/PBTHDDI_SDP_PARSE_INTERFACE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: "<= PASSIVE_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bthsdpddi.h
api_name:
-	BTHDDI_SDP_PARSE_INTERFACE
product: Windows
targetos: Windows
req.typenames: BTHDDI_SDP_PARSE_INTERFACE, *PBTHDDI_SDP_PARSE_INTERFACE
---

# _BTHDDI_SDP_PARSE_INTERFACE structure


## -description


The BTHDDI_SDP_PARSE_INTERFACE structure provides functions for parsing SDP records.


## -syntax


````
typedef struct _BTHDDI_SDP_PARSE_INTERFACE {
  INTERFACE            Interface;
  PVALIDATESTREAM      SdpValidateStream;
  PCONVERTSTREAMTOTREE SdpConvertStreamToTree;
  PCONVERTTREETOSTREAM SdpConvertTreeToStream;
  PFREETREE            SdpFreeTree;
  PBYTESWAPUUID128     SdpByteSwapUuid128;
  PBYTESWAPUINT128     SdpByteSwapUint128;
  PBYTESWAPUINT64      SdpByteSwapUint64;
  PRETRIEVEUUID128     SdpRetrieveUuid128;
  PRETRIEVEUINT128     SdpRetrieveUint128;
  PRETRIEVEUINT64      SdpRetrieveUint64;
  PFINDATTRIBUTEINTREE SdpFindAttributeInTree;
  PGETNEXTELEMENT      SdpGetNextElement;
  pReservedFunction    Reserved1;
  pReservedFunction    Reserved2;
  pReservedFunction    Reserved3;
  pReservedFunction    Reserved4;
} BTHDDI_SDP_PARSE_INTERFACE, *PBTHDDI_SDP_PARSE_INTERFACE;
````


## -struct-fields




### -field Interface

A structure that describes the 
     <b>BTHDDI_SDP_NODE_INTERFACE</b> interface for use by profile drivers. For more information about this
     structure, see 
     <a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a>.


### -field SdpValidateStream

A pointer to the 
     <a href="..\bthsdpddi\nc-bthsdpddi-pvalidatestream.md">SdpValidateStream</a> function.


### -field SdpConvertStreamToTree

A pointer to the 
     <a href="..\bthsdpddi\nc-bthsdpddi-pconvertstreamtotree.md">
     SdpConvertStreamToTree</a> function.


### -field SdpConvertTreeToStream

A pointer to the 
     <a href="..\bthsdpddi\nc-bthsdpddi-pconverttreetostream.md">
     SdpConvertTreeToStream</a> function.


### -field SdpFreeTree

A pointer to the 
     <a href="..\sdplib\nf-sdplib-sdpfreetree.md">SdpFreeTree</a> function.


### -field SdpByteSwapUuid128

A pointer to the 
     <a href="..\bthsdpddi\nc-bthsdpddi-pbyteswapuuid128.md">SdpByteSwapUuid128</a> function.


### -field SdpByteSwapUint128

A pointer to the 
     <a href="..\bthsdpddi\nc-bthsdpddi-pbyteswapuint128.md">SdpByteSwapUint128</a> function.


### -field SdpByteSwapUint64

A pointer to the 
     <a href="..\bthsdpddi\nc-bthsdpddi-pbyteswapuint64.md">SdpByteSwapUint64</a> function.


### -field SdpRetrieveUuid128

A pointer to the 
     <a href="..\bthsdpddi\nc-bthsdpddi-pretrieveuuid128.md">SdpRetrieveUuid128</a> function.


### -field SdpRetrieveUint128

A pointer to the 
     <a href="..\bthsdpddi\nc-bthsdpddi-pretrieveuint64.md">SdpRetrieveUint128</a> function.


### -field SdpRetrieveUint64

A pointer to the 
     <a href="..\bthsdpddi\nc-bthsdpddi-pretrieveuint64.md">SdpRetrieveUint64</a> function.


### -field SdpFindAttributeInTree

A pointer to the 
     <a href="..\sdplib\nf-sdplib-sdpfindattributeintree.md">
     SdpFindAttributeInTree</a> function.


### -field SdpGetNextElement

A pointer to the 
     <a href="..\bthsdpddi\nc-bthsdpddi-pgetnextelement.md">SdpGetNextElement</a> function.


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

<a href="..\bthsdpddi\nc-bthsdpddi-pconverttreetostream.md">SdpConvertTreeToStream</a>



<a href="..\bthsdpddi\nc-bthsdpddi-pgetnextelement.md">SdpGetNextElement</a>



<a href="..\bthsdpddi\nc-bthsdpddi-pconvertstreamtotree.md">SdpConvertStreamToTree</a>



<a href="..\bthsdpddi\nc-bthsdpddi-pbyteswapuint128.md">SdpByteSwapUint128</a>



<a href="..\bthsdpddi\nc-bthsdpddi-pvalidatestream.md">SdpValidateStream</a>



<a href="..\bthsdpddi\nc-bthsdpddi-pbyteswapuuid128.md">SdpByteSwapUuid128</a>



<a href="..\sdplib\nf-sdplib-sdpfindattributeintree.md">SdpFindAttributeInTree</a>



<a href="..\bthsdpddi\nc-bthsdpddi-pretrieveuint64.md">SdpRetrieveUint128</a>



<a href="..\bthsdpddi\nc-bthsdpddi-pretrieveuint64.md">SdpRetrieveUint64</a>



<a href="..\bthsdpddi\nc-bthsdpddi-pbyteswapuint64.md">SdpByteSwapUint64</a>



<a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a>



<a href="..\bthsdpddi\nc-bthsdpddi-pretrieveuuid128.md">SdpRetrieveUuid128</a>



<a href="..\sdplib\nf-sdplib-sdpfreetree.md">SdpFreeTree</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20BTHDDI_SDP_PARSE_INTERFACE structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

