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
ms.keywords: SdpAddAttributeToTree function [Bluetooth Devices], SdpAddAttributeToTree, sdplib/SdpAddAttributeToTree, bth_funcs_5a46529e-8b1b-474a-a005-16f7a5562d91.xml, bltooth.sdpaddattributetotree
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sdplib.h
req.include-header: BthSdpddi.h
req.target-type: Desktop
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= PASSIVE_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	sdplib.h
apiname:
-	SdpAddAttributeToTree
product: Windows
targetos: Windows
req.typenames: PRINTIFI32, *PPRINTIFI32
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




### -param Tree

TBD


### -param AttribId [in]

The identifier of the attribute to attach.


### -param AttribValue

TBD


### -param tag [in]

Specifies a 4-byte 
     <a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">pool tag</a> that uniquely identifies the driver that does the memory
     allocation. For more information about pool tags, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff544520">ExAllocatePoolWithTag</a>.


#### - Root [in]

The top level of the SDP record to which the 
     <b>SdpAddAttributeToTree</b> function attaches the SDP attribute node.


#### - AttribValueNode [in]

Pointer to the SDP node to be added as an attribute.


## -returns


Possible return values include:



## -remarks


Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_node_interface.md">BTHDDI_SDP_NODE_INTERFACE</a>.

For more information about the tree structure, see 
    <mshelp:link keywords="bltooth.converting_sdp_records_to_a_tree_structure" tabindex="0">Converting SDP Records to a
    Tree Structure</mshelp:link>.



## -see-also

<a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_node_interface.md">BTHDDI_SDP_NODE_INTERFACE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20SdpAddAttributeToTree function%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

