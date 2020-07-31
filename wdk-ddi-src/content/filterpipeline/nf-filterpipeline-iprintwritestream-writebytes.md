---
UID: NF:filterpipeline.IPrintWriteStream.WriteBytes
title: IPrintWriteStream::WriteBytes (filterpipeline.h)
description: The WriteBytes method writes a specified number of bytes to a stream.
old-location: print\iprintwritestream_writebytes.htm
tech.root: print
ms.assetid: d47c836e-a291-4cc2-9688-82526f8bfb8b
ms.date: 04/20/2018
keywords: ["IPrintWriteStream::WriteBytes"]
ms.keywords: IPrintWriteStream interface [Print Devices],WriteBytes method, IPrintWriteStream.WriteBytes, IPrintWriteStream::WriteBytes, WriteBytes, WriteBytes method [Print Devices], WriteBytes method [Print Devices],IPrintWriteStream interface, filterpipeline/IPrintWriteStream::WriteBytes, filterpipeline_168a03b1-8fdc-4a98-9a5f-5c706fcd401b.xml, print.iprintwritestream_writebytes
f1_keywords:
 - "filterpipeline/IPrintWriteStream.WriteBytes"
 - "IPrintWriteStream.WriteBytes"
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
- IPrintWriteStream.WriteBytes
targetos: Windows
req.typenames: 
---

# IPrintWriteStream::WriteBytes


## -description


The <code>WriteBytes</code> method writes a specified number of bytes to a stream.


## -parameters




### -param pvBuffer [in]

A pointer to the buffer that the bytes will be written from.


### -param cbBuffer [in]

The size of the buffer to be read from.


### -param pcbWritten [out]

A pointer to the number of bytes actually written. 


## -returns



<code>WriteBytes</code> returns an <b>HRESULT</b> value.



