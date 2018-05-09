---
UID: NS:bthsdpddi._BTHDDI_SDP_PARSE_INTERFACE
title: "_BTHDDI_SDP_PARSE_INTERFACE"
author: windows-driver-content
description: The BTHDDI_SDP_PARSE_INTERFACE structure provides functions for parsing SDP records.
old-location: bltooth\bthddi_sdp_parse_interface.htm
old-project: bltooth
ms.assetid: bb8a1dd5-8207-4034-993e-eed49dc0f9c4
ms.author: windowsdriverdev
ms.date: 4/27/2018
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bthsdpddi.h
api_name:
-	BTHDDI_SDP_PARSE_INTERFACE
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
     <a href="https://msdn.microsoft.com/library/windows/hardware/dn895657">INTERFACE</a>.


### -field SdpValidateStream

A pointer to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536847">SdpValidateStream</a> function.


### -field SdpConvertStreamToTree

A pointer to the 
     <a href="https://msdn.microsoft.com/3b285a32-c1bc-4103-aa2e-0f6c8f5cc7ec">
     SdpConvertStreamToTree</a> function.


### -field SdpConvertTreeToStream

A pointer to the 
     <a href="https://msdn.microsoft.com/6e3cc0ae-e214-4096-834b-b435ee0fcb46">
     SdpConvertTreeToStream</a> function.


### -field SdpFreeTree

A pointer to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536839">SdpFreeTree</a> function.


### -field SdpByteSwapUuid128

A pointer to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536793">SdpByteSwapUuid128</a> function.


### -field SdpByteSwapUint128

A pointer to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536788">SdpByteSwapUint128</a> function.


### -field SdpByteSwapUint64

A pointer to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536790">SdpByteSwapUint64</a> function.


### -field SdpRetrieveUuid128

A pointer to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536846">SdpRetrieveUuid128</a> function.


### -field SdpRetrieveUint128

A pointer to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536843">SdpRetrieveUint128</a> function.


### -field SdpRetrieveUint64

A pointer to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536845">SdpRetrieveUint64</a> function.


### -field SdpFindAttributeInTree

A pointer to the 
     <a href="https://msdn.microsoft.com/26c71c08-3b9a-474f-a232-d7f675582d27">
     SdpFindAttributeInTree</a> function.


### -field SdpGetNextElement

A pointer to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536841">SdpGetNextElement</a> function.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/dn895657">INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536788">SdpByteSwapUint128</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536790">SdpByteSwapUint64</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536793">SdpByteSwapUuid128</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536794">SdpConvertStreamToTree</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536796">SdpConvertTreeToStream</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536838">SdpFindAttributeInTree</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536839">SdpFreeTree</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536841">SdpGetNextElement</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536843">SdpRetrieveUint128</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536845">SdpRetrieveUint64</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536846">SdpRetrieveUuid128</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536847">SdpValidateStream</a>
 

 

