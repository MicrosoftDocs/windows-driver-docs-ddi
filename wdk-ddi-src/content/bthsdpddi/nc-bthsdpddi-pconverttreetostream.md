---
UID: NC:bthsdpddi.PCONVERTTREETOSTREAM
title: PCONVERTTREETOSTREAM
description: The Bluetooth SdpConvertTreeToStream function is used to produce a raw bytestream representation of an SDP record from a tree representation. The raw bytestream version is suitable for publication on a local SDP server.
old-location: bltooth\sdpconverttreetostream.htm
tech.root: bltooth
ms.assetid: 6e3cc0ae-e214-4096-834b-b435ee0fcb46
ms.date: 04/27/2018
ms.keywords: PCONVERTTREETOSTREAM, PCONVERTTREETOSTREAM callback, SdpConvertTreeToStream, SdpConvertTreeToStream callback function [Bluetooth Devices], bltooth.sdpconverttreetostream, bth_funcs_0f0b531b-9391-475c-a3a2-ac2b2a94e1dd.xml, bthsdpddi/SdpConvertTreeToStream
ms.topic: callback
req.header: bthsdpddi.h
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
req.lib: 
req.dll: 
req.irql: "<= PASSIVE_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	BthSdpddi.h
api_name:
-	SdpConvertTreeToStream
product:
- Windows
targetos: Windows
req.typenames: 
---

# PCONVERTTREETOSTREAM callback function


## -description


The Bluetooth 
  <b>SdpConvertTreeToStream</b> function is used to produce a raw bytestream representation of an SDP record
  from a tree representation. The raw bytestream version is suitable for publication on a local SDP
  server.


## -parameters




### -param Root

The root node of the tree-based representation of the SDP record to convert into a stream-based
     representation.


### -param *Stream

A pointer to the buffer that receives the converted SDP stream.


### -param Size

The address of an unsigned long integer to receive the length of the converted SDP stream.


### -param tag

Specifies a 4-byte 
     <a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">pool tag</a> that uniquely identifies the driver that does the memory
     allocation. For more information about pool tags, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff544520">ExAllocatePoolWithTag</a>.


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
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536794">SdpConvertStreamToTree</a> function. It
    generates a complete native SDP record from a Microsoft-specific tree structure. Driver developers might
    find it more convenient to build a SDP record as a tree and then convert it to a stream prior to
    publishing.

<b>SdpConvertTreeToStream</b> allocates the necessary memory to store the stream version of the SDP
    record. When the memory is no longer needed, the caller is responsible for freeing the memory using the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff544590">ExFreePool</a> driver support routine.

Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536636">BTHDDI_SDP_PARSE_INTERFACE</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536636">BTHDDI_SDP_PARSE_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544590">ExFreePool</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536794">SdpConvertStreamToTree</a>
 

 

