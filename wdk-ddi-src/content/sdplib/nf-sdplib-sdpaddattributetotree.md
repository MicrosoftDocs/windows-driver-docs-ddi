---
UID: NF:sdplib.SdpAddAttributeToTree
title: SdpAddAttributeToTree function
author: windows-driver-content
description: The Bluetooth SdpAddAttributeToTree function is used to attach an SDP attribute node to the top level of an SDP record.
old-location: bltooth\sdpaddattributetotree.htm
old-project: bltooth
ms.assetid: f5b72de2-c2e9-44ac-a2a7-04271e9253d3
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: SdpAddAttributeToTree
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sdplib.h
req.include-header: BthSdpddi.h
req.target-type: Desktop
req.target-min-winverclnt: Versions: Supported in Windows Vista, and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SdpAddAttributeToTree
req.alt-loc: sdplib.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= PASSIVE_LEVEL
req.typenames: *PSDCMD_DESCRIPTOR, SDCMD_DESCRIPTOR
req.product: Windows 10 or later.
---

# SdpAddAttributeToTree function



## -description
The Bluetooth 
   <b>SdpAddAttributeToTree</b> function is used to attach an SDP attribute node to the top level of an SDP
  record.



## -syntax

````
NTSTATUS SdpAddAttributeToTree(
  _In_ PSDP_TREE_ROOT_NODE Root,
  _In_ USHORT              AttribId,
  _In_ PSDP_NODE           AttribValueNode,
  _In_ ULONG               tag
);
````


## -parameters

### -param Root [in]

The top level of the SDP record to which the 
     <b>SdpAddAttributeToTree</b> function attaches the SDP attribute node.


### -param AttribId [in]

The identifier of the attribute to attach.


### -param AttribValueNode [in]

Pointer to the SDP node to be added as an attribute.


### -param tag [in]

Specifies a 4-byte 
     <a href="wdkgloss.p#wdkgloss.pool_tag#wdkgloss.pool_tag"><i>pool tag</i></a> that uniquely identifies the driver that does the memory
     allocation. For more information about pool tags, see 
     <a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>.


## -returns
Possible return values include:


## -remarks
Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_node_interface.md">BTHDDI_SDP_NODE_INTERFACE</a>.

For more information about the tree structure, see 
    <a href="https://msdn.microsoft.com/762cf68b-0082-4b9e-8f24-ff19ecf6f8bd">Converting SDP Records to a
    Tree Structure</a>.


## -see-also
<dl>
<dt>
<a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_node_interface.md">BTHDDI_SDP_NODE_INTERFACE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20SdpAddAttributeToTree function%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

