---
UID: NE:d3d12umddi.D3D12DDI_HANDLETYPE
title: D3D12DDI_HANDLETYPE
author: windows-driver-content
description: Contains driver handle types.
old-location: display\d3d12ddi_handletype.htm
old-project: display
ms.assetid: 807CC73E-C5A5-4D49-AFAF-32A51D832F82
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_HANDLETYPE, D3D12DDI_HANDLETYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D12DDI_HANDLETYPE
req.alt-loc: D3d12umddi.h
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
req.typenames: D3D12DDI_HANDLETYPE
---

# D3D12DDI_HANDLETYPE enumeration



## -description
Contains driver handle types.



## -syntax

````
typedef enum D3D12DDI_HANDLETYPE { 
  D3D12DDI_HT_COMMAND_QUEUE                  = 19,
  D3D12DDI_HT_COMMAND_ALLOCATOR              = 20,
  D3D12DDI_HT_PIPELINE_STATE                 = 21,
  D3D12DDI_HT_COMMAND_LIST                   = 22,
  D3D12DDI_HT_FENCE                          = 23,
  D3D12DDI_HT_DESCRIPTOR_HEAP                = 24,
  D3D12DDI_HT_HEAP                           = 25,
  D3D12DDI_HT_QUERY_HEAP                     = 27,
  D3D12DDI_HT_COMMAND_SIGNATURE              = 28,
  D3D12DDI_HT_0010_PIPELINE_LIBRARY          = 29,
  D3D12DDI_HT_0020_VIDEO_DECODER             = 30,
  D3D12DDI_HT_0020_VIDEO_DECODE_STREAM       = 31,
  D3D12DDI_HT_0020_VIDEO_PROCESSOR           = 32,
  D3D12DDI_HT_0020_VIDEO_PROCESS_STREAM      = 33,
  D3D12DDI_HT_0012_RESOURCE                  = 34,
  D3D12DDI_HT_PASS                           = 35,
  D3D12DDI_HT_0030_CRYPTOSESSION             = 36,
  D3D12DDI_HT_0030_CRYPTOSESSIONPOLICY       = 37,
  D3D12DDI_HT_0030_PROTECTEDRESOURCESESSION  = 37,
  D3D12DDI_HT_0032_VIDEO_DECODER_HEAP        = 39
} D3D12DDI_HANDLETYPE;
````


## -enum-fields

### -field D3D12DDI_HT_COMMAND_QUEUE

A command queue handle type.


### -field D3D12DDI_HT_COMMAND_ALLOCATOR

A command allocator handle type.


### -field D3D12DDI_HT_PIPELINE_STATE

A pipeline state handle type.


### -field D3D12DDI_HT_COMMAND_LIST

A command list handle type.


### -field D3D12DDI_HT_FENCE

A fence handle type.


### -field D3D12DDI_HT_DESCRIPTOR_HEAP

A descriptor heap handle type.


### -field D3D12DDI_HT_HEAP

A heap handle type.


### -field D3D12DDI_HT_QUERY_HEAP

A query heap handle type.


### -field D3D12DDI_HT_COMMAND_SIGNATURE

A command signature handle type.


### -field D3D12DDI_HT_0010_PIPELINE_LIBRARY

A pipeline library handle type.


### -field D3D12DDI_HT_0020_VIDEO_DECODER

A video decoder handle type.


### -field D3D12DDI_HT_0020_VIDEO_DECODE_STREAM

A video decode stream handle type.


### -field D3D12DDI_HT_0020_VIDEO_PROCESSOR

A video processor handle type.


### -field D3D12DDI_HT_0020_VIDEO_PROCESS_STREAM

A video process stream handle type.


### -field D3D12DDI_HT_0012_RESOURCE

A resource handle type.


### -field D3D12DDI_HT_PASS

A pass handle type.


### -field D3D12DDI_HT_0030_CRYPTOSESSION

A crypto session handle type.


### -field D3D12DDI_HT_0030_CRYPTOSESSIONPOLICY

A crypto session policy handle type.


### -field D3D12DDI_HT_0030_PROTECTEDRESOURCESESSION

A protected resource session handle type.


### -field D3D12DDI_HT_0032_VIDEO_DECODER_HEAP

A video decoder heap handle type.


## -remarks
