---
UID: NC:hdaudio.PGET_RESOURCE_INFORMATION
title: PGET_RESOURCE_INFORMATION (hdaudio.h)
description: The GetResourceInformation routine retrieves information about hardware resources.The function pointer type for a GetResourceInformation routine is defined as follows.
old-location: audio\getresourceinformation.htm
tech.root: audio
ms.assetid: ba1f0fa2-77dd-4ec3-86c8-c5d74465743f
ms.date: 05/08/2018
keywords: ["PGET_RESOURCE_INFORMATION callback function"]
ms.keywords: GetResourceInformation, GetResourceInformation callback function [Audio Devices], PGET_RESOURCE_INFORMATION, PGET_RESOURCE_INFORMATION callback, aud-prop2_03b48e3f-0650-45eb-b1d2-0db5e2e98636.xml, audio.getresourceinformation, hdaudio/GetResourceInformation
req.header: hdaudio.h
req.include-header: Hdaudio.h
req.target-type: Desktop
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PGET_RESOURCE_INFORMATION
 - hdaudio/PGET_RESOURCE_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - hdaudio.h
api_name:
 - GetResourceInformation
---

# PGET_RESOURCE_INFORMATION callback function


## -description

The <code>GetResourceInformation</code> routine retrieves information about hardware resources.

The function pointer type for a <code>GetResourceInformation</code> routine is defined as follows.

## -parameters

### -param _context 

[in]
Specifies the context value from the <b>Context</b> member of the <a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface">HDAUDIO_BUS_INTERFACE</a><u>, </u><a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_v2">HDAUDIO_BUS_INTERFACE_V2</a>, or <a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_bdl">HDAUDIO_BUS_INTERFACE_BDL</a> structure.

### -param CodecAddress

### -param FunctionGroupStartNode

#### - codecAddress [out]

Retrieves a codec address. This parameter points to a caller-allocated UCHAR variable into which the routine writes a codec address. The codec address identifies the serial data in (SDI) line on which the codec supplies response data to the HD Audio bus controller. A bus controller with <i>n</i> SDI pins can support up to <i>n</i> codecs with addresses that range from 0 to <i>n</i>-1.


#### - functionGroupStartNode [out]

Retrieves the function group's starting node ID. This parameter points to a caller-allocated UCHAR variable into which the routine writes the node ID. For more information, see the following Remarks section.

## -remarks

A codec contains one or more function groups. Each function group contains some number of nodes that are numbered sequentially beginning with the starting node. For example, if a function group contains three nodes and the starting node has a node ID of 9, the other two nodes in the function group have node IDs 10 and 11. For more information, see the Intel High Definition Audio Specification at the <a href="https://go.microsoft.com/fwlink/p/?linkid=42508">Intel HD Audio</a> website.

## -see-also

<a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface">HDAUDIO_BUS_INTERFACE</a>



<a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_bdl">HDAUDIO_BUS_INTERFACE_BDL</a>



<a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_v2">HDAUDIO_BUS_INTERFACE_V2</a>