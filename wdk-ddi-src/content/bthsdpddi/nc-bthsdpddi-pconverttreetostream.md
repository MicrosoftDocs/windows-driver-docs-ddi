---
UID: NC:bthsdpddi.PCONVERTTREETOSTREAM
title: PCONVERTTREETOSTREAM
author: windows-driver-content
description: The Bluetooth SdpConvertTreeToStream function is used to produce a raw bytestream representation of an SDP record from a tree representation. The raw bytestream version is suitable for publication on a local SDP server.
old-location: bltooth\sdpconverttreetostream.htm
old-project: bltooth
ms.assetid: 6e3cc0ae-e214-4096-834b-b435ee0fcb46
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: bltooth.sdpconverttreetostream, SdpConvertTreeToStream callback function [Bluetooth Devices], SdpConvertTreeToStream, PCONVERTTREETOSTREAM, PCONVERTTREETOSTREAM, bthsdpddi/SdpConvertTreeToStream, bth_funcs_0f0b531b-9391-475c-a3a2-ac2b2a94e1dd.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: bthsdpddi.h
req.include-header: BthSdpddi.h
req.target-type: Desktop
req.target-min-winverclnt: Versions: Supported in Windows Vista, and later.
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
req.irql: <= PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	BthSdpddi.h
apiname: 
-	SdpConvertTreeToStream
product: Windows
targetos: Windows
req.typenames: *PBTH_VENDOR_SPECIFIC_COMMAND, BTH_VENDOR_SPECIFIC_COMMAND
---

# PCONVERTTREETOSTREAM callback


## -description


The Bluetooth 
  <b>SdpConvertTreeToStream</b> function is used to produce a raw bytestream representation of an SDP record
  from a tree representation. The raw bytestream version is suitable for publication on a local SDP
  server.


## -prototype


````
PCONVERTTREETOSTREAM SdpConvertTreeToStream;

NTSTATUS SdpConvertTreeToStream(
   PSDP_TREE_ROOT_NODE Root,
   PUCHAR              Stream,
   PULONG              Size,
   ULONG               tag
)
{ ... }
````


## -parameters




### -param Root

The root node of the tree-based representation of the SDP record to convert into a stream-based
     representation.


### -param *Stream



### -param Size

The address of an unsigned long integer to receive the length of the converted SDP stream.


### -param tag

Specifies a 4-byte 
     <a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">pool tag</a> that uniquely identifies the driver that does the memory
     allocation. For more information about pool tags, see 
     <a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>.


#### - Stream

A pointer to the buffer that receives the converted SDP stream.


## -returns


Possible return values include:


<dl>
<dt>STATUS_SUCCESS
      </dt>
<dt>STATUS_INSUFFICIENT_RESOURCES
      </dt>
<dt>STATUS_INVALID_PARAMETER</dt>
</dl>




## -remarks


The 
    <b>SdpConvertTreeToStream</b> function performs the opposite operation as the 
    <a href="..\bthsdpddi\nc-bthsdpddi-pconvertstreamtotree.md">SdpConvertStreamToTree</a> function. It
    generates a complete native SDP record from a Microsoft-specific tree structure. Driver developers might
    find it more convenient to build a SDP record as a tree and then convert it to a stream prior to
    publishing.

<b>SdpConvertTreeToStream</b> allocates the necessary memory to store the stream version of the SDP
    record. When the memory is no longer needed, the caller is responsible for freeing the memory using the 
    <a href="..\wdm\nf-wdm-exfreepool.md">ExFreePool</a> driver support routine.

Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_parse_interface.md">BTHDDI_SDP_PARSE_INTERFACE</a>.



## -see-also

<a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_parse_interface.md">BTHDDI_SDP_PARSE_INTERFACE</a>

<a href="..\bthsdpddi\nc-bthsdpddi-pconvertstreamtotree.md">SdpConvertStreamToTree</a>

<a href="..\wdm\nf-wdm-exfreepool.md">ExFreePool</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20PCONVERTTREETOSTREAM callback function%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

