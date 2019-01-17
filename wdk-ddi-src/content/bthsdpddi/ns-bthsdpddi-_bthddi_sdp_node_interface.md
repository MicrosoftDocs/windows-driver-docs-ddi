---
UID: NS:bthsdpddi._BTHDDI_SDP_NODE_INTERFACE
title: "_BTHDDI_SDP_NODE_INTERFACE"
description: The BTHDDI_SDP_NODE_INTERFACE structure provides functions for manipulating SDP records, including converting them to and from a tree representation that profile drivers can more easily parse.
old-location: bltooth\bthddi_sdp_node_interface.htm
tech.root: bltooth
ms.assetid: c9aeaaed-f017-4b23-b867-d704c4f8afb6
ms.date: 04/27/2018
ms.keywords: "*PBTHDDI_SDP_NODE_INTERFACE, BTHDDI_SDP_NODE_INTERFACE, BTHDDI_SDP_NODE_INTERFACE structure [Bluetooth Devices], PBTHDDI_SDP_NODE_INTERFACE, PBTHDDI_SDP_NODE_INTERFACE structure pointer [Bluetooth Devices], _BTHDDI_SDP_NODE_INTERFACE, bltooth.bthddi_sdp_node_interface, bth_structs_54f8f76d-9f12-491d-b189-c4e2fdd9b364.xml, bthsdpddi/BTHDDI_SDP_NODE_INTERFACE, bthsdpddi/PBTHDDI_SDP_NODE_INTERFACE"
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
-	BTHDDI_SDP_NODE_INTERFACE
product:
- Windows
targetos: Windows
req.typenames: BTHDDI_SDP_NODE_INTERFACE, *PBTHDDI_SDP_NODE_INTERFACE
---

# _BTHDDI_SDP_NODE_INTERFACE structure


## -description


The BTHDDI_SDP_NODE_INTERFACE structure provides functions for manipulating SDP records, including
  converting them to and from a tree representation that profile drivers can more easily parse.


## -struct-fields




### -field Interface

A structure that describes the 
     <b>BTHDDI_SDP_NODE_INTERFACE</b> interface for use by profile drivers. For more information about this
     structure, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/dn895657">INTERFACE</a>.


### -field SdpCreateNodeTree

A pointer to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536818">SdpCreateNodeTree</a> function.


### -field SdpFreeTree

A pointer to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536839">SdpFreeTree</a> function
     <i>.</i>


### -field SdpCreateNodeNil

A pointer to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536812">SdpCreateNodeNil</a> function.


### -field SdpCreateNodeBoolean

A pointer to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536801">SdpCreateNodeBoolean</a> function.


### -field SdpCreateNodeUint8

A pointer to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536828">SdpCreateNodeUInt8</a> function.


### -field SdpCreateNodeUint16

A pointer to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536822">SdpCreateNodeUInt16</a> function.


### -field SdpCreateNodeUint32

A pointer to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536824">SdpCreateNodeUInt32</a> function.


### -field SdpCreateNodeUint64

A pointer to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536827">SdpCreateNodeUInt64</a> function.


### -field SdpCreateNodeUint128

A pointer to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536819">SdpCreateNodeUInt128</a> function.


### -field SdpCreateNodeInt8

A pointer to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536811">SdpCreateNodeInt8</a> function.


### -field SdpCreateNodeInt16

A pointer to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536804">SdpCreateNodeInt16</a> function.


### -field SdpCreateNodeInt32

A pointer to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536806">SdpCreateNodeInt32</a> function.


### -field SdpCreateNodeInt64

A pointer to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536808">SdpCreateNodeInt64</a> function.


### -field SdpCreateNodeInt128

A pointer to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536802">SdpCreateNodeInt128</a> function.


### -field SdpCreateNodeUuid16

A pointer to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536835">SdpCreateNodeUUID16</a> function.


### -field SdpCreateNodeUuid32

A pointer to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536836">SdpCreateNodeUUID32</a> function.


### -field SdpCreateNodeUuid128

A pointer to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536833">SdpCreateNodeUUID128</a> function.


### -field SdpCreateNodeString

A pointer to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536816">SdpCreateNodeString</a> function.


### -field SdpCreateNodeUrl

A pointer to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536831">SdpCreateNodeUrl</a> function.


### -field SdpCreateNodeAlternative

A pointer to the 
     <a href="https://msdn.microsoft.com/1e6b922d-01a2-4a67-91cb-74956d40d769">
     SdpCreateNodeAlternative</a> function.


### -field SdpCreateNodeSequence

A pointer to the 
     <a href="https://msdn.microsoft.com/9e02f32b-cd39-4953-9698-a1800bedf0e2">
     SdpCreateNodeSequence</a> function.


### -field SdpAddAttributeToTree

A pointer to the 
     <a href="https://msdn.microsoft.com/f5b72de2-c2e9-44ac-a2a7-04271e9253d3">
     SdpAddAttributeToTree</a> function.


### -field SdpAppendNodeToContainerNode

A pointer to the 
     <a href="https://msdn.microsoft.com/beec5516-6191-4b70-8c80-ddbaedbad5c0">
     SdpAppendNodeToContainerNode</a> function.


## -remarks



Profile drivers should specify the 
    <b>GUID_BTHDDI_SDP_NODE_INTERFACE</b> GUID to query for an instance of the BTHDDI_SDP_NODE_INTERFACE
    structure from the Bluetooth driver stack.

All the members of this structure, other than the 
    <b>Interface</b> member, are function pointers.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn895657">INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536784">SdpAddAttributeToTree</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536786">SdpAppendNodeToContainerNode</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536798">SdpCreateNodeAlternative</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536801">SdpCreateNodeBoolean</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536802">SdpCreateNodeInt128</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536804">SdpCreateNodeInt16</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536806">SdpCreateNodeInt32</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536808">SdpCreateNodeInt64</a>



<b>SdpCreateNodeInt8</b>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536812">SdpCreateNodeNil</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536814">SdpCreateNodeSequence</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536816">SdpCreateNodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536818">SdpCreateNodeTree</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536819">SdpCreateNodeUInt128</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536822">SdpCreateNodeUInt16</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536824">SdpCreateNodeUInt32</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536827">SdpCreateNodeUInt64</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536828">SdpCreateNodeUInt8</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536833">SdpCreateNodeUUID128</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536835">SdpCreateNodeUUID16</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536836">SdpCreateNodeUUID32</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536831">SdpCreateNodeUrl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536839">SdpFreeTree</a>
 

 

