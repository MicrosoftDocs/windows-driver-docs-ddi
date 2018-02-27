---
UID: NS:bdamedia.tagKS_DATARANGE_BDA_TRANSPORT
title: tagKS_DATARANGE_BDA_TRANSPORT
author: windows-driver-content
description: The KS_DATARANGE_BDA_TRANSPORT structure describes a range of data formats for a BDA transport stream.
old-location: stream\ks_datarange_bda_transport.htm
old-project: stream
ms.assetid: cd7dbcfa-f339-421a-9cc6-f4c494f13a41
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKS_DATARANGE_BDA_TRANSPORT, KS_DATARANGE_BDA_TRANSPORT, KS_DATARANGE_BDA_TRANSPORT structure [Streaming Media Devices], PKS_DATARANGE_BDA_TRANSPORT, PKS_DATARANGE_BDA_TRANSPORT structure pointer [Streaming Media Devices], bdamedia/KS_DATARANGE_BDA_TRANSPORT, bdamedia/PKS_DATARANGE_BDA_TRANSPORT, bdaref_89717b68-2829-4f7a-bcdb-10e0b790308c.xml, stream.ks_datarange_bda_transport, tagKS_DATARANGE_BDA_TRANSPORT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bdamedia.h
req.include-header: Bdamedia.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	bdamedia.h
apiname:
-	KS_DATARANGE_BDA_TRANSPORT
product: Windows
targetos: Windows
req.typenames: KS_DATARANGE_BDA_TRANSPORT, *PKS_DATARANGE_BDA_TRANSPORT
---

# tagKS_DATARANGE_BDA_TRANSPORT structure


## -description


The KS_DATARANGE_BDA_TRANSPORT structure describes a range of data formats for a BDA transport stream. 


## -syntax


````
typedef struct tagKS_DATARANGE_BDA_TRANSPORT {
  KSDATARANGE        DataRange;
  BDA_TRANSPORT_INFO BdaTransportInfo;
} KS_DATARANGE_BDA_TRANSPORT, *PKS_DATARANGE_BDA_TRANSPORT;
````


## -struct-fields




### -field DataRange

KSDATARANGE structure that describes a range of data formats.


### -field BdaTransportInfo

BDA_TRANSPORT_INFO structure that describes formatting for a BDA transport stream connection. 


## -remarks



A BDA_TRANSPORT_INFO structure in conjunction with a KSDATARANGE structure makes up a KS_DATARANGE_BDA_TRANSPORT data range. A data range describes a range of data formats. 

Pins of filters specify the data ranges they support to enable stream connections to pins of other filters that also support those data ranges.




## -see-also

<a href="..\ks\ns-ks-kspin_descriptor.md">KSPIN_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561658">KSDATARANGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556552">BDA Stream Format GUIDs</a>



<a href="..\bdamedia\ns-bdamedia-tagbda_transport_info.md">BDA_TRANSPORT_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_DATARANGE_BDA_TRANSPORT structure%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

