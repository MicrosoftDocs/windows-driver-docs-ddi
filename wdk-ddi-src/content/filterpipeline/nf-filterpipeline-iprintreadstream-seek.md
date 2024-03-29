---
UID: NF:filterpipeline.IPrintReadStream.Seek
title: IPrintReadStream::Seek (filterpipeline.h)
description: The Seek method changes the seek pointer to a new location in the stream.
old-location: print\iprintreadstream_seek.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["IPrintReadStream::Seek"]
ms.keywords: IPrintReadStream interface [Print Devices],Seek method, IPrintReadStream.Seek, IPrintReadStream::Seek, Seek, Seek method [Print Devices], Seek method [Print Devices],IPrintReadStream interface, filterpipeline/IPrintReadStream::Seek, filterpipeline_622c8e3a-c21f-4784-ba2d-96833fab4230.xml, print.iprintreadstream_seek
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IPrintReadStream::Seek
 - filterpipeline/IPrintReadStream::Seek
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - filterpipeline.h
api_name:
 - IPrintReadStream::Seek
---

# IPrintReadStream::Seek


## -description

The <code>Seek</code> method changes the seek pointer to a new location in the stream.

## -parameters

### -param dlibMove [in]


The displacement that is added to the location that <i>dwOrigin</i> specifies.

### -param dwOrigin [in]


The origin for the displacement that <i>dlibMove</i> specifies. The origin can be the beginning of the file (STREAM_SEEK_SET), the current seek pointer (STREAM_SEEK_CUR), or the end of the file (STREAM_SEEK_END).

### -param plibNewPosition [out]


A pointer to the location where <code>Seek</code> writes the value of the new seek pointer from the beginning of the stream.

## -returns

<code>Seek</code> returns an <b>HRESULT</b> value.

## -remarks

The <code>Seek</code> method might block, for example, if seeking to the end of the stream.

This method is similar to the <b>IStream::Seek</b> and <b>SetFilePointerEx</b> methods. For more information about these methods, see the Microsoft Windows SDK documentation.

