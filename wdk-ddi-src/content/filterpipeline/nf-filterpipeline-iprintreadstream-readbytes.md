---
UID: NF:filterpipeline.IPrintReadStream.ReadBytes
title: IPrintReadStream::ReadBytes (filterpipeline.h)
description: The ReadBytes method reads a number of bytes into a buffer.
old-location: print\iprintreadstream_readbytes.htm
tech.root: print
ms.assetid: 41ba600d-8b89-4e07-950a-a2518c2572a6
ms.date: 04/20/2018
keywords: ["IPrintReadStream::ReadBytes"]
ms.keywords: IPrintReadStream interface [Print Devices],ReadBytes method, IPrintReadStream.ReadBytes, IPrintReadStream::ReadBytes, ReadBytes, ReadBytes method [Print Devices], ReadBytes method [Print Devices],IPrintReadStream interface, filterpipeline/IPrintReadStream::ReadBytes, filterpipeline_92cb33c3-6229-47ca-b3da-2f4c268f8b7b.xml, print.iprintreadstream_readbytes
f1_keywords:
 - "filterpipeline/IPrintReadStream.ReadBytes"
 - "IPrintReadStream.ReadBytes"
req.header: filterpipeline.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: Filterpipeline.idl
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
- COM
api_location:
- filterpipeline.h
api_name:
- IPrintReadStream.ReadBytes
targetos: Windows
req.typenames: 
---

# IPrintReadStream::ReadBytes


## -description


The <code>ReadBytes</code> method reads a number of bytes into a buffer.


## -parameters




### -param pvBuffer 
[out]
A pointer to the buffer that the bytes will be read into..


### -param cbRequested 
[in]
The number of bytes that are requested for the read.


### -param pcbRead 
[out]
A pointer to the number of bytes actually read.


### -param pbEndOfFile 
[out]
A pointer to a <b>BOOL</b> value that indicates whether the end of file (EOF) was read.


## -returns



<code>ReadBytes</code> returns an <b>HRESULT</b> value.



