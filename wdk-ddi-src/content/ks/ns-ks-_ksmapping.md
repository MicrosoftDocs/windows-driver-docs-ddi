---
UID: NS:ks._KSMAPPING
title: "_KSMAPPING"
author: windows-driver-content
description: The KSMAPPING structure is used to describe a single contiguous chunk of physical memory for use in scatter/gather DMA operations.
old-location: stream\ksmapping.htm
old-project: stream
ms.assetid: 9a5149dc-5506-4100-80fc-7cd17585d2af
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ks/PKSMAPPING, PKSMAPPING, avstruct_65f80fd5-14a6-431b-a1b6-e6c3d18302d3.xml, ks/KSMAPPING, _KSMAPPING, stream.ksmapping, PKSMAPPING structure pointer [Streaming Media Devices], *PKSMAPPING, KSMAPPING structure [Streaming Media Devices], KSMAPPING
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	KSMAPPING
product: Windows
targetos: Windows
req.typenames: KSMAPPING, *PKSMAPPING
---

# _KSMAPPING structure


## -description


The KSMAPPING structure is used to describe a single contiguous chunk of physical memory for use in scatter/gather DMA operations. 


## -syntax


````
typedef struct _KSMAPPING {
  PHYSICAL_ADDRESS PhysicalAddress;
  ULONG            ByteCount;
  ULONG            Alignment;
} KSMAPPING, *PKSMAPPING;
````


## -struct-fields





#### - PhysicalAddress

This member contains the physical address of this piece of the data frame.


#### - ByteCount

This member contains the number of bytes of contiguous physical memory in this individual mapping.


#### - Alignment

This member specifies the memory alignment in bytes for this buffer.


## -remarks


In order for minidrivers to use this structure within the stream pointer offsets, the pin for which this is referring must specify scatter/gather DMA mapping generation through KSPIN_FLAG_GENERATE_MAPPINGS and the client must register its DMA adapter object with AVStream using <b>KsDeviceRegisterAdapterObject</b>. See <a href="https://msdn.microsoft.com/ba1c525b-26b0-4778-b58b-f4169cfb972e">AVStream DMA Services</a>. The KSPIN_FLAG_GENERATE_MAPPINGS flag is defined on the <a href="..\ks\ns-ks-_kspin_descriptor_ex.md">KSPIN_DESCRIPTOR_EX</a> reference page.



## -see-also

<a href="..\ks\nf-ks-ksdeviceregisteradapterobject.md">KsDeviceRegisterAdapterObject</a>

<a href="..\ks\ns-ks-_ksstream_pointer_offset.md">KSSTREAM_POINTER_OFFSET</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSMAPPING structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

